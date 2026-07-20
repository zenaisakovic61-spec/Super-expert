cmake_minimum_required(VERSION 3.24)

project(SuperExpert VERSION 1.0.0 LANGUAGES CXX)

if(WIN32)
    set(GEODE_SDK_PATH "C:/Users/runneradmin/AppData/Local/Geode/sdk")
else()
    set(GEODE_SDK_PATH "/home/runner/.local/share/Geode/sdk")
endif()

add_library(${PROJECT_NAME} SHARED src/main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE "${GEODE_SDK_PATH}/include")

if(NOT DEFINED GEODE_MOD_ID)
    set(GEODE_MOD_ID "zenaisakovic61-spec.super_expert")
endif()

target_compile_definitions(${PROJECT_NAME} PRIVATE GEODE_MOD_ID="${GEODE_MOD_ID}")
