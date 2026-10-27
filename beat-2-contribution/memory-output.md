Almost all of the keyboard shortcut code lives in one file, `avogadro/mainwindow.cpp`. I stayed inside `avogadro/` as you asked.

## Where the shortcut behavior lives

Shortcuts are set up in three different ways:

1. **Action shortcuts (shortcuts on menu items).** In `MainWindow::buildMenu()` (`mainwindow.cpp:3370` onward), each `QAction` gets a `setShortcut(...)` call:
   - New, Open, Close, Save, Save As, Quit (around lines 3390–3481)
   - Undo/Redo (3517, 3525) and Copy Image as `Ctrl+Alt+C` (3531)
   - The finished actions are registered with `m_menuBuilder->addAction(path, action, priority)`.
2. **Tool shortcuts.** In the tool toolbar setup (`mainwindow.cpp:3745–3757`), tools 1 through 10 get `Ctrl+1` … `Ctrl+9` and then `Ctrl+0`.
3. **Shortcuts with no menu item.** In the `MainWindow` constructor (`mainwindow.cpp:631–651`), `QShortcut` objects are created directly:
   - `Ctrl+Tab` / `Ctrl+Shift+Tab` (`Meta+…` on macOS) are connected to `nextMolecule()` / `previousMolecule()` (declared at `mainwindow.h:583–590`).
4. **Reserved camera keys.** The constructor calls `qApp->installEventFilter(this)` (`mainwindow.cpp:481`). After that, `MainWindow::eventFilter` (`mainwindow.cpp:1067`) and the helpers `isNavigationShortcut` and `isTextEntry` (1039–1063) catch `Ctrl+arrow` and pass it to the active `GLWidget`, so the camera moves even when keyboard focus is in a dock. They first claim the `ShortcutOverride` event so no other shortcut grabs the keys, and they skip text-entry widgets.

**Your uncommitted change at `mainwindow.cpp:648–650` won't compile:**
```cpp
auto* nextSection = new QShortcut(QKeySequence("F6"), this);
connect(nextSection, &QShortcut::activated, this,
        &MainWindow::)
```
The slot name is missing and the line has no closing `;`. You'll need to add a slot (declared in `mainwindow.h` next to `nextMolecule`) before this will build.

Also, `git status` lists nearly every file as modified. Ignoring whitespace, the only real change in `mainwindow.cpp`/`.h` is those 4 lines. The rest is probably line-ending churn from OneDrive or Windows, so set `core.autocrlf` or renormalize before you commit, or your PR diff will touch the whole file.

## The files that matter

| File                          | Role                                                                                                                                                                      |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `avogadro/mainwindow.cpp`     | All shortcut wiring: actions, `QShortcut`s and the event filter                                                                                                           |
| `avogadro/mainwindow.h`       | Declarations for the slots (`nextMolecule`, `previousMolecule`, any new one) and the `eventFilter` override (line 366)                                                    |
| `avogadro/mainwindow.ui`      | Qt Designer actions with `shortcut` properties (Open, Quit, New, Close, Save, Undo/Redo, Cut/Copy/Paste, Select All/None)                                                 |
| `avogadro/menubuilder.cpp/.h` | Builds the menu bar from the actions `MainWindow` hands it (`addAction` → `buildMenuBar`). It doesn't set shortcuts; it only strips `&` mnemonics from titles (line 129). |

## How they connect

The `MainWindow` constructor:
- loads `mainwindow.ui`
- calls `buildMenu()`, which creates actions, sets their shortcuts and passes them to `MenuBuilder`
- calls `m_menuBuilder->buildMenuBar(menuBar())` (line 553)
- then adds the standalone `QShortcut`s (line 631 onward)

Separately, the app-wide event filter sends `Ctrl+arrow` to the `GLWidget`. Tool plugins supply their own `QAction`s, and `MainWindow` assigns `Ctrl+N` to those.

## Tests

There are no unit tests inside `avogadro/`. Testing there is built on QtTesting (a record-and-replay UI test library), enabled with `ENABLE_TESTING` (`avogadro/CMakeLists.txt:110–117` and `275–276`). It adds a **Testing → Record Test… / Play Test…** menu (`mainwindow.cpp:3370–3379`). The actual tests are in the top-level `tests/` directory, which I didn't open because it's outside `avogadro/`. Say if you want me to look there for existing shortcut or key-event tests.


-----------------------

Nothing in `tests/` covers keyboard shortcuts, key events or focus handling. Both test systems drive the app without a keyboard, so you can't test a new shortcut directly without extra work.

## What's in `tests/`

**1. QtTesting XML replays** (`tests/CMakeLists.txt:1–31`)
- These replay UI recordings made with the **Testing → Record Test…** menu I mentioned earlier.
- The recordings aren't in this repo. They live in a separate repo, `avogadrodata`, under `tests/avogadro/xml/*.xml`.
- `avogadrodata` isn't in your clone steps, so if it's missing CMake prints "No data root found" and adds none of the tests.
- In principle this is the only system that could record a real key press.

**2. End-to-end tests over RPC** (`tests/rpc/`, pytest)
- These launch the real app and control it through its JSON-RPC socket (the remote-control interface in `avogadro/rpclistener.cpp`).
- They run as the CTest tests `avogadro-rpc` and `avogadro-rpc-corpus`.
- They need pytest plus `avogadro/connect.py` from `avogadrolibs/python`.
- The RPC interface has no method to send a key, trigger a `QAction` or move focus. It only exposes commands like `setActiveMolecule`, `activateTool`, `undo` and `selectAll`, so a test calls `undo` directly instead of pressing Ctrl+Z.

## Files worth reading

| File                                                                                      | Why it matters                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `tests/rpc/test_builtins.py:451–478`                                                      | Tests `setActiveMolecule`: valid index, out-of-range index, error replies. This is the closest existing test to `nextMolecule`/`previousMolecule` (the Ctrl+Tab slots).                                   |
| `tests/rpc/test_molecules.py:168–277`                                                     | Switches between several open molecules and checks each keeps its own undo history and layers. If your shortcut changes the active molecule or which panel it lands on, this is the state to keep intact. |
| `tests/rpc/scenarios/multi_molecule_layers.json`, `close_active_molecule_neighbours.json` | JSON scenarios that switch molecules. Good models if you add a scenario.                                                                                                                                  |
| `tests/rpc/test_builtins.py:517`                                                          | `listTools`/`activateTool`, the RPC version of the Ctrl+1…Ctrl+0 tool shortcuts.                                                                                                                          |
| `tests/rpc/README.md`                                                                     | Rules for these tests. The important one: **nothing may open a modal dialog**. If your shortcut opens one, it can't run under these tests.                                                                |

## What this means for issue #910

- **Regression check:** run `python -m pytest tests/rpc --avogadro ./build/prefix/bin/avogadro2 -m "not corpus"` (or `ctest -R avogadro-rpc`) to confirm nothing around molecule switching or tools broke.
- **Testing the shortcut itself:** your realistic options are:
  - manual testing, written up step by step in the PR
  - a QtTesting recording, which would need a PR to the separate `avogadrodata` repo
  - a new RPC method that triggers an action. I'd ask the maintainers before adding test hooks to `rpclistener.cpp`.