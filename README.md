# STM32 Bluetooth Alarm Clock

A programmable real-time clock (RTC) system based on the **STM32F429** microcontroller. It features wireless configuration via an **HC-05 Bluetooth module** and a buzzer-based alert system.

## Project Overview
Developed for the **Microcontrollers** course, this project implements a remote-controlled digital clock. Users can synchronize time, set alarms, and monitor status via a Bluetooth terminal on a smartphone.

### Technical Specifications & Hardware
* **Microcontroller:** STM32F429ZI (Nucleo-144 board)
* **Bluetooth Module:** HC-05 (UART interface)
* **RTC Clock Source:** **LSI (Low Speed Internal)**
    * *Design Note:* The system was switched to the internal RC oscillator (~32 kHz) to ensure consistent time incrementing, as the external crystal (LSE) exhibited hardware instability during the prototyping phase.
* **Indicators:** Active Buzzer for alarms and Serial Console (stdout) for real-time debugging.

## Commands & Functionality
The system parses commands received via Bluetooth and provides feedback through the serial terminal.

**Available Commands:**
1.  `INIT_TIME`: Initializes the current date and time.
2.  `SET_ALARM`: Configures the alarm trigger time.
3.  `STOP_ALARM`: Silences the buzzer once the alarm is active.

## Repository Structure
* `Src/` & `Inc/`: Core logic, RTC management, and command parsing.
* `Drivers/`: HAL and CMSIS driver files.
* `Template_GPIO.ioc`: STM32CubeMX configuration file.
* `MDK-ARM/`: Keil uVision project files.
