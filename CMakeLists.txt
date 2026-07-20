cmake_minimum_required(VERSION 3.24)

set(GEODE_SDK_WINDOWS "C:/Users/runneradmin/AppData/Local/Geode/sdk")
set(GEODE_SDK_LINUX "/home/runner/.local/share/Geode/sdk")
if(WIN32)
    set(Geode_DIR "${GEODE_SDK_WINDOWS}")
    set(ENV{GEODE_SDK} "${GEODE_SDK_WINDOWS}")
else()
    set(Geode_DIR "${GEODE_SDK_LINUX}")
    set(ENV{GEODE_SDK} "${GEODE_SDK_LINUX}")
endif()

project(SuperExpert)

find_package(Geode REQUIRED)
