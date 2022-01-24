# peach.pLog

## Contents
- [peach.pLog](#peachplog)
  - [Contents](#contents)
  - [1. Dependencies](#1-dependencies)
  - [2. Message, Debug and Warning](#2-message-debug-and-warning)
  - [3. Enable And Disable Debug Message](#3-enable-and-disable-debug-message)
  - [4. Error and Exception Throwing.](#4-error-and-exception-throwing)


## 1. Dependencies
> python_version > 2.7


## 2. Message, Debug and Warning
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

## 3. Enable And Disable Debug Message
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

## 4. Error and Exception Throwing.

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