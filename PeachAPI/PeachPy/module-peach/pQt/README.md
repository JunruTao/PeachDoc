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
  - [3. pQt.style](#3-pqtstyle)
    - [3.0 dependencies](#30-dependencies)
    - [3.1 Global Vars and Fonts](#31-global-vars-and-fonts)
    - [3.2 Style Sheet Helper](#32-style-sheet-helper)

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

<br><br>

## 3. pQt.style

### 3.0 dependencies
- `peach.pQt.qHotel`/`PySide2`
- `peach`
- `datetime`
- `re`


### 3.1 Global Vars and Fonts
Most of the global varibles act as enums. Therefore by calling the namespace, user should be able to see `WIDGET` &rarr; `"QWidget"`, or fonts like `fnt_Arial` &rarr; `"Arial"` etc.



<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> load_all_custom_fonts() </code><br><br>
    <blockquote>[ Style-Font ] load all the fonts under peach/font folder</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


### 3.2 Style Sheet Helper

1. Make unique ids for each object in session:


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> unique_object_str </code><sup>(obj=None)</sup><br><br>
    <blockquote>[ Style ] Get Unique String for StyleSheet.<br> In order to make each widget more unique and customized,The unique name is required to customize. In the <code>Sheet</code> Class, the format of the sheet will be following:<br> <code>[Category]#[ObjectName] { ... }</code> Style.</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str/QObject/None</code>  <b> obj </b> :  Anything<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> unique name based on time
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

2. Sheet Class 


<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `object` </sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.</sup> pDir.<code> Sheet </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`constructor` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> __init__ </code><sup>(self, obj=None, cat=None, state="default")</sup><br><br>
    <blockquote>[ Sheet ] constructor</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str/QCore.QObject</code>  <b> obj </b> :  any<br>
    <!--@param-->- <code>str/None</code>  <b> cat </b> :  None Auto detect. str. i.g. "QWidget" or use sty.C.wgt<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `member` `return` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> newState </code><sup>(self, state="default")</sup><br><br>
    <blockquote>[ Sheet ] setter (set current_state)<br> Create a new state to store styles. This function shouldbe called first before adding any style.</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> state </b> :  state name, i.g. "warning", "selected"<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> state name
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `member` `return` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> newStateCopy </code><sup>(self, state="default")</sup><br><br>
    <blockquote>[ Sheet ] setter (set current_state)<br> Create a new state to store styles, this function willcopy all the style values in previous(current) state, thenset the current state the new one.</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> state </b> :  state name, i.g. "warning", "selected"<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> state name
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> get </code><sup>(self, state="")</sup><br><br>
    <blockquote>[ Sheet ] getter</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> state </b> :  Specific State to get.<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> Constructed Style Sheet.
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> getStates </code><sup>(self)</sup><br><br>
    <blockquote>[ Sheet ] getter</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> list of str</code> states
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> getObjectName </code><sup>(self)</sup><br><br>
    <blockquote>[ Sheet ] getter</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> object name
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setObject </code><sup>(self, obj=None, cat=None)</sup><br><br>
    <blockquote>[ Sheet ] setter: update sheet object</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str/QCore.QObject</code>  <b> obj </b> :  any<br>
    <!--@param-->- <code>str/None</code>  <b> cat </b> :  None Auto detect. str. i.g. "QWidget" or use sty.C.wgt<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setTextColor </code><sup>(self, *args)</sup><br><br>
    <blockquote>[ Sheet ] setter. config text color</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int/float</code>  <b> args </b> :  f/sRGB<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setBackgroundColor </code><sup>(self, *args)</sup><br><br>
    <blockquote>[ Sheet ] setter. config background color</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int/float</code>  <b> args </b> :  f/sRGB<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setBorderColor </code><sup>(self, *args)</sup><br><br>
    <blockquote>[ Sheet ] setter. config border color</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int/float</code>  <b> args </b> :  f/sRGB<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setBorderStyle </code><sup>(self, style="solid")</sup><br><br>
    <blockquote>[ Sheet ] setter. border style border-style</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> style </b> :  i.g. style<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setBorderWidth </code><sup>(self, width=0, unit="px")</sup><br><br>
    <blockquote>[ Sheet ] setter. set border width(thickness)</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int</code>  <b> width </b> : <br>
    <!--@param-->- <code>str</code>  <b> unit </b> :  unit, i.g. "px", "pt", "em"...<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setBorderRadius </code><sup>(self, radius=0, unit="px")</sup><br><br>
    <blockquote>[ Sheet ] setter. set border radius(roundness)</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int</code>  <b> radius </b> : <br>
    <!--@param-->- <code>str</code>  <b> unit </b> :  unit, i.g. "px", "pt", "em"...<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setFont </code><sup>(self, font="", size=-1, unit="px", i=False, b=False, large=False)</sup><br><br>
    <blockquote>[ Sheet ] setter. set font /style and size</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> font </b> :  font name, "" using application default<br>
    <!--@param-->- <code>int</code>  <b> size </b> :  font size,`-1` doesn't change<br>
    <!--@param-->- <code>str</code>  <b> unit </b> :   i.g. "px", "pt", "em"...<br>
    <!--@param-->- <code>bool</code>  <b> i </b> :  italic<br>
    <!--@param-->- <code>bool</code>  <b> b </b> :  bold<br>
    <!--@param-->- <code>bool</code>  <b> large </b> :  large<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`setter` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> setFontSize </code><sup>(self, size=-1)</sup><br><br>
    <blockquote>[ Sheet ] setter. only set font size</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>int</code>  <b> size </b> :  size<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `member` `args`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> assign </code><sup>(self, *args)</sup><br><br>
    <blockquote>[ Sheet ] modifier. Assign this style to one/multiple objects</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>QObjects</code>  <b> args </b> :  object to assign style sheet<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


__Example:__

```python
# .. in an ui class
    self.bnt1 = QtWidgets.QPushButton("bnt1")
    self.bnt2 = QtWidgets.QPushButton("bnt2")
    self.bnt3 = QtWidgets.QPushButton("bnt3")
    self.bnt4 = QtWidgets.QPushButton("bnt4")

    # create style only for a type, QPushButton
    s_sheet = style.Sheet(cat=style.BUTTON)
    s_sheet.setTextColor(0.9)
    s_sheet.setBorderStyle()
    s_sheet.setBorderWidth(0)
    s_sheet.setBorderRadius(5)
    s_sheet.setBackgroundColor(0.3)
    s_sheet.setFont(style.fnt_Arial, 16, i=True, b=True)
    s_sheet.assign(self.bnt1, 
                   self.bnt2, 
                   self.bnt3)

    # this assign will copy all the attributes 
    # from the current one state. now modify above it
    s_sheet.newStateCopy("dif"):
    s_sheet.setTextColor(0.9, 0, 0)
    s_sheet.assign(self.bnt4)

    # create a new state, brand new style sheet. 
    s_sheet.newState()
    s_sheet.setObject(self)
    s_sheet.setBackgroundColor(62, 9, 35)
    s_sheet.assign(self)
```