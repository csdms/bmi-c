cmake_minimum_required(VERSION 2.8)

project(bmic C)

set(BMI_VERSION 2.0)

configure_file(${CMAKE_SOURCE_DIR}/${CMAKE_PROJECT_NAME}.pc.cmake
  ${CMAKE_BINARY_DIR}/${CMAKE_PROJECT_NAME}.pc)

include(GNUInstallDirs)
install(
  FILES bmi.h
  DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
)
install(
  FILES ${CMAKE_BINARY_DIR}/${CMAKE_PROJECT_NAME}.pc
  DESTINATION ${CMAKE_INSTALL_LIBDIR}/pkgconfig
)
