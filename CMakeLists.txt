cmake_minimum_required(VERSION 3.20)

project(Openlang LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(Openlang
    src/main.cpp
    src/lexer/lexer.cpp
)

set_target_properties(Openlang PROPERTIES
    COMPILE_WARNING_AS_ERROR ON
)

target_include_directories(Openlang PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)