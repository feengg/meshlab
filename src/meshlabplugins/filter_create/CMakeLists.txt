# Copyright 2019-2020, Collabora, Ltd.
# SPDX-License-Identifier: BSL-1.0

### Generated file! Edit the templates in src/templates,
### specifically src/templates/CMakeLists.template.cmake (shared with all other directories),
### or create a derived template in src/templates/filter_create.cmake,
### then re-run ./make-cmake.py

set(SOURCES filter_create.cpp)

set(HEADERS filter_create.h)

add_library(filter_create MODULE ${SOURCES} ${HEADERS})

target_include_directories(filter_create PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(filter_create PUBLIC common)

set_property(TARGET filter_create PROPERTY FOLDER Plugins)

set_property(TARGET filter_create PROPERTY RUNTIME_OUTPUT_DIRECTORY
                                           ${MESHLAB_PLUGIN_OUTPUT_DIR})

set_property(TARGET filter_create PROPERTY LIBRARY_OUTPUT_DIRECTORY
                                           ${MESHLAB_PLUGIN_OUTPUT_DIR})

install(
    TARGETS filter_create
    DESTINATION ${MESHLAB_PLUGIN_INSTALL_DIR}
    COMPONENT Plugins)
