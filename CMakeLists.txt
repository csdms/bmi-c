cmake_minimum_required(VERSION 3.12)

project(bmic LANGUAGES C)

set(BMI_VERSION 2.0)
include(GNUInstallDirs)

configure_file(${CMAKE_SOURCE_DIR}/${CMAKE_PROJECT_NAME}.pc.cmake
  ${CMAKE_BINARY_DIR}/${CMAKE_PROJECT_NAME}.pc)

install(
  FILES bmi.h
  DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
)
install(
  FILES ${CMAKE_BINARY_DIR}/${CMAKE_PROJECT_NAME}.pc
  DESTINATION ${CMAKE_INSTALL_LIBDIR}/pkgconfig
)
