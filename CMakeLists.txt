cmake_minimum_required(VERSION 3.25)

project(SuperExpertMod VERSION 1.0.5 LANGUAGES CXX)

find_package(Geode REQUIRED)

add_geode_mod(
    xanii.super_expert
    VERSION 1.0.5
    SOURCES src/main.cpp
)
