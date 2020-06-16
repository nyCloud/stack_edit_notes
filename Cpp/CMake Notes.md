# CMake Notes
## 1. A Basic Starting Point 
```cpp
cmake_minimum_required(VERSION 3.10)

# Project name
project(Tutorial)

# Specify Cpp standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the executable
add_executable(Tutorial tutorial.cpp)
```

## 2. Adding a Library
Too add a library, we can create a subdirectory containing  code for this library. 
```cpp


```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ1MjY5MDAyMSwxNDU1NzY0NzU2XX0=
-->