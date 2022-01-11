# Module pQt

## Topics
- [Module pQt](#module-pqt)
  - [Topics](#topics)
  - [Sub-Modules](#sub-modules)
  - [1. pQt.qHotel](#1-pqtqhotel)
  - [2. pQt.pq_ico](#2-pqtpq_ico)
    - [2.0 Dependencies](#20-dependencies)
    - [2.1 Getting QPixmap object](#21-getting-qpixmap-object)
    - [2.2 Using pQt Icon Manager](#22-using-pqt-icon-manager)

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

### 2.1 Getting QPixmap object

__Examples:__

- From _name_ get _QtGui.QPixmap_ object.
```python
from peach.pQt import pq_ico

q_pixmap = pq_ico.getIcon("peach")
```

<br><br>

### 2.2 Using pQt Icon Manager 

__Examples:__
- Use Icon Manager, pre-log _QtGui.QPixmap_ objects and query them.
```python
from peach.pQt import pq_ico

pq_im = pq_ico.IconManager()
pq_im.stash("peach", "peach_dev", "peachFolder_dev")

qPxm_peach = pq_im.get("peach")
```