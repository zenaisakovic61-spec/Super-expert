cmake_minimum_required(VERSION 3.24)

project(SuperExpert VERSION 1.0.0 LANGUAGES CXX)

find_package(Geode REQUIRED)

add_geode_mod(
    ID "zenaisakovic61-spec.super_expert"
    NAME "Super Expert"
    DEVELOPER "zenaisakovic61-spec"
    DESCRIPTION "Super Expert mod for Geometry Dash"
    VERSION "1.0.0"
)

target_sources(${PROJECT_NAME} PRIVATE src/main.cpp)

