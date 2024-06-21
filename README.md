# Embedded System Control with STM32 - Blinking LED with Optimizations

## Overview
This project an optimization of [this](https://github.com/Joel-Milla/ActivateDeactivateLED) repository. This version includes optimizations using `volatile` and `const` keywords, and a new `main.h` file to improve code clarity and efficiency.

## Key Features
- **Clock Activation**: Ensures power is supplied to GPIOD peripherals, and allows GPIOA to receive power.
- **GPIO Configuration**: Sets specific GPIOD pins to output mode to turn on the LEDs, and read input values coming from a specific GPIOA pin.
- **Optimizations**: Uses `volatile` for O3 optimization and `const` to indicate immutable pointers.
- **Structured Register Access**: `main.h` contains types to interact with the registers via structures, making the code more readable.

## Project Structure
- `main.c`: Implements the configuration of the GPIO pins and controlling the LEDs.
- `main.h`: Defines types and structures to facilitate interaction with hardware registers.

## Hardware and Tools
- **Microcontroller**: STM32F407
- **IDE**: STM32CubeIDE

## Setup and Run
1. Open the project in STM32CubeIDE.
2. Connect the STM32F407 development board.
3. Compile the code to the microcontroller.

## Testing
- **LED Blinking**: Observe that by connecting VDD pin with PA0 pin, four LEDs turn on.

## Detailed Operation
- **Clock Initialization**: The clock for GPIOD && GPIOA are enabled to allow data and voltage passage.
- **Mode Configuration**:
  - GPIOD pin 12/13/14/15 are set to output mode to control the four LEDs.
  - GPIOA pin 0 is being read so the program knows when to turn on the LEDs.
- **Optimization and Structure**:
  - `volatile` keyword is used to ensure proper handling of variables subject to change unexpectedly.
  - `const` keyword indicates pointers that should not be modified.
  - `main.h` file includes bitfield structures to interact with the GPIO registers, providing clear manipulation for the programmer to understand.
