cmake_minimum_required(VERSION 3.12)

# rest of your project
add_executable(anavi_dev_mic
    main.c
    usb_descriptors.c
    anavi_dev_mic.c
)

target_include_directories(anavi_dev_mic PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_link_libraries(anavi_dev_mic PRIVATE tinyusb_device tinyusb_board pico_pdm_microphone)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(anavi_dev_mic)
