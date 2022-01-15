# Module pQt

## Topics
- [Module pQt](#module-pqt)
  - [Topics](#topics)
  - [Sub-Modules](#sub-modules)
  - [1. pQt.qHotel](#1-pqtqhotel)
  - [2. pQt.img](#2-pqtimg)
    - [2.0 Dependencies](#20-dependencies)
    - [2.1 Getting QPixmap object](#21-getting-qpixmap-object)
    - [2.2 Using img Icon Manager](#22-using-img-icon-manager)
      - [4.3.1 Constructor](#431-constructor)

<br><br>

## Sub-Modules
- > None
<br><br>

## 1. pQt.qHotel
This is a Qt, PyQt, PySide wrapper. Instead of importing from PySide2, which might change in other senarios for example importing from PyQt5, it is not very handy to change all the imports in each file that uses Qt functions.

> usage:

```python 
from peach.pQt.qHotel import QtWidgets, QtGui
```

## 2. pQt.img
### 2.0 Dependencies
- `peach.pQt.qHotel`
- `peach.Imp`
- `peach.Ico`

### 2.1 Getting QPixmap object

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pQt.</sup> img.<code> getPixmap </code><sup>(name="", size="x25")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> : Icon Name<br>
    <!--@param-->- <code>str</code>  <b> size </b> : i.g. "x25", "SVG" etc
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>QtGui.QPixmap</code> or <code>None</code> Qt Pixmap object
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


__Examples:__

- From _name_ get _QtGui.QPixmap_ object.
```python
from peach.pQt import img

q_pixmap = img.getPixmap("peach", size="x25")
```

<br><br>

### 2.2 Using img Icon Manager 

Updates: <sub>@<sup>Added[ 2022-01-12 23:14 ]</sup></sub><br>

<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `object` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.pQt.</sup> img.<code> IconManager </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

> member functions:
#### 4.3.1 Constructor

<!--///////////////////Function-Table/////////////////////-->
- <sub>`constructor` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    IconManager.<code> __init__ </code><sup>(self, size="x25")</sup><br><br>
    <blockquote>
    <sub>@<sup>Added[ 2022-01-12 22:42 ]</sup></sub><br>
    When IconManager's constructor is called, you need specify the which size of icons this manager is managing.<br>However, you can query other sizes from this manager if other icons are created first somewhere in Runtime.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> size </b> : i.g. "x25", "SVG" etc
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`member` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    IconManager.<code> stash </code><sup>(*args)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>*str</code>  <b> name </b> : icon names you want to stash in.
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`member`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    IconManager.<code> stash_all </code><sup>(*args)</sup><br>
    <blockquote>
    Stash the found icon of this manager's size.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    IconManager.<code> get </code><sup>(self, name, size_="")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> : Icon Name<br>
    <!--@param-->- <code>str</code>  <b> size </b> : i.g. "x25", "SVG" etc
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>QtGui.QPixmap</code> or <code>None</code>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->



__Examples:__
- Use Icon Manager, pre-log _QtGui.QPixmap_ objects and query them.
```python
from peach.pQt import img

pq_im = img.IconManager()
pq_im.stash("peach", "peach_dev", "peachFolder_dev")

qPxm_peach = pq_im.get("peach")
```