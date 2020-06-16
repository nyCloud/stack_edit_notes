# CMake Notes

```cpp
cmake_minimum_required(VERSION 3.10)

# Project name
project(Tutorial)
configure_file(TutorialCOnfig.h.in TutorialConfig.h)

# Add the executable
add_executable(Tutorial tutorial.cpp)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ1NTc2NDc1Nl19
-->