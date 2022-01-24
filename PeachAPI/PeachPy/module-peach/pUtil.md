# peach.pUtil

Anything else that commonly used to convert, do math, naming parsing, etc. Should be included in this module

# Contents
- [peach.pUtil](#peachputil)
- [Contents](#contents)
  - [1. Dependencies](#1-dependencies)
  - [2. Color Casting](#2-color-casting)


## 1. Dependencies
- `None`

## 2. Color Casting

<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pUtil.<code> fRGB </code><sup>(*args)</sup><br><br>
    <blockquote>
    From given arguments cast to RGB tuple, if one value is give, color will be grayscale
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>float</code>  <b> args </b> :  color values<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> tuple of 3 floats</code>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pUtil.<code> fRGBA </code><sup>(*args)</sup><br><br>
    <blockquote>
    From given arguments cast to RGBA tuple, if one value is give, color will be grayscale
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>float</code>  <b> args </b> :  color values<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> tuple of 4 floats</code>
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->



<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pUtil.<code> sRGB </code><sup>(*args)</sup><br><br>
    <blockquote>
    From given arguments cast to RGB tuple
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>float</code>  <b> args </b> :  color values Any<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> tuple of 3 ints</code> 0-255 int8
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->



<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pUtil.<code> sRGBA </code><sup>(*args)</sup><br><br>
    <blockquote>
    From given arguments cast to RGB tuple
    </blockquote>
    </td></tr>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>float</code>  <b> args </b> :  color values Any<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> tuple of 3 ints</code> 0-255 int8
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

__Examples__

```python
from peach import pUtil

# [normalized float RGB]
pUtil.fRGB(0.5)
# >>> (0.5, 0.5, 0.5)

pUtil.fRGB(0.3, 0.3)
# >>> (0.5, 0.5, 0)

pUtil.fRGB(0.3, 255, 255)
# >>> (0.5, 1, 1)

# [8bit int RGB]
pUtil.sRGB(1, 0, 0)
# >>> (1, 0, 0)

pUtil.sRGB(1.0, 0, 0)
# >>> (255, 0, 0)

pUtil.sRBG(0.4, 100, 100)
# >>> (102, 100, 100)

```