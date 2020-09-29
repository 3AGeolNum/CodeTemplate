
set(target_name code_template)
add_library(${target_name} STATIC "") # try SHARED for dynamic library

target_sources(${target_name}
    PRIVATE
		"${PROJECT_SOURCE_DIR}/src/code_template/print_log.cpp"
    PRIVATE 
		"${PROJECT_SOURCE_DIR}/include/code_template/print_log.h"
)
target_include_directories(${target_name} 
    PUBLIC   
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
	$<BUILD_INTERFACE:${PROJECT_BINARY_DIR}>
	$<INSTALL_INTERFACE:include>
)

export(TARGETS ${target_name}
        FILE ${PROJECT_BINARY_DIR}/${target_name}_target.cmake
)
	
#install target
install(TARGETS ${target_name} EXPORT ${target_name} DESTINATION ${PROJECT_BINARY_DIR}/install/lib)
#install export
install(EXPORT ${target_name} FILE ${target_name}_target.cmake DESTINATION ${PROJECT_BINARY_DIR}/install/cmake/)

#install includes
install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/
        DESTINATION ${PROJECT_BINARY_DIR}/install/include/
)


