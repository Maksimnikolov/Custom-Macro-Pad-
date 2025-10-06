# Max Deck

Max Deck is an open-source, customizable macro keypad that displays a unique image behind every key. It was created as an affordable alternative to commercial macro devices while still offering flexibility, software control, and extendable features.

The device supports multiple profiles, assigns shortcuts to each key, and can automatically update its display based on the active application. A companion desktop app makes setup and configuration simple and beginner-friendly.

---

## Overview

Max Deck connects to your computer over USB and communicates through a serial interface. After setup, it runs in the background and listens for button presses, triggering keystrokes or launching applications as assigned.

The project includes:
- Firmware for the microcontroller  
- A desktop GUI for managing images and macros

---

## Key Features

- Individual icon for every button  
- Multiple profiles with different macro sets  
- Automatic switching based on the active application (optional)  
- Launch applications directly from the keypad  
- MQTT support for home automation  
- Easy image uploading through the GUI  
- No manual Python library installation required

---

## Desktop Software

The project includes a ready-to-use application for both Windows and macOS, as well as the full Python source code.

You can:
- Upload custom images  
- Assign macros to any button  
- Record keypresses directly from the GUI  
- Select icon colors  
- Link profiles to specific applications  

Once configured, the app can run silently in the background and handle keystrokes automatically.

**Note:**  
Automatic profile switching currently works only on Windows. The macOS version has been tested on macOS Big Sur (11.6).

---

## Images

When uploading an image, the software automatically converts it to the correct format and size. You can pick a color during upload, and darker sections of the image will display in that color. For multi-color icons, modifications can be made directly in the firmware.

---

## Macros

Keyboard input is handled using the `pynput` library. You can enter macros manually or record them in the GUI.

Examples include:
- Typing words character by character  
- Sending key combinations (e.g., Ctrl + Shift + S)  
- Running scripts or shortcuts  

For complex workflows, you can assign unused key combinations and manage them using tools like AutoHotKey.

---

## Application-Based Switching

Max Deck can change its key layout dynamically based on what you're doing. Each profile can be assigned to a specific application, and the software will update the keypad accordingly.

Available behaviors:
1. Launch an application when navigating to its folder on the keypad  
2. Focus an application before sending its macros  
3. Switch the displayed profile based on the active window

---

## Firmware

The firmware runs on an ESP8266 board and stores bitmap images in SPIFFS, ensuring they remain available after power-off.

When a button is pressed, the device sends its ID over USB serial. The companion software then fires the corresponding macro or command.

All firmware files are located in the `Code` folder, and default builds can be flashed using standard Arduino tools.

---

## MQTT Integration

Max Deck can also be used as a smart home controller. An alternative firmware example is provided that publishes button numbers via MQTT to a configurable topic, making it compatible with platforms like Home Assistant.

Images can still be stored on the device and updated using the GUI. Future updates may allow MQTT setup directly from the desktop software.

---

## Hardware Notes

Refer to the included BOM for the complete list of required components.

Core hardware includes:
- ESP8266 (WEMOS D1 Mini V4 with USB-C)  
- 128×160 TFT display  
- Low-profile M2 fasteners  
- Custom PCB  
- 3D printed and/or CNC machined parts  

Make sure the display’s pinout and hole pattern match the PCB design.

---

## Printed & Machined Parts

### 3D Printed Components
All printed parts can be produced without supports. Orientation guidelines are included in the project files.

### Machined Components
- Carbon fiber top plate (1 mm)  
- Acrylic keycaps (4.5 mm, identical shape)

If CNC equipment isn’t available, keycaps can be made from layered laser-cut acrylic or printed using clear resin and polished.

---

## PCB Files

Gerber files are included in a zipped folder and can be sent to any PCB manufacturer.

---

## Advanced Image Customization

For multi-color icons, changes can be made directly in the firmware. The `Code` directory contains instructions and examples for manual customization.

---
