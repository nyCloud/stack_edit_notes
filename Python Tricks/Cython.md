# Cython

## 1. Intro
Cython is Python with C data types.

### 1.1 Basic Usage
To build a Cython *.pyx file into importable *.so file. We can use following script.

```python
from distutils.core import setup
from Cython.Build import cythonize

setup(
    ext_modules = cythonize("helloworld.pyx", 
					        annotate=False)
    # More info at:
    # https://cython.readthedocs.io/en/latest/src/userguide/source_files_and_compilation.html
)
```

Then call
```
$ python setup.py build_ext
```

## 2. Cython Syntax

### 2.1 Types
#### Basic Types
`char` : 8-bit signed integer
`short`: 16-bit signed integer
`int`: 32-bit signed integer
`long`: 64-bit signed integer
`long : long`64-bit signed integer
`float`: 32-bit floating point
`double`: 64-bit floating point
`long double`: 80-bit floating point
#### Array
`type name[size]`:  An array with specific size
#### Pointer
`type *name`: a C pointer with given type
#### Structure
`struct name { declaration}: a C`structure
```c
cdef struct Student:
	int age
	char *name
```

#### cdef & ctypedef
cdef is used to declear a new variable like `cdef int a`
ctypedef is used to declare a type like `ctypedef int* IntPtr`
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQzNTg1NTg3LDE3ODMyMTgzODMsNjQ0Mz
Y0MDMxLC0xNDI0ODEzMjAwLDM1NjM1OTYzNCwtMTcwNzQ5MDk0
NywxOTIxNzEwMDM5XX0=
-->