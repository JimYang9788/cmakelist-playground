cmake_minimum_required (VERSION 3.10)

project (Tutorial)

add_executable(Tutorial tutorial.m.cpp)

add_subdirectory(MathStuff) 

target_link_libraries(Tutorial PUBLIC MathStuff)


# add the binary tree to the search path for include files
# so that we will find TutorialConfig.h
target_include_directories(Tutorial PUBLIC
                          "${PROJECT_BINARY_DIR}"
                          "${PROJECT_SOURCE_DIR}/MathStuff"
                          )

# C++version config
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)