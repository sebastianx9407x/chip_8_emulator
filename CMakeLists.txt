cmake_minimum_required(VERSION 3.14)
project(chip_8)

set(CMAKE_CXX_STANDARD 11)

add_subdirectory(3rdParty/sdl-2.0.20 EXCLUDE_FROM_ALL)
add_subdirectory(3rdParty/imgui-1.88 EXCLUDE_FROM_ALL)

include_directories(3rdParty/sdl-2.0.20/include)
include_directories(3rdParty/imgui-1.88)

add_executable(
    chip_8
    Source/chip_8.cpp
    Source/main.cpp
    Source/platform.cpp
)

target_compile_options(chip_8 PRIVATE -Wall)

target_link_libraries(chip_8 PRIVATE SDL2::SDL2 ImGui::ImGui)