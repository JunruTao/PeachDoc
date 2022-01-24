# pQt.style

## Contents:
- [pQt.style](#pqtstyle)
  - [Contents:](#contents)
  - [1. dependencies](#1-dependencies)
  - [2. Global Vars and Fonts](#2-global-vars-and-fonts)
  - [3. Style Sheet Helper](#3-style-sheet-helper)
    - [3.1 Make unique ids for each object in session:](#31-make-unique-ids-for-each-object-in-session)
    - [3.2 Sheet Class](#32-sheet-class)
      - [3.2.1 Constructor](#321-constructor)
      - [3.2.2 Key Function](#322-key-function)
      - [3.2.3 Getters](#323-getters)
      - [3.2.4 Setters](#324-setters)
      - [3.2.5 Examples](#325-examples)


## 1. dependencies
- `peach.pQt.qHotel`/`PySide2`
- `peach`
- `datetime`
- `re`


## 2. Global Vars and Fonts
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


## 3. Style Sheet Helper

### 3.1 Make unique ids for each object in session:


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

### 3.2 Sheet Class 

<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `object` </sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.</sup> pDir.<code> Sheet </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


#### 3.2.1 Constructor

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


#### 3.2.2 Key Function


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


#### 3.2.3 Getters


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


#### 3.2.4 Setters


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


#### 3.2.5 Examples

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