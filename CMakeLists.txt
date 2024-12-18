cmake_minimum_required(VERSION 3.12)
project(learnopengl VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(vendor)

file(GLOB SOURCES "src/*.cc" "src/*.c")
add_executable(learnopengl ${SOURCES})

target_link_libraries(learnopengl
	PRIVATE
		glfw
		glad
)
target_include_directories(learnopengl
	PRIVATE
		"src/"
)


