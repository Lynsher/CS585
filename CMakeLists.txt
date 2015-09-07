cmake_minimum_required (VERSION 2.6)
project (Game)
#The version number
set (Game_VERSION_MAJOR 1)
set (Game_VERSION_MINOR 0)

option(USE_MYOPERATION
       "Use game provided operations" ON)

if (USE_MYOPERATION)
  include_directories("${PROJECT_BINARY_DIR}/src")
  add_subdirectory(src)
  set (EXTRA_LIBS ${EXTRA_LIBS} src)
endif (USE_MYOPERATION)

add_executable(Game game.m.cpp)
target_link_libraries(Game ${EXTRA_LIBS})

