cmake_minimum_required(VERSION 2.6)

project (bmi)

set (BMI_VERSION 0.1)

configure_file (${CMAKE_CURRENT_SOURCE_DIR}/bmic.pc.cmake
                ${CMAKE_CURRENT_SOURCE_DIR}/bmic.pc)

set (BUILD_SHARED_LIBS ON)

include_directories( ${CMAKE_CURRENT_SOURCE_DIR}/.. )
include_directories( ${CMAKE_CURRENT_SOURCE_DIR} )

set (bmi_lib_SRCS bmi.c)
add_library (bmic ${bmi_lib_SRCS} )

########### Install files ###############

install(TARGETS bmic DESTINATION lib COMPONENT bmi)
install(FILES bmi.h bmilib.h
        DESTINATION include/bmi
        COMPONENT bmi)
install(FILES bmic.pc DESTINATION lib/pkgconfig)
