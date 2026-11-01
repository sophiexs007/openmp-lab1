cmake_minimum_required(VERSION 3.28)

project(OpenMP_lab1 LANGUAGES CXX)

if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release CACHE STRING "Build type: Release Debug" FORCE)
endif()

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_SCAN_FOR_MODULES OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(main apps/main.cpp)

message(STATUS "")
message("Build type: ${CMAKE_BUILD_TYPE}")
find_package(OpenMP REQUIRED)
target_compile_options(main PRIVATE -Wall -Wextra)
target_link_libraries(main PRIVATE OpenMP::OpenMP_CXX) 
