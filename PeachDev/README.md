# Peach Developer Documentation(Internal)

## Contents:
- [Peach Developer Documentation(Internal)](#peach-developer-documentationinternal)
  - [Contents:](#contents)
  - [pHoudini:](#phoudini)
    - [1. Adding New PyPanel:](#1-adding-new-pypanel)

## pHoudini:
### 1. Adding New PyPanel:
This process is being automated by CMake scripts, if needs to add new pypanel to pHoudini Package. Follow the following steps:

1. :black_circle: __Go to__ `${peach_dev_dir}/lib/peach/houdini_panels`
   <br><br>
2. :black_circle: __Create a new directory, name it with the panel name__
   - in this case, I'll name with `new_panel` <br><br>
3. :black_circle: __Create 2 files under this__ `new_panel` __directory:__
   1. `pypanel_new_panel.py`
        > the nameing follows `pypanel_<your_panel_name>`. After, open this file and write your panel script in here. for example:
        ```python
        from peach import pImp
        from peach.pHoudini.panels import my_panel
        pImp.reload(my_panel)


        def onCreateInterface():
            # on create is Houdini pypanel template function:
            widget = my_panel.MyPanelUI()
            return widget
        ``` 
        <br>

    1. `CMakeLists.txt` - a CMake File:
        > Open this file, you should follow this format and write following information:
        ```cmake
        # ------------------------------------------------
        # Houdini Panel CMake Configuration
        # [ new_panel ]

        # 1. Which Package to install this panel to
        set(TARGET_PKG "PeachAsset" PARENT_SCOPE)

        # 2. Panel Lable:
        set(PANEL_LABEL "New Panel" PARENT_SCOPE)

        # 3. Choose an Icon
        set(PANEL_ICON "peach_dev" PARENT_SCOPE)

        # 4. if this pane panel has a divider (optional)
        set(PANEL_MENU_SPR "false" PARENT_SCOPE)
        ```
        <br><br>

4. :black_circle: Go back to directory `../houdini_panels` and open up `CMakeLists.txt` file under this folder:
   - Add this name to: 
    ```cmake
    # ...
    # [ SUBDIRS OF PANELS ]
    list(APPEND PANEL_NAMES 
            "peach_main"
            "asset_browser"
            "new_panel"  # <----- HERE
    )
    # ...
    ``` 

5. :black_circle: Build Project. `mingw32-make`