cmake_minimum_required(VERSION 3.24)

project(SuperExpert VERSION 1.0.0 LANGUAGES CXX)

if(WIN32)
    file(GLOB_RECURSE GEODE_CONFIG_FILES "C:/Users/runneradmin/*GeodeConfig.cmake")
else()
    file(GLOB_RECURSE GEODE_CONFIG_FILES "/home/runner/*GeodeConfig.cmake")
endif()

if(GEODE_CONFIG_FILES)
    list(GET GEODE_CONFIG_FILES 0 FIRST_MATCH)
    get_filename_component(GEODE_DIR_FOUND "${FIRST_MATCH}" DIRECTORY)
    get_filename_component(GEODE_SDK_ROOT "${GEODE_DIR_FOUND}/../../.." ABSOLUTE)
    set(Geode_DIR "${GEODE_DIR_FOUND}")
    set(ENV{GEODE_SDK} "${GEODE_SDK_ROOT}")
endif()

find_package(Geode REQUIRED)

add_geode_mod(
    ID "zenaisakovic61-spec.super_expert"
    NAME "Super Expert"
    DEVELOPER "zenaisakovic61-spec"
    DESCRIPTION "Super Expert mod for Geometry Dash"
    VERSION "1.0.0"
)

target_sources(${PROJECT_NAME} PRIVATE src/main.cpp)
