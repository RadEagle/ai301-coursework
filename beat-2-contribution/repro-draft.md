Thank you for letting me know. The environment I have now [v2.1.0 (77e13db) in Windows (WSL)] matches what you said. As for AI use, I plan to have the LLM generate code to add shortcuts according to the implementation plan below, and I'll review every line before opening a PR.

## Reproduction Steps
1. Clone the repo according to the instructions outlined [here](https://avogadro.cc/develop/build.html#manual-clone)
    ```bash
    git clone https://github.com/OpenChemistry/openchemistry.git
    cd openchemistry
    git clone https://github.com/OpenChemistry/avogadrolibs.git
    git clone https://github.com/OpenChemistry/avogadroapp.git
    git -C avogadroapp checkout 2.1.0
    git -C avogadrolibs checkout 2.1.0
    ```
2. Follow the setup instructions outlined [here](https://avogadro.cc/develop/build.html#building-avogadro)
    * Perform these commands in the directory named `openchemistry`
    ```bash
    git submodule update --init thirdparty/jkqtplotter
    git submodule update --init fragments molecules crystals avogadro-i18n
    ```

    * Perform these commands in the parent directory of `openchemistry`
    ```
    sudo apt update
    sudo apt install qt6-base-dev qt6-svg-dev libgl1-mesa-dev
    sudo apt install libxml2-dev
    sudo apt install libglu1-mesa-dev
    cmake -DQT_VERSION=6 -DBUILD_MOLEQUEUE=OFF -S ./openchemistry -B ./build
    cmake --build ./build
    ./build/prefix/bin/avogadro2
    ```
3. With the app opened, click on the black display box.
4. Try to cycle focus through visible docks using any key (e.g., F6 and Shift+F6)
    * Because this feature is not implemented yet, there is no way to achieve the desired behavior.

## Behavior
**Expected:** A shortcut exists that cycles through visible docks and 3D view.
**Actual:** No shortcut exists that achieves expected behavior.

## Next Steps (Rough Implementation Plan)
Reading the issue, I searched `F6` and `Qt::Key_F6` in `avogadrolibs` and there is no reference listed, so the shortcut is free to use.

I also noticed while playing with the Avogadro app there is an extra pane "Z-Matrix Editor" that is not visible by default. If shown, should I use `F6` and `Shift+F6` to cycle through that too?

To implement these shortcuts, I will add two `QShortcut`s to `mainwindow.cpp`:

* `F6` - Cycle forward the 3D view and visible dock sections
* `Shift + F6` - Cycle backward the 3D view and visible dock sections

These new shortcuts will be linked to their respective new functions:

* `F6` -> `focusNextPane`
* `Shift + F6` -> `focusPreviousPane`

Here is how the new function `focusNextPane` will be implemented:

1. Construct a list of **visible** panes, listed in the following order
    1. 3D view: `m_multiViewWidget->activeWidget()`
    2. Tool Settings: `m_toolDock`
    3. Display Types: `m_sceneDock`
    4. Display Type Settings: `m_viewDock`
    5. Molecules List: `m_moleculeDock`
    6. Layers: `m_layerDock`
    7. Z-Matrix Editor (if in-scope)
2. If there is only 1 visible pane, return
3. Find which pane in the visible list contains `QApplication::focusWidget()`
4. If there is no pane that has the focus widget, default focus to the 3D view
5. Otherwise, do the following
    1. Get the index of the selected pane
    2. `setFocus()` on the next pane's first focusable child

The function `focusPreviousPane` will be implemented similarly, except we will cycle through the visible panes similar to what `previousMolecule` did. That is, after getting the index, decrement by one, increment by the number of visible panes, then take the remainder after dividing by said number of visible panes.

I will also need to declare these new functions at `mainwindow.h`