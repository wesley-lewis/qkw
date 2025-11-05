cmake_minimum_required(VERSION 3.15)
project(qkw VERSION 1.0 LANGUAGES CXX)

set(CMAKE_POLICY_VERSION_MINIMUM 3.5)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

# ----- fmt -----
FetchContent_Declare(
	fmt
	GIT_REPOSITORY https://github.com/fmtlib/fmt.git
	GIT_TAG 11.0.2
)
FetchContent_MakeAvailable(fmt)

# ----- yaml-cpp -----
FetchContent_Declare(
	yaml-cpp
	GIT_REPOSITORY https://github.com/jbeder/yaml-cpp.git
	GIT_TAG master
)
FetchContent_MakeAvailable(yaml-cpp)

# Find dependencies
find_package(SQLite3 REQUIRED)

file(GLOB SRC_FILES src/*.cpp)

# Add the executable
add_executable(${PROJECT_NAME} ${SRC_FILES})

target_include_directories(${PROJECT_NAME}
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}/include
)

# Link the libraries
target_link_libraries(${PROJECT_NAME}
	PRIVATE
		fmt::fmt
		SQLite::SQLite3
		yaml-cpp
)
