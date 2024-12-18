cmake_minimum_required(VERSION 3.12)
project(learnopengl VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(vendor)	

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

find_package(OpenGL REQUIRED)

file(GLOB SOURCES "src/*.cc" "src/*.c")
add_executable(learnopengl ${SOURCES})

target_link_libraries(learnopengl
	PRIVATE
		glfw
		glad
		OpenGL::GL
)
target_include_directories(learnopengl
	PRIVATE
		"src/"
)


