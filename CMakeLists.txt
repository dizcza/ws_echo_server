# The following lines of boilerplate have to be in your project's CMakeLists
# in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.16)

list(APPEND EXTRA_COMPONENT_DIRS
           "/home/dizcza/Projects/Embedded/eclipse-workspace/esp32-sdpsensor/components_esp32"
           "/home/dizcza/Projects/Embedded/eclipse-workspace/esp32-sdpsensor/esp-idf-lib/components"
           "$ENV{IDF_PATH}/examples/common_components"
           )

set(COMPONENTS esp32 esp_rom freertos log main bsp esp_event nvs_flash esp_netif protocol_examples_common json esp_http_server console)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
get_filename_component(ProjectId ${CMAKE_CURRENT_LIST_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})
project(${ProjectId})
