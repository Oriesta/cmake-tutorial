cmake_minimum_required(VERSION 3.10)

# set the project name
project(Tutorial VERSION 1.0)

# configure a header file to pass the version number to the source code
configure_file(TutorialConfig.h.in TutorialConfig.h)

# specify the c++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# add the executable
add_executable(Tutorial tutorial.cxx)

# the project configuration header file will be added to the binary tree
# therefore add the binary tree to the include search path
target_include_directories(Tutorial PUBLIC
                           "${PROJECT_BINARY_DIR}"
                          )