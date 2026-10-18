# Hardware Design
This folder contains the files for the PCB for the step tracker

## Table of contents:


## Power Block
This block of the PCB contains the supply of power to the system. This consists of 3 main components:

1. A 3.7 Volt LiPo battery 
2. A TPS63031DS regulator for buck/boost conversion 
3. A push button to control on/off of system

The net labels are as follows:
- VBAT+ : the positive end of the LiPo Battery
- VBAT_SW: the voltage after going through the switch 
- 3V3: The regulated voltage


## Controller Block
This block of the PCB contains the main schematic for the controller (ESP32-C3-Mini-1). This connects the controller to all the peripherals of the PCB. The main layout is as follows:

1. Connection to the accelerometer
2. Connection to the LCD 
3. Connection to the EEPROM 
4. Connection to the Power Supply
5. Connection to the USB-C receptacle for programming/debugging 
6. Push button for resetting of the controller

The net labels are as follows:

- I2C_SDA: The Serial Data line for the accelerometer and EEPROM data
- I2C_SCL: The Serial Clock line for the accelerometer and EEPROM clock
- ACC_INT1: The accelerometer's step interrupt 
- LCD_SCK: The LCD serial clock
- LCD_MOSI: The LCD serial data
- LCD_CS: The LCD Chip Select
- LCD_A0: The LCD command/data selection
- LCD_RESET: The LCD reset 

## Accelerometer Block
This block of the PCB contains the accelerometer (LSM6DS3TR-C). It is connected to the controller block via I2C, and also has an interrupt pin for step detection. 

## Memory Block
This block of the PCB contains the EEPROM (AT24C04). It is connected to the controller block via I2C, and is used to store the step count. 

## Display Block
This block of the PCB contains the LCD (SSD1306B02). It is connected to the controller block via I2C, and is used to display the step count.

