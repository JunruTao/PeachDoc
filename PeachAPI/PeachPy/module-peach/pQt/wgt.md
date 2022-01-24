# pQt.wgt

## Contents
- [pQt.wgt](#pqtwgt)
  - [Contents](#contents)
  - [1. Template Widget Functions](#1-template-widget-functions)
    - [1.1 Built in Header Helper](#11-built-in-header-helper)

## 1. Template Widget Functions
### 1.1 Built in Header Helper

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> getHeaderTemplateWidget </code><sup>(**kwargs)</sup><br><br>
    <blockquote>[ Get Header Widget ]</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>Flags</code>  <b> kwargs </b> :  settings- see file<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> QWidget</code> constructed widget
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

__Example (Dev-tool Header)__

```python
# in side a widget class..

ttl = "pHoudini-DevTool: Sop Renamer".format(pGlob.PEACH_PY_VERSION)
self.lbl_header = wgt.getHeaderTemplateWidget(type="dev_tool",
                                              title=ttl,
                                              height=70,
                                              font_size=23)

self.master_layout.addWidget(self.lbl_header)
# ...

```