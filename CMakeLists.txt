cmake_minimum_required(VERSION 2.8)

set(project_name "hello")
set(project_sources "app.cpp")

project(${project_name})
# add_subdirectory(ext/googletest)
add_subdirectory(ext/tinyxml2)

message(***)
# message(${gtest_include_dirs})
# message(${gtest_libs_dir})
message(${tinyxml2_include_dirs})
message(${tinyxml2_libs_dir})
message(***)

# include_directories(${gtest_include_dirs} ${tinyxml2_include_dirs})
include_directories(${tinyxml2_include_dirs})
add_executable(${project_name} ${project_sources})
# add_dependencies(${project_name} googletest tinyxml2)
add_dependencies(${project_name} tinyxml2)
target_link_libraries(${project_name} ${tinyxml2_libs_dir}/libtinyxml2.a)