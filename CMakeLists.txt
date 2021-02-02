cmake_minimum_required(VERSION 3.13)

project(vl53l1x-st-core)

set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)

add_library(vl53l1x-st-core STATIC)

target_sources(vl53l1x-st-core PRIVATE
    en.STSW-IMG007/api/core/vl53l1_api.c
    en.STSW-IMG007/api/core/vl53l1_api_calibration.c
    en.STSW-IMG007/api/core/vl53l1_api_core.c
    en.STSW-IMG007/api/core/vl53l1_api_debug.c
    en.STSW-IMG007/api/core/vl53l1_api_preset_modes.c
    en.STSW-IMG007/api/core/vl53l1_api_strings.c
    en.STSW-IMG007/api/core/vl53l1_core.c
    en.STSW-IMG007/api/core/vl53l1_core_support.c
    en.STSW-IMG007/api/core/vl53l1_error_strings.c
    en.STSW-IMG007/api/core/vl53l1_register_funcs.c
    en.STSW-IMG007/api/core/vl53l1_silicon_core.c
    en.STSW-IMG007/api/core/vl53l1_wait.c
    en.STSW-IMG007/api/platform/vl53l1_platform.c)

target_include_directories(vl53l1x-st-core
    PUBLIC en.STSW-IMG007/api/core
    PUBLIC en.STSW-IMG007/api/platform)

add_library(vl53l1x-base STATIC)
target_sources(vl53l1x-base PRIVATE
    Src/vl53l1x_base.cpp)
target_include_directories(vl53l1x-base PUBLIC Inc)
target_link_libraries(vl53l1x-base PUBLIC vl53l1x-st-core)


