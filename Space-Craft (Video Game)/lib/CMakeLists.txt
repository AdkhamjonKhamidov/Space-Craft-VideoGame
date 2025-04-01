# Minimum CMake version required
cmake_minimum_required(VERSION 3.15)

# Project name and version
project(SpaceCraftLib VERSION 1.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add source files
set(SOURCE_FILES
    src/SpaceCraft.cpp
    src/PhysicsEngine.cpp
    src/GraphicsEngine.cpp
)

# Add header files
set(HEADER_FILES
    include/SpaceCraft.h
    include/PhysicsEngine.h
    include/GraphicsEngine.h
)

# Create the library
add_library(SpaceCraftLib ${SOURCE_FILES} ${HEADER_FILES})

# Include directories
target_include_directories(SpaceCraftLib PUBLIC include)

# Find SDL3 package
find_package(SDL3 REQUIRED)

# Link SDL3 to the library
target_link_libraries(SpaceCraftLib PUBLIC SDL3::SDL3)