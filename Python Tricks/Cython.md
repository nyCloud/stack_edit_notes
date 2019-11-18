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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MDc0OTA5NDcsMTkyMTcxMDAzOV19
-->