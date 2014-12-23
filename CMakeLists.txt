cmake_minimum_required(VERSION 2.8.12.1)

###########################################################################
## Project Settings                                                      ##
## ----------------                                                      ##
## Can be changed across projects                                        ##
###########################################################################
# how the project and the build targets will be called
set(PROJECT_NAME "AzzuUtils")

# when false, this will add "src/Main.cpp" to the build and build an executable.
# otherwise, it will build a library
set(IS_LIBRARY true)
# set the type of the library, either STATIC or SHARED
set(LIBRARY_TYPE STATIC)

# will add the "test" subdirectory and "test/Main.cpp"
set(HAS_TESTS true)

# will add the lib/ directory to the build if true
set(HAS_LIBS true)
# define the names of the built libs to be added to the main target
set(LIBS )
# define the names of the built libs to be added to the test target
set(TEST_LIBS GTest GMock)

# will copy the resources/ folder to the installation directory
set(HAS_RESOURCES true)

# third party libs that will be added with find_package
set(THIRD_PARTY_PACKAGES SDL2)

# dynamic libraries that will be copied from the lib/ folder to the app directory
list(APPEND DYNAMIC_LIBRARIES)

# boost libraries
set(ADD_BOOST true)
set(BOOST_COMPONENTS)

# Settings necessary for individual computer configurations go in this file
include(CMake/user_defined_settings.cmake)

###########################################################################
## Build                                                                 ##
include(CMake/project_build.cmake)                                       ##
###########################################################################
