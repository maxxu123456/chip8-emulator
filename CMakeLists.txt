cmake_minimum_required(VERSION 3.24)
project(chip8)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(external/SDL)

add_executable(
    chip8
    src/Chip8.cpp
    src/Main.cpp
    src/Platform.cpp
)

target_compile_options(chip8 PRIVATE -Wall)

target_include_directories(${PROJECT_NAME} PRIVATE 
    src                    
    external/SDL/include 
)

target_link_libraries(${PROJECT_NAME} PRIVATE 
    SDL2::SDL2
    glad
)
