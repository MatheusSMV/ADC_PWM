cmake_minimum_required(VERSION 3.13)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(PICO_SDK_PATH "C:/Users/mathe/.pico-sdk")


# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)

# == DO NOT EDIT THE FOLLOWING LINES for the Raspberry Pi Pico VS Code Extension to work ==
if(WIN32)
    set(USERHOME $ENV{USERPROFILE})
else()
    set(USERHOME $ENV{HOME})  #Apagar ao enviar.
endif()
set(sdkVersion 2.1.0)
set(toolchainVersion 13_3_Rel1)
set(picotoolVersion 2.1.0)
set(picoVscode ${USERHOME}/.pico-sdk/cmake/pico-vscode.cmake)
if (EXISTS ${picoVscode})
    include(${picoVscode})
endif()
# ====================================================================================

set(PICO_BOARD pico CACHE STRING "Board type")
include(pico_sdk_import.cmake)

# Definir o Nome do Projeto
project(Projeto_01 C CXX ASM)
pico_sdk_init()

add_executable(${PROJECT_NAME}
Projeto_01.c # Nome do Projeto Principal em C
inc/ssd1306.c # Biblioteca para o display OLED
)

# Program Name e Program Version
pico_set_program_name(${PROJECT_NAME} "Projeto_01")
pico_set_program_version(${PROJECT_NAME} "0.1")

# Habilitando UART
pico_enable_stdio_uart(${PROJECT_NAME} 0)
pico_enable_stdio_usb(${PROJECT_NAME} 1)

# Bibliotecas Utilizadas
target_link_libraries(${PROJECT_NAME} 
    pico_stdlib
    hardware_i2c
    hardware_adc
    hardware_pwm
    hardware_gpio
)


target_include_directories(${PROJECT_NAME} PRIVATE 
  ${PICO_SDK_PATH}/src/rp2_common/hardware_pio/include
)


pico_add_extra_outputs(${PROJECT_NAME})
