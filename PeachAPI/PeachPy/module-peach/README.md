# Module peach

## Sub-modules
- [peach.pBlender](./pBlender/README.md)
- [peach.pHoudini](./pHoudini/README.md)
- [peach.pQt](./pBlender/README.md)

## Topics
- [Module peach](#module-peach)
  - [Sub-modules](#sub-modules)
  - [Topics](#topics)
  - [1. peach.pDir](#1-peachpdir)
    - [1.0 Dependencies](#10-dependencies)
    - [1.1 Back-slash to Fore-slash](#11-back-slash-to-fore-slash)
    - [1.2 Extension removal](#12-extension-removal)
    - [1.3 os.path function encapsulation](#13-ospath-function-encapsulation)
    - [1.4 ls functions](#14-ls-functions)
    - [1.5 Peach Paths](#15-peach-paths)
  - [2. peach.pImp](#2-peachpimp)
    - [2.0 Dependencies](#20-dependencies)
    - [2.1 Reload Module Function](#21-reload-module-function)
  - [3. peach.pLog](#3-peachplog)
    - [3.0 Dependencies](#30-dependencies)
    - [3.1 Message, Debug and Warning](#31-message-debug-and-warning)
    - [3.2 Enable And Disable Debug Message](#32-enable-and-disable-debug-message)
    - [3.3 Error and Exception Throwing.](#33-error-and-exception-throwing)
  - [4. peach.pIco](#4-peachpico)
    - [4.0 Denpendencies](#40-denpendencies)
    - [4.1 Icon Path configuration](#41-icon-path-configuration)
    - [4.2 Icon Class](#42-icon-class)
      - [4.2.1 Constructor](#421-constructor)
      - [4.2.2 getPath, getName](#422-getpath-getname)
    - [4.3 IconTank Class](#43-icontank-class)
      - [4.3.1 Constructor](#431-constructor)
      - [4.3.2 Refresh Database](#432-refresh-database)
      - [4.3.3 getTypes, getNames, get](#433-gettypes-getnames-get)

<br><br>

## 1. peach.pDir
### 1.0 Dependencies
- `os`
- `peach.pLog` 
- `peach.pImp`

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
If you are familiar with Linux `ls` function, this is basically what it does: it lists all the directories or files under the given path. retunr `None` or `[]` if there isn't any.

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
    <!--@param-->- <code>str</code>  <b> path </b> : filepath to scan<br>
    <!--@param-->- <code>bool</code> <b> n </b> : true: return <i>names</i>; false: return <i>full path</i> 
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>list</code> of names/paths,"<code>None</code> if directory not found.
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
    peach.pDir.<code> getPeachDir() </code> 
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
    peach.pDir.<code> getPeachConfigsDir() </code>
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
    peach.pDir.<code> getPeachHouDir() </code> 
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
    peach.pDir.<code> getPeachBlnDir() </code>
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
    peach.pDir.<code> getPeachIconsDir() </code>
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


<br><br>

## 2. peach.pImp
### 2.0 Dependencies
- `sys`
- python version < 3.4 `imp`
- python version >= 3.4 `importlib`

### 2.1 Reload Module Function
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

<br><br>

## 3. peach.pLog
### 3.0 Dependencies
> python_version > 2.7


### 3.1 Message, Debug and Warning
These three are the most commently used function in this module, basically sending information to console, handy tools to inspect, debug functions, classes etc. The messages will formated in this format:

| >>> `[ <class>::<function>::<state> ]: <message>` <- console message format|
|----------------------------------------------------------------------------|

Example:
```
>>> [pLog::AddPoint::debugMsg]: Adding point at location (2.0, 2.0, 4.3)
>>> [IM::AddIcon::Warning]: The icon is not added, cannot find path /mnt/resource/icons/peach.png
>>> [pLog]: Just want to print something...
```


> key functions:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pLog.<code> message </code><sup>(*args, fn=None, cls=None, state="")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>Any</code>  <b> *args </b> : arguments of (Any), messages<br>
    <!--@param-->- <code>str/func</code> <b> fn </b> : can be function pointer or string<br>
    <!--@param-->- <code>str/self</code> <b> cls </b> : can be class instance or string<br>
    <!--@param-->- <code>str</code> <b> state </b> : custom state.
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pLog.<code> debug </code><sup>(*args, fn=None, cls=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>Any</code>  <b> *args </b> : arguments of (Any), messages<br>
    <!--@param-->- <code>str/func</code> <b> fn </b> : can be function pointer or string<br>
    <!--@param-->- <code>str/self</code> <b> cls </b> : can be class instance or string<br>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pLog.<code> warning </code><sup>(*args, fn=None, cls=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>Any</code>  <b> *args </b> : arguments of (Any), messages<br>
    <!--@param-->- <code>str/func</code> <b> fn </b> : can be function pointer or string<br>
    <!--@param-->- <code>str/self</code> <b> cls </b> : can be class instance or string<br>
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub> &uarr; `private` `args` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pLog.<code> _print </code><sup>(**kwargs)</sup><br><br>
    <blockquote>
    [ Internal Function ] <br>
    Other Logging Function Inplement this function internally.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

__Exmaples:__

1. Print Message
```python
from peach import pLog

pLog.message("I've got something")

# >>> [ pLog ]: I've got something
```

2. Multiple Messages
```python
pLog.message("I've", "got", "something")

# >>> [ pLog ]: I've 
# >>> [ pLog ]: got
# >>> [ pLog ]: something
```

3. Print String with Sender/Function name
```python
def Foo():
    pass

pLog.message("I've got something", fn=Foo)
# >>> [ pLog::Foo ]: I've got something

pLog.message("I've got something", fn=Foo, cls="Test")
# >>> [ Test::Foo ]: I've got something

pLog.warning("This is a warning", fn=Foo, cls="Test")
# >>> [ Test::Foo::Warning ]: This is a warning
```

4. Calling in side classes
```python
class MyClass(object):
    def __init__(self):
        pass
    def Foo(self, a=1, b=2):
        c = a + b
        pLog.debug("Value is: %d" % c, fn=self.Foo, cls=self)
        return c

mc = MyClass()
mc.Foo()

# >>> [ MyClass::Foo::debugMsg ]: Value is 3
```

<br><br>

### 3.2 Enable And Disable Debug Message
> global variables:
<!--///////////////////Variable-Table//////////////////////-->
- <sub>`private` `bool` `default`=True</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ Variable ] -->
    peach.pLog.<code> _enable_debug </code>
    </td></tr>
    <!-- ( /END OF Variable ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

> key function:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td>
    peach.pLog.<code> enable_debug_msg() </code>
    </td></tr>
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td>
    peach.pLog.<code> disable_debug_msg() </code>
    </td></tr>
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

```python
from peach import pLog

pLog.debug("something1")

# disable from here
pLog.disable_debug_msg()
pLog.debug("something2")

# enabled from here
pLog.enable_debug_msg()
pLog.debug("something3")

# >>> [ pLog::debugMsg ]: something1
# >>> [ pLog::debugMsg ]: something3
```

<br><br>

### 3.3 Error and Exception Throwing.

> key functions:
<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    peach.pLog.<code> error </code><sup>(msg, fn=None, cls=None, e=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> msg </b> : messages<br>
    <!--@param-->- <code>str/func</code> <b> fn </b> : can be function pointer or string<br>
    <!--@param-->- <code>str/self</code> <b> cls </b> : can be class instance or string<br>
    <!--@param-->- <code>Any</code> <b> e </b> : Error Object
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

__Examples__:

1. use it as the same as message:
```python
from peach import pLog

def Foo():
    pass

# this will not raise and stop. only print message
pLog.error("error here", fn=Foo)
```

2. throw specific errors:
```python
pLog.error("error here", fn=Foo, e=RuntimeError("lib open"))
```

3. put it in try-except block:
```python
try:
    import hou
except ImportError as e:
    pLog.error("Cannot Load <hou> Module", cls=__file__, fn="import", e=e)
finally:
    pLog.debug("<hou> Module Found", cls=__file__, fn="import")
```

<br><br>

## 4. peach.pIco
### 4.0 Denpendencies
- `peach.pImp`
- `peach.pDir`
- `peach.pLog`

### 4.1 Icon Path configuration
Even though `configure_icon_path()` is a public function, there's no need to call this function in other scripts. basically it calculate the icon path and store it in a global parameter of this module.

<br><br>

### 4.2 Icon Class
There's no need to handle this object by users manually. Icon object is a type, you can get this object from IconTank Object instance. Check section [4.3 IconTank Class](#43-icontank-class). Once you get the icon object, you can call `getPath` and `getName` to get the information you required.

<!--///////////////////Class-Table/////////////////////-->
<sub> Inherit &rarr; `object` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big>peach.pIco.<code> Icon </code><sup>class</sup><br></big>
    </td></tr> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

> member functions:
#### 4.2.1 Constructor
<!--///////////////////Function-Table/////////////////////-->
- <sub>`constructor` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> __init__ </code><sup>(self, name="", types=None)</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> : icon name<br>
    <!--@param-->- <code>list</code> or <code>str</code> <b> types </b> : i.g. "x25", "SVG" etc
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

#### 4.2.2 getPath, getName
<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> getPath </code><sup>(self, size="SVG")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> size </b> : i.g. "x25", "SVG" etc
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>list</code> or <code>None</code> filepath of the icon
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> getName() </code>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>str</code> name of this icon object
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<br><br>


### 4.3 IconTank Class


<!--///////////////////Class-Table/////////////////////-->
<sub> Inherit &rarr; `object` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big>peach.pIco.<code> IconTank </code><sup>class</sup><br></h4>
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
    IconTank.<code> __init__ </code><sup>(self, name="", types=None)</sup><br><br>
    <blockquote>
    When IconTank's constructor is called the first time, internally it will run function 
    <i>_construct_library</i>. it will construct/log in all the found icons by scanning the directory.This function will be only running once. unless refresh is called.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

#### 4.3.2 Refresh Database
<!--///////////////////Function-Table/////////////////////-->
- <sub>`member`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    IconTank.<code> refresh </code><sup>(self, name="", types=None)</sup><br><br>
    <blockquote>
    Clear Icon Database and rescan directory. and call <i>_construct_library</i>. it will construct/log in all the found icons, by scanning the directory.
    </blockquote>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


#### 4.3.3 getTypes, getNames, get
<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> getTypes() </code><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>list</code> icon types
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> getNames() </code><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>list</code> icon names
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->
<!--///////////////////Function-Table/////////////////////-->
- <sub>`getter` `args`</sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    Icon.<code> get </code><sup>(self, name="")</sup><br>
    </td></tr> 
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> : name of the icon
    </detials><dv>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code>Icon</code> <a href="#42-icon-class"> Icon Object</a>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

```python
from peach import pIco

im = pIco.IconTank()
peach_icon = im.get("peach")
picon_path = peach_icon.getPath("x25")
```