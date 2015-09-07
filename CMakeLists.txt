cmake_minimum_required (VERSION 2.6)
project (Game)

set (Tutorial_VERSION_MAJOR 1)
set (Tutorial_VERSION_MINOR 0)
set(CMAKE_C_FLAGS "-Wall -g")

option(USE_MYMATH "Use tutorial provided math implementation" ON)

if (USE_MYMATH)
  include_directories ("${PROJECT_SOURCE_DIR}/src")
  add_subdirectory (src)
  set (EXTRA_LIBS ${EXTRA_LIBS} src)
endif (USE_MYMATH)

add_executable (Game game.m.cpp)
target_link_libraries (Game ${EXTRA_LIBS})
