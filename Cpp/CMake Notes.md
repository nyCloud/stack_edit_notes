# CMake Notes

```cpp
cmake_minimum_required(VERSION 3.10)

# Project name
project(Tutorial VERSION 1.0)
configure_file(TutorialCOnfig.h.in TutorialConfig.h)

# Add the executable
add_executable(Tutorial tutorial.cpp)
target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}")
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4MzExMjY1MF19
-->