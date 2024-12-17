## 变量

#### 设置c/c++ 标准

``` cmake
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF) # We use -std=c++17 instead of -std=gnu++17 in macOS
set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
```

#### C/C++ 编译符号

``` cmake
CMAKE_CXX_FLAGS
CMAKE_C_FLAGS
CMAKE_EXE_LINKER_FLAGS
CMAKE_MODULE_LINKER_FLAGS
```

#### 构建类型

``` cmake
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE RelWithDebInfo CACHE STRING
      "Choose the type of build, options are:
        None Debug Release RelWithDebInfo Profile."
      FORCE)
endif()
```

## 检查

#### 检查文件是否存在

``` cmake
if(NOT EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/laf/CMakeLists.txt)
  message(FATAL_ERROR "Your Aseprite repository is incomplete, initialize submodules using:\n  git submodule update --init --recursive")
endif()
```

#### Qt

``` cmake
find_package(Qt5 COMPONENTS )
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set_target_properties(main PROPERTIES AUTOUIC_SEARCH_PATH ./form)
``` 

## Basic

``` cmake
# 收集.cpp 文件
aux_source_directories(./src SRC)
```

``` cmake
add_executable(main main.cpp)
target_include_directories(main ./include)
target_link_directories(main ./link)
target_link_libraries(main tools)
```


#### ASAN

#### Ctest
``` cmake
enable_testint()
add_executable(mytest test.cpp)
add_test(NAME MyTest COMMAND mytest)
```