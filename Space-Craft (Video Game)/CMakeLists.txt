cmake_minimum_required(VERSION 3.16)

# Project name and version
project(Space-Craft VERSION 1.0)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add source files
file(GLOB_RECURSE SOURCES src/*.cpp)

# Add executable
add_executable(SpaceCraft ${SOURCES})

# Include directories
target_include_directories(SpaceCraft PRIVATE include)

# Link libraries (if any)
# target_link_libraries(SpaceCraft PRIVATE some_library)