# For more information about build system see
# https://docs.espressif.com/projects/esp-idf/en/latest/api-guides/build-system.html
# The following five lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(Esp32Bacnet)

if(ESP_PLATFORM)
	# Build ArduinoJson as an ESP-IDF component
	idf_component_register(INCLUDE_DIRS src)
	return()
endif()

add_subdirectory(src)

idf_component_register(INCLUDE_DIRS "src")
