cmake_minimum_required(VERSION 3.14)


if(NOT TARGET code_template)
	project(CodeTemplate)
    find_package(CodeTemplate REQUIRED CONFIG)
    enable_testing()
endif()

add_executable(test_hello test_hello.cpp)
target_link_libraries(test_hello PUBLIC code_template)
add_test(NAME test_hello COMMAND test_hello)