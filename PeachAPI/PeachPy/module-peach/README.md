# Module peach

## Topics
- [Module peach](#module-peach)
  - [Topics](#topics)
  - [Sub-modules](#sub-modules)
  - [1. peach.pDir](#1-peachpdir)
    - [1.1 Back-slash to Fore-slash](#11-back-slash-to-fore-slash)
    - [1.2 Extension removal](#12-extension-removal)
    - [1.3 os.path function encapsulation](#13-ospath-function-encapsulation)
    - [1.4 ls functions](#14-ls-functions)
    - [1.5 Peach Paths](#15-peach-paths)

## Sub-modules
- [peach.pBlender](./pBlender/README.md)
- [peach.pHoudini](./pHoudini/README.md)
- [peach.pQt](./pBlender/README.md)


## 1. peach.pDir
### 1.1 Back-slash to Fore-slash
In order to work nicely with Houdini on Window Machines, all the file path should be formatted with `/`. Here's a simple function does it:

> key function:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td>
    peach.pDir.<code> pathSlashConvert </code> <sup>(path="")</sup> 
    </td></tr>
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

```python
from peach import pDir
pDir.pathSlashConvert("C:\\your_path\\to_file.ext")

>>> "C:/your_path/to_file.ext"
```

<br><br>
### 1.2 Extension removal

> key function:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> 
    peach.pDir.<code> remove_ext </code> <sup> (file_name='') </sup> 
    </td></tr>
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

```python
from peach import pDir
pDir.remove_ext("your_file.ext")

>>> "your_file"
```

<br><br>
### 1.3 os.path function encapsulation 
Instead of import os module everywhere in the code, it is nice to wrap them up into some handy functions.

> key function: (works the same as os.path.exists )
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> exists </code> <sup> (path) </sup> 
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

> key function: (works the same as os.path.join )
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> join </code> <sup> (*args) </sup> 
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

```python
from peach import pDir

pDir.join("your_path", "to", "file.ext")
>>> "your_path/to/file.ext"

pDir.exists("your_path")
>>> False
```

<br><br>
### 1.4 ls functions

> key functions:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> ls </code><sup>(path="", n=False)</sup>,<br>
    peach.pDir.<code> listdir </code></code><sup>(path="", n=False)</sup>,<br>
    peach.pDir.<code> listfiles </code></code><sup>(path="", n=False)</sup>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    - <code>str</code>  <b> path </b> : filepath to scan<br>
    - <code>bool</code> <b> n </b> : true: return <i>names</i>; false: return <i>full path</i> 
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    - &rarr; <code>list</code> of names/paths,"<code>None</code> if directory not found.
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


```python
from peach import pDir

pDir.ls("your_path", n=False)
>>> ["Files", "Directories"]

pDir.listdir("your_path", n=False)
>>> ["Directories", ]

pDir.listfiles("your_path", n=False)
>>> ["Files", ]
```


<br><br>
### 1.5 Peach Paths
In order to get configure other modules, loading resources, etc, it is very handy to handle the path here.

> key function:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> getPeachDir </code> 
    <br><br>
    <blockquote> - Note: this function will only search once in runtime when it is called, it's recursive search from the python module until it finds the root <code>${PEACH}</code> folder. After that, it will store the value in <code>_PEACH_DIR</code> file scope global variable.</blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    &rarr; <code>str</code> "<b>${peach}/</b>"
    </detials>
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


> other Functions: 

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> getPeachConfigsDir </code>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> <summary><i>return</i>: </summary>
    &rarr; <code>str</code> "<b>${peach}/config</b>"
    </detials>
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> getPeachHouDir </code> 
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> <summary><i>return</i>: </summary>
    &rarr; <code>str</code> "<b>${peach}/pHoudini</b>"
    </detials>
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> getPeachBlnDir </code>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> <summary><i>return</i>: </summary>
    &rarr; <code>str</code> "<b>${peach}/pBlender</b>"
    </detials>
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `return`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pDir.<code> getPeachIconsDir </code>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    &rarr; <code>str</code> "<b>${peach}/icons</b>"
    </detials>
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
