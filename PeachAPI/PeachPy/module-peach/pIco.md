# peach.pIco

## Contents
- [peach.pIco](#peachpico)
  - [Contents](#contents)
  - [1. Denpendencies](#1-denpendencies)
  - [2. Icon Path configuration](#2-icon-path-configuration)
  - [3. Icon Class](#3-icon-class)
    - [3.1 Constructor](#31-constructor)
    - [3.2 getPath, getName](#32-getpath-getname)
  - [4. IconTank Class](#4-icontank-class)
    - [4.1 Constructor](#41-constructor)
    - [4.2 Refresh Database](#42-refresh-database)
    - [4.3 getTypes, getNames, get](#43-gettypes-getnames-get)
  - [5. Getting Houdini SVG Icons](#5-getting-houdini-svg-icons)
  - [6. Getting Images](#6-getting-images)
    - [6.1 Getting "Peach Brand" Specific Images:](#61-getting-peach-brand-specific-images)

## 1. Denpendencies
- `peach.pImp`
- `peach.pDir`
- `peach.pLog`

## 2. Icon Path configuration
Even though `configure_icon_path()` is a public function, there's no need to call this function in other scripts. basically it calculate the icon path and store it in a global parameter of this module.

<br><br>

## 3. Icon Class
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
### 3.1 Constructor
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

### 3.2 getPath, getName
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


## 4. IconTank Class


<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `object` </sub> <!--{ `TAGS` }-->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big>peach.pIco.<code> IconTank </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


> member functions:
### 4.1 Constructor
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

### 4.2 Refresh Database
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


### 4.3 getTypes, getNames, get
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
- <sub>`pub` `member`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> printTypes </code><sup>(self)</sup><br><br>
    <blockquote>[ IconTank ] Debug Function</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `member`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> printNames </code><sup>(self)</sup><br><br>
    <blockquote>[ IconTank ] Debug Function</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
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
    <!-- . . . . . . . . . . . . . . . . . . . . . . . . -->

```python
from peach import pIco

im = pIco.IconTank()
peach_icon = im.get("peach")
picon_path = peach_icon.getPath("x25")
```

<br><br>

----

## 5. Getting Houdini SVG Icons


<!--///////////////////Function-Table/////////////////////-->
- <sub>`pub` `args` `return`</sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ FUNCTIONS ] -->
    <sup>peach.</sup> pDir.<code> getHouIcon </code><sup>(name="")</sup><br><br>
    <blockquote>[ Get Houdini Icon ] Icon Name (usually match with HDA Name)</blockquote>
    <!-- ( /END OF FUNCTIONS ) -->
    <tr><td> <!-- [ PARAMETER INPUTS ] -->
    <details> 
    <summary><i>parameters</i>: </summary>
    <!--@param-->- <code>str</code>  <b> name </b> :  icon name<br>
    </detials>
    </td></tr> 
    <!-- ( /END OF PARM ) -->
    <tr><td> <!-- [ RETURN VALUES ] -->
    <details> 
    <summary><i>return</i>: </summary>
    <!--@return-->&rarr; <code> str</code> filepath
    </detials> 
    </td></tr>
    <!-- ( /END OF RETURN ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


__Example__

```python

from peach import pIco

pIco.getHouIcon("sop_peachM_railing")

# >>> result# "peach_dir/icons/HICON/sop_peachM_railing.svg" 

```

<br><br>

----

## 6. Getting Images

### 6.1 Getting "Peach Brand" Specific Images:

__[ Based Template Class ]__

<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `object` </sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.</sup> pIco.<code> _DP0IcXTemplate </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


__User Callable Classes__

1.  `Digital Peach Brand` Icon: (`DP` Class)
<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `_DP0IcXTemplate` </sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.</sup> pIco.<code> DP </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->

<br>

2. `Digital Peach Studio` Brand Icon: (`DP` Class)
<!--///////////////////Class-Table/////////////////////-->
<sub>Inherit &rarr; `_DP0IcXTemplate` </sub> <!-- `TAGS` -->
    <table>
    <tr><td> <!-- [ CLASS ] -->
    <big><sup>peach.</sup> pIco.<code> DPS </code><sup>class</sup><br></h4>
    </td></big> 
    <!-- ( /END OF CLASS ) -->
    </table>
    <!-- . . . . . . . . . . . . . . . . . . . . . . . .  -->


Functions:
> - < class >. `blackSVG()`
> - < class >. `black256()`
> - < class >. `black512()`
> - < class >. `whiteSVG()`
> - < class >. `white256()`
> - < class >. `white512()`
> - < class >. `blackTextAndStrokeColorIcoSVG()`
> - < class >. `blackTextAndStrokeColorIco256()`
> - < class >. `blackTextAndStrokeColorIco512()`
> - < class >. `blackTextColorIcoSVG()`
> - < class >. `blackTextColorIco256()`
> - < class >. `blackTextColorIco512()`
> - < class >. `whiteTextColorIcoSVG()`
> - < class >. `whiteTextColorIco256()`
> - < class >. `whiteTextColorIco512()`