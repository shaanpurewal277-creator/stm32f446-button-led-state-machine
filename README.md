# STM32F446 Button LED State Machine

Embedded C project for the STM32 Nucleo-F446 built using STM32CubeIDE.  
This project demonstrates interrupt-driven button input with short-press and long-press detection controlling multiple LED modes.

![20260310_230325](https://github.com/user-attachments/assets/0f753e33-9613-41aa-bb8d-fbb70734c31d)


---

## Features

- Short press cycles LED modes
  - Solid ON
  - Quick flash
  - SOS pattern

- Long press turns LED OFF from any mode

- Uses EXTI interrupts instead of polling
- Implements software debouncing
- Detects button press and release using rising and falling edge interrupts
- Uses interruptible timing so flashing and SOS patterns can stop immediately when the button is pressed

---

## Hardware

- STM32 Nucleo-F446
- Breadboard
- Pushbutton
- LED
- Current-limiting resistor
- Jumper wires

---

## Pin Configuration

| Pin | Function |
|-----|----------|
| PA8 | Button input |
| PB5 | LED output |

---

## GPIO Setup

Button input:

PA8 → GPIO_MODE_IT_RISING_FALLING  
PA8 → GPIO_PULLDOWN

LED output:

PB5 → GPIO_MODE_OUTPUT_PP

---

## Behavior

Short press cycles through LED modes:

OFF → ON → FLASH → SOS → ON

Long press from any mode turns the LED off:

(any mode) → OFF

---

## LED Modes

### Solid ON
LED remains continuously on.

### Quick Flash
LED remains mostly off with a brief flash:

OFF 1000 ms  
ON 100 ms

### SOS Pattern

Standard Morse code SOS pattern:

S = short short short  
O = long long long  
S = short short short

---

## Concepts Demonstrated

This project demonstrates several important embedded firmware concepts:

- Embedded C programming
- STM32 HAL usage
- GPIO configuration
- External interrupt handling (EXTI)
- Button debouncing
- Short-press vs long-press detection
- Finite state machines
- Timing using HAL_GetTick()
- Interrupt-safe shared variables (volatile)
- Interruptible delay patterns

---

## Development Environment

- STM32CubeIDE
- STM32 HAL Drivers
- ARM GCC Toolchain

---

## Project Structure

Core/  
Drivers/  
main.c  
STM32xxxx.ioc  
README.md  
.gitignore  

The `.ioc` file allows the project to be reopened and modified using STM32CubeMX inside STM32CubeIDE.

---

## Purpose

This project was created as a learning exercise to practice real embedded firmware patterns beyond simple LED blinking, including interrupt-driven input handling and state-machine based behavior control.

---

## Author

Michael Berry
