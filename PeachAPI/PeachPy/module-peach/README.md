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

> key function: `peach.pDir.pathSlashConvert(path="")`

```python
from peach import pDir
pDir.pathSlashConvert("C:\\your_path\\to_file.ext")

>>> "C:/your_path/to_file.ext"
```

### 1.2 Extension removal
> key function: `peach.pDir.remove_ext(file_name='')`

```python
from peach import pDir
pDir.remove_ext("your_file.ext")

>>> "your_file"
```

### 1.3 os.path function encapsulation 
Instead of import os module everywhere in the code, it is nice to wrap them up into some handy functions.

- `exists` works the same as _os.path.exists_
- `join` works the same as _os.path.join_
  
```python
from peach import pDir

pDir.join("your_path", "to", "file.ext")
>>> "your_path/to/file.ext"

pDir.exists("your_path")
>>> False
```

### 1.4 ls functions
> Key Functions: `ls`, `listdir`, `listfiles`
- Function Params and Returns: 
    - :electric_plug: `str` __path__  &larr; filepath to scan
    - :electric_plug: `bool` __n__  &larr; true: return _names_; false: return _full path_.
    
    &rarr; _return_: `list` of names/paths, `None` if directory not found.

```python
from peach import pDir

pDir.ls("your_path", n=False)
>>> ["Files", "Directories"]

pDir.listdir("your_path", n=False)
>>> ["Directories", ]

pDir.listfiles("your_path", n=False)
>>> ["Files", ]
```

### 1.5 Peach Paths
In order to get configure other modules, loading resources, etc, it is very handy to handle the path here.
> Key Function: `getPeachDir()`
> > :warning: this function will only search once in runtime when it is called, it's recursive search from the python module until it finds the root `${PEACH}` folder. After that, it will store the value in `_PEACH_DIR` file scope global variable.  


> Other Functions: 
> - `getPeachConfigsDir()`
>   - &rarr; _return_: `str` "__${peach}/config__"

> - `getPeachHouDir()`
>   - &rarr; _return_: `str` "__${peach}/pHoudini__"

> - `getPeachBlnDir()`
>   - &rarr; _return_: `str` "__${peach}/pBlender__"

> - `getPeachIconsDir()`
>   - &rarr; _return_: `str` "__${peach}/icons__"