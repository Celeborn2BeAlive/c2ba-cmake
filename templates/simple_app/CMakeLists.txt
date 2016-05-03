cmake_minimum_required(VERSION 2.8)

project(simple_app)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

file(
    GLOB_RECURSE
    SRC_FILES
    src/*.cpp src/*.hpp
)

add_executable(
    simple_app
    ${SRC_FILES}
)

target_include_directories(
    simple_app
    PUBLIC
    third-party/include
)

install(
    TARGETS simple_app
    DESTINATION bin
)