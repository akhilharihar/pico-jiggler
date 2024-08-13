add_executable(jiggler
        jiggler.c
        usb_descriptors.c
        )

target_include_directories(jiggler PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_link_libraries(jiggler PRIVATE pico_stdlib tinyusb_device tinyusb_board pico_unique_id)
pico_add_extra_outputs(jiggler)

pico_set_program_description(jiggler "Simulate mouse that periodically moves a small amount")
pico_set_program_version(jiggler ${CMAKE_PROJECT_VERSION})
pico_set_program_url(jiggler ${CMAKE_PROJECT_HOMEPAGE_URL})

add_custom_command(
        TARGET jiggler POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_CURRENT_BINARY_DIR}/jiggler.uf2" "${CMAKE_CURRENT_BINARY_DIR}/${PICO_BOARD}-jiggler.uf2"
)