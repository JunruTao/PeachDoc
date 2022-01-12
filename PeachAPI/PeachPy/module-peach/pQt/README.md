# Module pQt

## Topics
- [Module pQt](#module-pqt)
  - [Topics](#topics)
  - [Sub-Modules](#sub-modules)
  - [1. pQt.qHotel](#1-pqtqhotel)
  - [2. pQt.pq_ico](#2-pqtpq_ico)
    - [2.0 Dependencies](#20-dependencies)
    - [2.1 Getting QPixmap object](#21-getting-qpixmap-object)
    - [2.2 Using pq_ico Icon Manager](#22-using-pq_ico-icon-manager)

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

## 2. pQt.pq_ico
### 2.0 Dependencies
- `peach.pQt.qHotel`
- `peach.Imp`
- `peach.Ico`

### 2.1 Getting QPixmap object

<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> getPixmap </code><sup>(name="", size="x25")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> : Icon Name
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
from peach.pQt import pq_ico

q_pixmap = pq_ico.getPixmap("peach", size="x25")
```

<br><br>

### 2.2 Using pq_ico Icon Manager 

__Examples:__
- Use Icon Manager, pre-log _QtGui.QPixmap_ objects and query them.
```python
from peach.pQt import pq_ico

pq_im = pq_ico.IconManager()
pq_im.stash("peach", "peach_dev", "peachFolder_dev")

qPxm_peach = pq_im.get("peach")
```