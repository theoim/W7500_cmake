add_library(SYSTEM_W7500X_FILES STATIC 
                ${SYSTEM_W7500X_DIR}/Source/system_W7500x.c)

target_include_directories(SYSTEM_W7500X_FILES PUBLIC
        ${SYSTEM_W7500X_DIR}/Include
        ${CMSIS_DIR}/Include
        )