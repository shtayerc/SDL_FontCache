cmake_minimum_required(VERSION 3.1)
project(SDL_FontCache VERSION 0.10.0 LANGUAGES C)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_library(SDL_FontCache
    SDL_FontCache.h
    SDL_FontCache.c
)
add_library(SDL_FontCache::SDL_FontCache ALIAS SDL_FontCache)

target_include_directories(
  SDL_FontCache
  INTERFACE $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>)

target_link_libraries(SDL_FontCache PUBLIC 
    SDL3::SDL3 
    SDL3_ttf::SDL3_ttf)