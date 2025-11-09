cmake_minimum_required(VERSION 3.11)
project(3drenderer C)

set(CMAKE_C_STANDARD 99)

include(FetchContent)
FetchContent_Declare(
    SDL2
    GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
    GIT_TAG release-2.32.8
)
set(SDL_SHARED OFF CACHE BOOL "" FORCE)
set(SDL_STATIC ON CACHE BOOL "" FORCE)
set(SDL_TEST OFF CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(SDL2)

add_executable(3drenderer src/main.c)
target_link_libraries(3drenderer PRIVATE SDL2::SDL2main SDL2::SDL2-static)

