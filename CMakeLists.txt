cmake_minimum_required(VERSION 3.24)

project(SuperExpert VERSION 1.0.0 LANGUAGES CXX)

find_package(geode REQUIRED)

add_geode_mod(
    ID "yourname.super_expert"
    NAME "Super Expert"
    DEVELOPER "YourName"
    DESCRIPTION "Super Expert mod for Geometry Dash"
    VERSION "1.0.0"
)

target_sources(${PROJECT_NAME} PRIVATE src/main.cpp)

