cmake_minimum_required(VERSION 2.8)
set(CMAKE_PREFIX_PATH /usr/arm-none-eabi CACHE STRING "Library search paths")
set(MCU_FAMILY f4 CACHE STRING "MCU family")
set(MCU_HSE 8000000 CACHE STRING "MCU crystal (MHz)")

set(STM32PLUS_CONFIGURATION small-${MCU_FAMILY}-${MCU_HSE})
find_package(stm32plus REQUIRED)
include_directories(${STM32PLUS_INCLUDE_DIRS})

project(blink C CXX ASM)

add_executable(${PROJECT_NAME}
  blink.cpp
  system/LibraryHacks.cpp
  system/${MCU_FAMILY}/System.c
  system/${MCU_FAMILY}/Startup.s
)
target_link_libraries(${PROJECT_NAME} ${STM32PLUS_LIBS})
set_target_properties(${PROJECT_NAME} PROPERTIES
  LINK_FLAGS "-T${PROJECT_SOURCE_DIR}/system/f4/Linker.ld")

add_bin_target(${PROJECT_NAME})
