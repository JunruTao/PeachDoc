# Module peach.pHoudini


## Sub-Modules
- panels  <sup>` (utility module) `</sup>
- tools <sup>` (utility module) `</sup>
  - dev_tools <sup>` (utility module) `</sup>


## Topics
- [Module peach.pHoudini](#module-peachphoudini)
  - [Sub-Modules](#sub-modules)
  - [Topics](#topics)
  - [1. pHoudini.hNode](#1-phoudinihnode)
    - [1.0 Dependencies](#10-dependencies)
    - [1.1 Selection](#11-selection)
    - [1.2 Naming](#12-naming)
    - [1.3 Color](#13-color)
  - [2. pHoudini.wm](#2-phoudiniwm)
    - [2.0 Dependencies](#20-dependencies)
    - [2.1 Getting Main Window Properties](#21-getting-main-window-properties)

<br><br>

## 1. pHoudini.hNode
This layer implement `<hou.node/Node>` functions, anything related to hou node management.

### 1.0 Dependencies
- `hou`
- `peach.pImp`
- `peach.pLog`

### 1.1 Selection

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> select </code><sup>(node=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : node to select<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> deselect </code><sup>(node=None)</sup><br><br>
    <blockquote>
    If there's no node specified, selection will be cleared.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : node to deselect<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> listSelected </code><sup>(item=False, connection=False, bundle=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>bool</code>  <b> item </b> : if list selected items<br>
    <!--@param-->- <code>bool</code>  <b> connection </b> : if list selected connections<br>
    <!--@param-->- <code>bool</code>  <b> bundle </b> : if list selected bundle<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>tuple of hou items</code>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<br><br>


### 1.2 Naming

name/rename fucntions.

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> rename </code><sup>(node=None, name="", sel=False)</sup><br><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : houdini node<br>
    <!--@param-->- <code>str</code>  <b> name </b> : target name to rename to<br>
    <!--@param-->- <code>bool</code>  <b> sel </b> : if query selected<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> getName </code><sup>(node=None)</sup><br><br>
    <blockquote>
    
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> :  houdini node<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> node name
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->



```python
from peach.pHoudini import hNode

sl = hNode.listSelected()
if sl:
    hNode.rename(sl[0], "new_name")

```



<br><br>

### 1.3 Color
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> getColor </code><sup>(node=None)</sup><br><br>
    <blockquote>
    
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> :  houdini node<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> hou.Color</code> node color
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<sup>Other Getters:</sup>

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> getColorRGB </code><sup>(node=None)</sup><br>
    <sup>peach.pHoudini.</sup> hNode.<code> getColorHSV </code><sup>(node=None)</sup><br>
    <sup>peach.pHoudini.</sup> hNode.<code> getColorHSL </code><sup>(node=None)</sup><br>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> :  houdini node<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> tuple </code>color value
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

Set Color:

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> hNode.<code> changeColor </code><sup>(node, *args)</sup><br><br>
    <blockquote>
    
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> :  houdini node<br>
    <!--@param-->- <code>hou.Color or float</code>  <b> args </b> : houdini color or tuple of RGB <br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<br><br>

## 2. pHoudini.wm

### 2.0 Dependencies
- `hou`

### 2.1 Getting Main Window Properties
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