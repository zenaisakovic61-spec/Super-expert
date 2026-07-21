cmake_minimum_required(VERSION 3.24)

project(SuperExpert VERSION 1.0.0 LANGUAGES CXX)

set(GEODE_SDK_ROOT "$ENV{GEODE_SDK}")

if(NOT GEODE_SDK_ROOT AND DEFINED GEODE_SDK)
    set(GEODE_SDK_ROOT "${GEODE_SDK}")
endif()

if(GEODE_SDK_ROOT)
    list(APPEND CMAKE_PREFIX_PATH "${GEODE_SDK_ROOT}")
    include("${GEODE_SDK_ROOT}/share/Geode/cmake/GeodeConfig.cmake" OPTIONAL)
    include("${GEODE_SDK_ROOT}/cmake/GeodeConfig.cmake" OPTIONAL)
endif()

add_library(${PROJECT_NAME} SHARED src/main.cpp)

if(GEODE_SDK_ROOT)
    target_include_directories(${PROJECT_NAME} PRIVATE "${GEODE_SDK_ROOT}/include")
endif()

if(NOT DEFINED GEODE_MOD_ID)
    set(GEODE_MOD_ID "zenaisakovic61-spec.super_expert")
endif()

target_compile_definitions(${PROJECT_NAME} PRIVATE GEODE_MOD_ID="${GEODE_MOD_ID}")
