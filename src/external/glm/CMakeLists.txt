add_library(glm INTERFACE)

target_sources(
	glm
	INTERFACE
	${CMAKE_CURRENT_SOURCE_DIR}/glm/glm.hpp
)

target_include_directories(
	glm
	INTERFACE
	${CMAKE_CURRENT_SOURCE_DIR}
)
