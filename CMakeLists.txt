cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(gameEngine VERSION 1.0)

find_package(SDL2 2 REQUIRED)
find_package(GLM 1 REQUIRED)
find_package(GLEW 2 REQUIRED)

file(GLOB_RECURSE SRC_FILES Sources/*.cpp Sources/*.c)
add_executable(gameEngine main.cpp ${SRC_FILES})
target_include_directories(gameEngine PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/Header ${SDL2_INCLUDE_DIR} ${GLM_INCLUDE_DIR} ${GLEW_INCLUDE_DIR})
target_link_libraries(gameEngine PUBLIC ${SDL2_LIBRARIES} ${SDL2_DEPENDENCIES} ${GLM_LIBRARIES} ${GLM_DEPENDENCIES} ${GLEW_LIBRARIES} ${GLEW_DEPENDENCIES})
target_link_libraries(gameEngine PUBLIC "-framework OpenGL")

