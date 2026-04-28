cmake_minimum_required(VERSION 3.20.0)

# Add the project root as a board root so Zephyr can find local boards under ../boards
list(APPEND BOARD_ROOT ${CMAKE_CURRENT_LIST_DIR}/..)

# Load a local board alias file so -b our_board resolves to our_board/mcxn947/cpu0
set(ZEPHYR_BOARD_ALIASES "${CMAKE_CURRENT_SOURCE_DIR}/board_aliases.cmake" CACHE STRING "Zephyr board aliases")

find_package(Zephyr REQUIRED)
project(my_zephyr_app)

target_sources(app PRIVATE src/main.cpp)
