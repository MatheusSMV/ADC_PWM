

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(PICO_SDK_PATH "C:/Users/mathe/.pico-sdk")

set(PICO_BOARD pico CACHE STRING "Board type")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(ADC_PWM C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(ADC_PWM ADC_PWM.c inc/ssd1306.c)

pico_set_program_name(ADC_PWM "ADC_PWM")
pico_set_program_version(ADC_PWM "0.1")

# Modify the below lines to enable/disable output over UART/USB
pico_enable_stdio_uart(ADC_PWM 0)
pico_enable_stdio_usb(ADC_PWM 1)

# Add the standard library to the build
target_link_libraries(ADC_PWM 
    pico_stdlib
    hardware_i2c
    hardware_adc
    hardware_pwm
    hardware_gpio
)

# Add the standard include files to the build
target_include_directories(ADC_PWM PRIVATE 
  ${PICO_SDK_PATH}/src/rp2_common/hardware_pio/include
)

# Add any user requested libraries
target_link_libraries(ADC_PWM 
        hardware_i2c
        )

pico_add_extra_outputs(ADC_PWM)

