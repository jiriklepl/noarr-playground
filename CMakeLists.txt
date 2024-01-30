cmake_minimum_required(VERSION 3.15)

include(FetchContent)

project(NoarrPlayground
    VERSION 0.1.0
    DESCRIPTION "Noarr Playground"
    LANGUAGES CXX
)

# set the C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Fetch Noarr Structures
FetchContent_Declare(
    Noarr
    GIT_REPOSITORY https://github.com/jiriklepl/noarr-structures.git
    GIT_TAG        main
)
FetchContent_MakeAvailable(Noarr)

# include Noarr Structures
include_directories(${Noarr_SOURCE_DIR}/include)

add_executable(playground playground.cpp)
