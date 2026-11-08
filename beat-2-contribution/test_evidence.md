## Before (master, 77e13db, v2.1.0, WSL)
Build: `git checkout master && cmake --build ../../build`
| Step | Key | Expected | Observed |
|---|---|---|---|
| 1.3 | F6 from 3D view | focus moves to a pane | Nothing happens. Focus stays in the 3D view; F6 is not bound. |
| 2.3 | Shift+F6 | focus moves to the previous pane | Nothing happens. |

## After (feat/910-pane-shortcuts, 4ff3030d)
| Test | Key presses | Focus landed on (in order) | Pass |
|---|---|---|---|
| 1 Default layout | F6 ×6 | 3D view → Tool → Display Types → Display Type Settings → Molecules → 3D view | ✅ |
| 2 Default layout | Shift+F6 ×6 | 3D view → Molecules → Display Type Settings → Display Types → Tools → 3D view | ✅ |
| 3 Hidden/empty panes | F6 ×5 | … never Layers (behind Files) or empty Display Type Settings | ✅ |
| 4 Tools dragged to bottom | F6 ×1 | Display Types (Tools last) | ✅ |
| 5 One pane per area | F6 ×4 | 3D view → Top → Left → Right → Bottom → 3D view | ✅ |