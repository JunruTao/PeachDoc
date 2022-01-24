# pHoudini.wm

## Contents
- [pHoudini.wm](#phoudiniwm)
  - [Contents](#contents)
  - [1. Dependencies](#1-dependencies)
  - [2. Getting Main Window Properties](#2-getting-main-window-properties)
  - [3. Houdini Editor/Panes](#3-houdini-editorpanes)

## 1. Dependencies
- `hou`

## 2. Getting Main Window Properties
Houdini's window manager functions.

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> wm.<code> getMainWindow </code><sup>(item=False, connection=False, bundle=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>QtWidgets.QWidget</code> Houdini Main window widget
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> wm.<code> getMainWindowRect </code><sup>(item=False, connection=False, bundle=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>QtWidgets.QRect</code> Houdini Main window Rectangle
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> wm.<code> getMainWindowCenter </code><sup>(item=False, connection=False, bundle=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>QtWidgets.QPoint</code> Houdini Main window Center point
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


__Handy Usage Example:__

```python
from peach.pQt.qHotel import QtWidgets
from peach.pHoudini import wm

class MyUI(QtWidgets.QWidget)
    def __init__(self, parent=None):
        QtWidgets.QWidget.__init__(self, parent, QtCore.Qt.WindowStaysOnTopHint)

        # Set Dialog's location to the center of Houdini's window
        p = wm.getMainWindowCenter()
        self.setGeometry(p.x(), p.y(), 250, 110)
        self.setWindowTitle('Center Screen Widget Demo')

        #... ui buidling

```

<br><br>

## 3. Houdini Editor/Panes


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> getCurrentEditor() </code><br><br>
    <blockquote>[ Houdini ] get Current working Network</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> hou.Pane</code>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

