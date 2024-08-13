cmake_minimum_required(VERSION 3.12)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

set(FETCHCONTENT_QUIET FALSE)
include(FetchContent)

FetchContent_Declare(pico_sdk
GIT_REPOSITORY https://github.com/raspberrypi/pico-sdk.git
GIT_TAG 6a7db34ff63345a7badec79ebea3aaef1712f374
GIT_SHALLOW TRUE
GIT_SUBMODULES_RECURSE FALSE
GIT_SUBMODULES lib/tinyusb
GIT_PROGRESS TRUE
)

FetchContent_MakeAvailable(pico_sdk)
include(${pico_sdk_SOURCE_DIR}/pico_sdk_init.cmake)
include(${pico_sdk_SOURCE_DIR}/tools/FindELF2UF2.cmake)

project(pico-jiggler
VERSION 1.1.0
HOMEPAGE_URL https://github.com/akhilharihar/pico-jiggler
LANGUAGES C CXX ASM)

# Initialize the SDK
pico_sdk_init()

add_subdirectory(jiggler)
