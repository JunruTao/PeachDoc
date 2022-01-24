# peach.pImp

## Contents
- [peach.pImp](#peachpimp)
  - [Contents](#contents)
  - [1. Dependencies](#1-dependencies)
  - [2. Reload Module Function](#2-reload-module-function)
  

## 1. Dependencies
- `sys`
- python version < 3.4 `imp`
- python version >= 3.4 `importlib`

## 2. Reload Module Function
In order to reload function in runtime for testing, debug purposes, it is very handy to wrap the `reload` functions in one place in order to make scripts more robostic in python 2 and 3. At the same time, allowing one reload function to reload multiple modules.

> global variables:
<!--///////////////////Variable-Table/////////////////////-->
- <sub>`global` `bool` `default`=True</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ Variable ] -->
    peach.pImp.<code> ALLOW_MODULE_RUNTIME_RELOAD </code>
    </td></tr>
    <!-- ( /END OF Variable ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

> key function:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pImp.<code> reload </code><sup>(*args, force=False)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>modules</code>  <b> *args </b> : Modules to reload<br>
    <!--@param-->- <code>bool</code> <b> force </b> : true then force reloading, even if <i>ALLOW_MODULE_RUNTIME_RELOAD</i> is set to <i>False</i>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


```python
from peach import pImp
from peach import pDir
from peach import pIco
from peach import pLog

# reload modules to test.
pImp.reload(pDir, pIco, pLog)

# once this is set, modules will not be reloaded.
pImp.ALLOW_MODULE_RUNTIME_RELOAD = False
pImp.reload(pDir, pIco, pLog)
```
