# Module `peach.pHoudini`

## Topics
- [Module `peach.pHoudini`](#module-peachphoudini)
  - [Topics](#topics)
  - [Sub-Modules](#sub-modules)
  - [1. pHoudini.node](#1-phoudininode)
    - [1.0 Dependencies](#10-dependencies)
    - [1.1 Selection](#11-selection)
    - [1.2 Naming](#12-naming)

<br><br>

## Sub-Modules
- panel  <sup>` (utility module) `</sup>


<br><br>

## 1. pHoudini.node
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
    <sup>peach.pHoudini.</sup> node.<code> select </code><sup>(node=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : node to select<br>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> node.<code> deselect </code><sup>(node=None)</sup><br><br>
    <blockquote>
    If there's no node specified, selection will be cleared.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : node to deselect<br>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> node.<code> listSelected </code><sup>(item=False, connection=False, bundle=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>bool</code>  <b> item </b> : if list selected items<br>
    <!--@param-->- <code>bool</code>  <b> connection </b> : if list selected connections<br>
    <!--@param-->- <code>bool</code>  <b> bundle </b> : if list selected bundle<br>
    </detials><dv>
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

### 1.2 Naming

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.pHoudini.</sup> node.<code> rename </code><sup>(node=None, name="", sel=False)</sup><br><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>hou.Node</code>  <b> node </b> : houdini node<br>
    <!--@param-->- <code>str</code>  <b> name </b> : target name to rename to<br>
    <!--@param-->- <code>bool</code>  <b> sel </b> : if query selected<br>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . 