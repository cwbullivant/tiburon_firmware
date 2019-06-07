# tiburon_firmware
Firmware for the Tiburon AUV

This repository contains the firmware for the thrusters, sensors (IMU, hydrophones), and pneumatic systems (torpedos, markers) 
for the Tiburon autonomous underwater vehicle, to be used in competition at AUVSI RoboSub 2020 and as an educational tool beyond.

Tiburon utilizes an STM32F446re microcontroller, and the firmware is written to operate on bare metal, without the use of 
the pre-built STM32Cube Hardware Abstraction Layer (HAL). The microcontroller interfaces with Tiburon's main computer, an 
NVidia Jetson Xavier SoM, via I2C. The firmware sends commands received from the Jetson to eight independent thrusters (configured as SPI slaves) via PWM, receives data from the IMU and Hydrophones via I2C, and pneumatic systems via SPI. 

The finished firmware at RoboSub is planned to use FreeRTOS to manage these several capabilities, but initial development 
is being conducted with simple traditional infinite loop.
