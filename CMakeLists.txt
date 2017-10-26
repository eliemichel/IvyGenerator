cmake_minimum_required(VERSION 3.0)
project(IvyGenerator)

add_subdirectory(external)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5Widgets REQUIRED)
if(Qt5Widgets_FOUND)
	message("Using Qt ${Qt5Widgets_VERSION} from ${Qt5Widgets_INCLUDE_DIRS}")
endif()

function(target_link_libraries_and_dll target lib)
	target_link_libraries(${target} ${lib})
	add_custom_command(
	    TARGET ${target} POST_BUILD
	    COMMAND ${CMAKE_COMMAND} -E copy_if_different
	        $<TARGET_FILE:${lib}>
	        $<TARGET_FILE_DIR:${target}>
	)
endfunction()



add_executable(
	ivy
	BasicMesh.cpp
	BasicMesh.h
	Camera.cpp
	Camera.h
	Common.cpp
	Common.h
	Ivy.cpp
	Ivy.h
	ivygenerator.cpp
	ivygenerator.h
	main.cpp
	OBJLoader.cpp
	OBJLoader.h
	OBJWriter.cpp
	OBJWriter.h
	RenderWidget.cpp
	RenderWidget.h
	SetupWidget.cpp
	SetupWidget.h
	Vector2d.h
	Vector3d.h
)

target_link_libraries(ivy glad)
target_link_libraries_and_dll(ivy Qt5::Core)
target_link_libraries_and_dll(ivy Qt5::Gui)
target_link_libraries_and_dll(ivy Qt5::Widgets)


#file(COPY share DESTINATION .)
