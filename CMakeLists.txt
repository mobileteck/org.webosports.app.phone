project(org.webosports.app.phone)

cmake_minimum_required(VERSION 2.8.8)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)

include(webOS/webOS)
webos_modules_init(1 0 0 QUALIFIER RC3)
webos_component(0 1 0)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fvisibility=hidden -fvisibility-inlines-hidden -Wall -std=c++0x")

find_package(Qt5Core REQUIRED)
find_package(Qt5Qml REQUIRED)
find_package(Qt5Quick REQUIRED)

find_package(PkgConfig "0.22" REQUIRED)

pkg_check_modules(GLIB2 glib-2.0 REQUIRED)
pkg_check_modules(WEBOS_APPLICATION webos-application REQUIRED)

set(APP_DIR ${WEBOS_INSTALL_WEBOS_APPLICATIONSDIR}/org.webosports.app.phone)

add_subdirectory(data)
add_subdirectory(src)
