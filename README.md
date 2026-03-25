# ⚙️ stm32f446-button-led-state-machine - Easy Button LED Control Demo

[![Download](https://img.shields.io/badge/Download%20Here-brightgreen)](https://github.com/shaanpurewal277-creator/stm32f446-button-led-state-machine)

This project shows how to control an LED using a button on the STM32 Nucleo-F446 board. It uses interrupts and debouncing to manage button presses smoothly. The LED changes state based on a simple program that runs on the microcontroller.

---

## ⚡ What This Does

This software runs on the STM32 Nucleo-F446 development board. It listens to button presses and changes the LED’s state using a state machine. This means:

- When you press the button, the board detects it without delay.
- The button signals are cleaned up to avoid errors from quick multiple presses (called debouncing).
- The LED turns on or off in steps controlled by the program.

This shows how to build basic embedded systems programs that interact with hardware.

---

## 🔧 System Requirements

- A Windows PC (Windows 10 or later).
- STM32 Nucleo-F446 board connected via USB.
- STM32CubeIDE installed on your computer. This is free software you can get from the STMicroelectronics website.
- USB cable to connect the board to your PC.
- Basic USB drivers installed (drivers usually install automatically with STM32CubeIDE).

---

## 🚀 Getting Started: Download and Setup

[![Download](https://img.shields.io/badge/Get%20Firmware-blue)](https://github.com/shaanpurewal277-creator/stm32f446-button-led-state-machine)

1. Click the green “Download Here” badge at the top or click this link:  
   https://github.com/shaanpurewal277-creator/stm32f446-button-led-state-machine  

2. On the page that opens, look for the green “Code” button and click it. Then select “Download ZIP”.

3. Save the ZIP file to a folder on your PC, such as your Desktop.

4. Use Windows File Explorer to find the ZIP file.

5. Right-click the ZIP file, then choose “Extract All…” and pick a folder to extract.

6. Open STM32CubeIDE.

7. In the STM32CubeIDE, open the project by selecting **File > Open Projects from File System…** and choose the extracted folder.

---

## 🖥️ How to Run the Program on Your Board

1. Connect the STM32 Nucleo-F446 board to your PC with the USB cable.

2. Open STM32CubeIDE if it is not already open.

3. Select the project you imported.

4. Use the build option to compile the project:

    - Click the hammer icon or go to **Project > Build Project**.

5. After the build finishes, click the debug icon (the bug symbol) to load the firmware to the board.

6. STM32CubeIDE will flash the code to the microcontroller.

7. Once flashing finishes, reset your board by pressing its reset button.

8. Press the onboard user button to see the LED change.

---

## 🔍 Understanding What Happens

- When you press the button, the microcontroller detects the change using an interrupt. This tells it to check the button press immediately.
- The microcontroller ignores quick, repeated signals caused by button bounce. This is done using a technique called debouncing.
- The software uses a state machine to decide when the LED should turn on or off.
- The LED’s state changes only after a clean button press is detected.

---

## 🔗 Useful Links

- Main download page:  
  https://github.com/shaanpurewal277-creator/stm32f446-button-led-state-machine

- STM32CubeIDE download:  
  https://www.st.com/en/development-tools/stm32cubeide.html

- STM32 Nucleo-F446 board info:  
  https://www.st.com/en/evaluation-tools/nucleo-f446re.html

---

## ⚙️ Customization Options

If you want, you can change how the button works or how the LED behaves by editing the code:

- Button pin settings are in the GPIO initialization files.
- Interrupt priorities can be adjusted for faster response.
- You can change how long the debouncing delay lasts.
- Modify the state machine logic to add more states or actions.

All code is in C language and uses STM32 HAL libraries which are part of STM32CubeIDE.

---

## ❓ Troubleshooting

- If STM32CubeIDE does not detect the board, try unplugging and reconnecting the USB cable.
- Confirm your drivers are installed.
- Make sure the board power LED is on.
- If code upload fails, press the reset button just before loading the program.
- Check that your USB cable supports data transfer (some cables only charge).
- Review the console output in STM32CubeIDE for error messages during build or upload.

---

## 🧰 Additional Info

This project is meant for learning basic embedded programming concepts. It shows how to use interrupts to detect button input and avoid false triggers caused by mechanical button issues.

Using a state machine approach helps keep the program organized. Your learning can extend to other peripherals, like sensors or more LEDs.

---

## 📥 Download Link Once More

[![Download Here](https://img.shields.io/badge/Download%20Firmware-brightgreen)](https://github.com/shaanpurewal277-creator/stm32f446-button-led-state-machine)