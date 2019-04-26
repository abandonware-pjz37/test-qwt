cmake_minimum_required(VERSION 3.2)

option(HUNTER_STATUS_DEBUG "..." ON)
option(HUNTER_BUILD_SHARED_LIBS "..." ON)

set(HUNTER_CONFIGURATION_TYPES Release CACHE STRING "...")

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/f310ff5c5691f027db729b7d726d922df3edc007.zip"
    SHA1 "4ac3195dd3dbde8805a263c92e3c6857af48b95f"
    LOCAL
)

project(foo)

hunter_add_package(PNG)
find_package(PNG CONFIG REQUIRED)

hunter_add_package(Qwt)
find_package(Qwt CONFIG REQUIRED)

add_executable(foo foo.cpp)
target_link_libraries(foo PUBLIC Qwt::qwt)
