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
if(USE_MYMATH)
	add_subdirectory(MathFunctions)
	list(APPEND EXTRA_LIBS MathFunctions)
	list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
endif()

add_executable(Tutorial tutorial.cpp)
target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}" ${EXTRA_INCLUDES})
target_link_libraries(Tutorial PUBLIC ${EXTRA_LIBS})
```

**target_include_directories**
Adding include directories to a target.
```cpp
target_include_directories(<target>  [SYSTEM]  [BEFORE]
						   <INTERFACE|PUBLIC|PRIVATE>  [items1...]
						  [<INTERFACE|PUBLIC|PRIVATE>  [items2...]  ...])
```
**target_link_libraries**
Specify libraries or flags to use when linking a given target and/or its dependents.
```cpp
target_link_libraries(<target>  ...  <item>...  ...)
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUxNTk5MTE2NSwtMTg5MzM3OTgyMiwtMT
E5NzUxNTQyMCwxNTI1NzIwOTY2LC0xODIyNDExNTIsMjM1OTM0
MDI4LDE0NTU3NjQ3NTZdfQ==
-->