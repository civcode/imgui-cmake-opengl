cmake_minimum_required(VERSION 2.8)

project(imgui-01)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED CONFIG)

message(STATUS "Source dir: ${PROJECT_SOURCE_DIR}")
message(STATUS "CMake Source dir: ${CMAKE_SOURCE_DIR}")

file(GLOB imgui-01_SRC
    ${PROJECT_SOURCE_DIR}/imgui/*.h
    ${PROJECT_SOURCE_DIR}/imgui/*.cpp
)

include_directories(
    ${PROJECT_SOURCE_DIR}/imgui
)

set(SOURCES 
    #${PROJECT_SOURCE_DIR}/imgui/imgui.cpp 
    #${PROJECT_SOURCE_DIR}/imgui/imgui.h
    ${imgui-01_SRC}
)
message(STATUS	"glob: ${imgui-01_SRC}")
message(STATUS	"glob: ${SOURCES}")

#add_executable(imgui-01 ${SOURCES} ${imgui-01_SRC})
add_executable(imgui-01 src/main.cpp ${SOURCES} )

target_link_libraries(imgui-01 ${OPENGL_LIBRARIES} glfw)

