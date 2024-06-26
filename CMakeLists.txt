cmake_minimum_required(VERSION 3.0.2)

project(PPUViewer)

find_package(Qt5Widgets)
find_package(Qt5Core)
find_package(Qt5Gui)
find_package(Qt5OpenGL)

find_package(OpenGL)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

SET( PPUViewer_SRCS
   main.cpp   
   PPUViewer.cpp
   PPUViewer.h
   RenderWidget.cpp
   RenderWidget.h
)

add_executable(PPUViewer ${PPUViewer_SRCS})

qt5_use_modules(PPUViewer Widgets OpenGL)

target_link_libraries(PPUViewer
    ${QT_LIBRARIES}
    ${OPENGL_glu_LIBRARY}
    ${OPENGL_LIBRARY}
    glut
)
