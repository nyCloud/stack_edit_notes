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
Too add a library, we can create a subdirectory containing the code for this library, say 'MathFunctions.h' and 'sqrt.cpp'. Then we will need to add a 'CMakeLists.txt' file under this subdirectory containing: 
```cpp
add_library(MathFunctions sqrt.cpp)
```

To make use of the new library we will add an add_subdirectory() call in the top-level 'CMakeLists.txt':
```cpp
if(US)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NjcwNTA2ODUsMTQ1NTc2NDc1Nl19
-->