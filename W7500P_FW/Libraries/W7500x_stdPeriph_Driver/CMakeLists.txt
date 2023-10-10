add_library(GPIO_FILES STATIC ${CMAKE_CURRENT_SOURCE_DIR}/src/W7500x_gpio.c)
target_include_directories(GPIO_FILES PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/inc)
target_link_libraries(GPIO_FILES SYSTEM_W7500X_FILES)