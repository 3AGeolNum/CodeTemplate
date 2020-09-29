
cmake_minimum_required(VERSION 3.14)

# set the project name
project(CodeTemplate)

# set options
option(CODETEMPLATE_WITH_EXECUTABLES "Compile mains" OFF)
option(CODETEMPLATE_WITH_TESTS "Compile test projects" OFF)

# package settings
include(CMakePackageConfigHelpers)
configure_package_config_file(cmake/CodeTemplateConfig.cmake.in CodeTemplateConfig.cmake INSTALL_DESTINATION ${PROJECT_BINARY_DIR})
install(FILES ${PROJECT_BINARY_DIR}/CodeTemplateConfig.cmake DESTINATION ${PROJECT_BINARY_DIR}/install/cmake/)

#about libraries
add_subdirectory(src/code_template)

#about executable
if(CODETEMPLATE_WITH_EXECUTABLES)
    message(STATUS "Configuring CodeTemplate with executables")
    add_subdirectory(src/bin)
endif()

#about tests
if(CODETEMPLATE_WITH_TESTS)
    # Enable testing with CTest
    enable_testing()
    message(STATUS "Configuring CodeTemplate with tests")
    add_subdirectory(tests)
endif()

#------------------------------------------------------------------------------------------------
# Configure CPack
if(WIN32)
    set(CPACK_GENERATOR "ZIP")
else()
    set(CPACK_GENERATOR "TGZ")
endif()

# This must always be last!
include(CPack)