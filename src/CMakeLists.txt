include_directories (.)

set(SOURCE_FILES
	lexer.cpp
	tinyparser.cpp
)

set(HEADER_FILES
	lexer.hpp
	wptr.hpp
	tinyparser.hpp
	genvisitor.hpp
)

add_library (${PROJECT_NAME} ${LIBRARY_TYPE} ${SOURCE_FILES})

target_compile_features (${PROJECT_NAME} PRIVATE cxx_range_for)

# Export.
export (TARGETS ${PROJECT_NAME} FILE "./tipaConfig.cmake")
export (PACKAGE ${PROJECT_NAME})
install(FILES ${HEADER_FILES} DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/include)
