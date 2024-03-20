cmake_minimum_required(VERSION 3.12)

# Set the vcpkg toolchain file
set(CMAKE_TOOLCHAIN_FILE
    $ENV{HOME}/vcpkg/scripts/buildsystems/vcpkg.cmake
    CACHE STRING "Vcpkg toolchain file")

project(
  template
  VERSION 1.0
  LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Export compile commands for LSP
set(CMAKE_EXPORT_COMPILE_COMMANDS
    ON
    CACHE INTERNAL "")

find_package(GTest CONFIG REQUIRED)
find_package(SDL2 CONFIG REQUIRED)

add_compile_options(
  -Wall
  -Wextra
  -Wpedantic
  -Wno-shadow
  -Wnon-virtual-dtor
  -Wno-redundant-move
  -Wold-style-cast)

add_subdirectory(src)
