cmake_minimum_required(VERSION 3.2)

option(HUNTER_STATUS_DEBUG "..." ON)
set(HUNTER_CONFIGURATION_TYPES Release CACHE STRING "...")

include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.23.163.tar.gz"
    SHA1 "e4a6bc5a951806f285bb7e09f845a600f7285193"
)

project(foo)

hunter_add_package(PNG)
find_package(PNG CONFIG REQUIRED)

hunter_add_package(Qwt)
find_package(Qwt CONFIG REQUIRED)

add_executable(foo foo.cpp)
target_link_libraries(foo PUBLIC Qwt::qwt PNG::png)
