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
target_link_libraries(Tutorial PUBLIC ${EXTRA_LIBS})
target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}" ${EXTRA_INCLUDES})
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

## 3. Adding Usage Requirements for Library

```cpp
add_library(MathFunctions sqrt.cpp)
target_include_directories(MathFunctions INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
```
```cpp
if(USE_MYMATH)
	add_subdirectory(MathFunctions)
	list(APPEND EXTRA_LIBS MathFunctions)
	# There is  no need to add extra includes if target include directories is added in the library
	# list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
endif()

add_executable(Tutorial tutorial.cpp)
target_link_libraries(Tutorial PUBLIC ${EXTRA_LIBS})
# target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}" ${EXTRA_INCLUDES})
```

## 4. Installing and Testing
For install the library and the header file, we can simply add:
```cpp
install(TARGETS MathFunctions DESTINATION lib)
install(FILES MathFunctions.h DESTINATION include)
```
and
```cpp
install(TARGETS Tutorial DESTINATION bin)
install(FILES "${PROJECT_BINARY_DIR/TutorialConfig.h}" DESTINATION include)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg2MDEwNTIwNSwyMTM0ODE1MTU5LDk5ND
U3OTAxOCwxNTE1OTkxMTY1LC0xODkzMzc5ODIyLC0xMTk3NTE1
NDIwLDE1MjU3MjA5NjYsLTE4MjI0MTE1MiwyMzU5MzQwMjgsMT
Q1NTc2NDc1Nl19
-->