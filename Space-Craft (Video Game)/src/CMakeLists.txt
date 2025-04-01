cmake_minimum_required(VERSION 3.16)

# Project name and version
project(SpaceCraft VERSION 1.0)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add source files
file(GLOB_RECURSE SOURCES "src/*.cpp")

# Add executable
add_executable(SpaceCraft ${SOURCES})

# Include directories
target_include_directories(SpaceCraft PRIVATE ${CMAKE_SOURCE_DIR}/include)

# Find and link libraries (SDL3)
find_package(SDL3 REQUIRED)
if (SDL3_FOUND)
    target_include_directories(SpaceCraft PRIVATE ${SDL3_INCLUDE_DIRS})
    target_link_libraries(SpaceCraft PRIVATE SDL3::SDL3)
endif()

# Enable warnings
if (MSVC)
    target_compile_options(SpaceCraft PRIVATE /W4 /WX)
else()
    target_compile_options(SpaceCraft PRIVATE -Wall -Wextra -Werror)
endif()