cmake_minimum_required(VERSION 3.25)
project(uin-campus LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(uincampus_core
    src/version.cpp
    src/regles.cpp
    src/saisie.cpp)
target_include_directories(uincampus_core PUBLIC include)
target_compile_options(uincampus_core PRIVATE -Wall -Wextra -Wpedantic)

add_executable(uin-campus app/main.cpp)
target_link_libraries(uin-campus PRIVATE uincampus_core)
target_compile_options(uin-campus PRIVATE -Wall -Wextra -Wpedantic)
