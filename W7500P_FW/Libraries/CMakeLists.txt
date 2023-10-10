include(W7500x_common.cmake)
set(TARGET_NAME main)

add_executable(${TARGET_NAME}   
        ${CMAKE_SOURCE_DIR}/W7500P_FW/Projects/Peripheral_Examples/GPIO/Blink_LED/${TARGET_NAME}.c
        )

target_link_libraries(${TARGET_NAME} PRIVATE
        GPIO_FILES
        )

extract_binary(${TARGET_NAME})