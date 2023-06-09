# Real-Time Temperature Control System

This repository contains the code for a real-time temperature control system implemented on a TM4C123GH6PM microcontroller using FreeRTOS. The system consists of multiple tasks that work together to control the temperature based on user-defined setpoints. The tasks include reading temperature data from an ADC, displaying information on an LCD, receiving user input through UART, and controlling a buzzer and LED to indicate temperature conditions.

## Prerequisites

To run this code on the TM4C123GH6PM microcontroller, you will need the following:

- TM4C123GH6PM microcontroller board
- FreeRTOS library
- Tiva C Series device support package (driverlib)
- Code Composer Studio or any other suitable IDE for C programming

## Getting Started

To get started with the code:

1. Connect the TM4C123GH6PM microcontroller to your computer.
2. Set up the development environment and install the necessary software and libraries.
3. Create a new project in your IDE and import the provided source code files.
4. Build the project and flash the code onto the microcontroller.

## Code Structure

The code consists of several source files that perform specific functions:

- `ADC.c` and `ADC.h`: Contains functions for initializing and reading analog values from the ADC.
- `LCD.c` and `LCD.h`: Implements the driver functions for the LCD module.
- `main.c`: The main file that initializes tasks and handles the overall system operation.
- `UART.c` and `UART.h`: Provides functions for UART communication with the user.
- `tm4c123gh6pm.h`: Registers and definitions specific to the TM4C123GH6PM microcontroller.

## Tasks

The system is divided into four tasks, each responsible for a specific functionality:

1. **MAIN Controller**: Monitors the temperature and controls the heater and LED based on user-defined setpoints. It communicates with other tasks to display information on the LCD and activate the buzzer if necessary.

2. **UART Controller**: Handles user input through UART. It prompts the user to enter temperature setpoints and sends the input to the MAIN Controller task for processing.

3. **LCD Controller**: Displays the temperature and setpoint values on an LCD. It receives the data from the MAIN Controller task and updates the display accordingly.

4. **BUZZER Controller**: Controls the buzzer based on temperature conditions. It receives commands from the MAIN Controller task to either activate or stop the buzzer.

## Usage

After flashing the code onto the microcontroller, follow these steps to interact with the system:

1. Open a serial terminal or serial monitor program and connect to the microcontroller's UART port.
2. The system will prompt you to enter temperature setpoints. Follow the instructions and enter the desired temperature setpoints in degrees Celsius.
3. The system will display the current temperature and setpoint on the LCD.
4. If the temperature exceeds a predefined alarm value, the buzzer will activate.
5. You can change the temperature setpoints at any time by following the prompts in the serial terminal.

## Future Improvements

Although the current system provides basic temperature control functionality, there are several areas for improvement and expansion:

- Enhance error handling and input validation for user interactions.
- Implement more advanced temperature control algorithms, such as PID control.
- Integrate additional sensors to monitor environmental conditions.
- Add networking capabilities to enable remote monitoring and control.
- Implement a graphical user interface (GUI) for easier user interactions.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code for both commercial and non-commercial purposes.

## Acknowledgements

This project was developed as a demonstration of real-time systems

 and FreeRTOS on the TM4C123GH6PM microcontroller. Special thanks to the creators and contributors of the FreeRTOS library for providing an excellent framework for real-time embedded systems.
