# STM32F446 Button LED State Machine

Embedded C firmware project for the **STM32 Nucleo-F446RE** developed using **STM32CubeIDE**.

This project demonstrates **interrupt-driven button input**, **short-press vs long-press detection**, and a **finite state machine controlling multiple LED modes**. The firmware also includes **UART debug output** to monitor system state transitions.

![20260310_230325](https://github.com/user-attachments/assets/0f753e33-9613-41aa-bb8d-fbb70734c31d)

---

## Features

- **Short press** cycles LED modes:
  - Solid ON
  - Quick flash
  - SOS pattern

- **Long press** turns LED **OFF from any mode**

- Uses **EXTI interrupts** instead of polling  
- Implements **software debouncing**  
- Detects button **press and release** using **rising and falling edge interrupts**  
- Uses **interruptible timing** so flashing and SOS patterns stop immediately when the button is pressed  
- **UART debug output via USART2** reports LED mode transitions

---

## Hardware

- STM32 Nucleo-F446RE  
- Breadboard  
- Pushbutton  
- LED  
- Current-limiting resistor  
- Jumper wires  

---

## Hardware Overview

```
Button ───> PA8 (EXTI interrupt input)

LED ──────> PB5 (GPIO output)

UART ─────> USART2 → ST-LINK Virtual COM Port → PC Terminal
```

---

## Pin Configuration

| Pin | Function |
|-----|----------|
| PA8 | Button input |
| PB5 | LED output |

---

## GPIO Setup

Button input

```
PA8 → GPIO_MODE_IT_RISING_FALLING
PA8 → GPIO_PULLDOWN
```

LED output

```
PB5 → GPIO_MODE_OUTPUT_PP
```

---

## Behavior

Short press cycles through LED modes:

```
OFF → ON → FLASH → SOS → ON
```

Long press from any mode turns the LED off:

```
(any mode) → OFF
```

---

## LED Modes

### Solid ON

LED remains continuously on.

---

### Quick Flash

LED remains mostly off with a brief flash.

```
OFF 1000 ms
ON  100 ms
```

---

### SOS Pattern

Standard Morse code SOS pattern:

```
S = short short short
O = long long long
S = short short short
```

---

## Debug Output

The firmware provides **UART debug messages via USART2** to report LED mode transitions.

Example terminal output:

```
MODE: ON
MODE: FLASH
MODE: SOS
MODE: OFF
```

<img width="1523" height="999" alt="Screenshot (464)" src="https://github.com/user-attachments/assets/1a4088f5-90fb-4987-ac06-7857a5c0e2d6" />


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
- Timing using `HAL_GetTick()`  
- Interrupt-safe shared variables (`volatile`)  
- Interruptible delay patterns  
- UART debug logging  

---

## Development Environment

- STM32CubeIDE  
- STM32 HAL Drivers  
- ARM GCC Toolchain  

---

## Project Structure

```
Core/
Drivers/
STM32F446RETX_FLASH.ld
STM32F446RETX_RAM.ld
Interrupt1.ioc
README.md
.gitignore
```

The `.ioc` file allows the project to be reopened and modified using **STM32CubeMX inside STM32CubeIDE**.

---

## Purpose

This project was created as a learning exercise to explore real embedded firmware design patterns beyond simple LED blinking, including:

- interrupt-driven input handling  
- state machine architecture  
- responsive firmware behavior  
- serial debugging  

---

## Author

Michael Berry
