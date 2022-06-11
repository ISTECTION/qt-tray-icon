cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project(qt-tray-icon LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Widgets)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Widgets)

set(TS_FILES res/lang/ru_RU.ts)

set(QT_SOURCES
    src/main.cpp
    src/mainwindow.cpp)

set(QT_HEADERS include/mainwindow.h)

add_executable(${PROJECT_NAME}
    ${QT_SOURCES}
    ${QT_HEADERS}
    ${TS_FILES}
    res/resources.qrc
    mainwindow.ui)

target_link_libraries(helloworld Qt${QT_VERSION_MAJOR}::Widgets)