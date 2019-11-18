# Cython

## 1. Intro
Cython is Python with C data types.

### 1.1 Basic Usage
To build a Cython *.pyx file into importable *.so file. We can use following script.

```python
from distutils.core import setup
from Cython.Build import cythonize

setup(
    ext_modules = cythonize("helloworld.pyx")
)
```

Then call
```
$ python setup.py build_ext
```

## 2. Cython Syntax

### 2.1 Types



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MjQ4MTMyMDAsMzU2MzU5NjM0LC0xNz
A3NDkwOTQ3LDE5MjE3MTAwMzldfQ==
-->