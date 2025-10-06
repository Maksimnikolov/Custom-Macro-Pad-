Max Deck
Max Deck is an open-source, customizable macro keypad that displays a unique image behind every key. It was created as an affordable alternative to commercial macro devices while still offering flexibility, software control, and extendable features.
The device can switch between multiple profiles, assign shortcuts to each key, and update its display based on the active application. A companion desktop app makes setup and configuration fast and beginner-friendly.
Overview
Max Deck connects to your computer over USB and communicates through a simple serial interface. Once configured, it runs in the background and listens for button presses, sending keystrokes or launching applications based on your settings.
The project includes both firmware (for the microcontroller) and a desktop GUI for managing images and macros.
Key Features
Individual icon for every button
Multiple profiles with different macro sets
Optional automatic switching based on active application
Supports launching software directly from the keypad
MQTT compatibility for smart home use
Easy image uploading through the GUI
Works without needing to install Python libraries manually
Desktop Software
A ready-to-use application is included for both Windows and macOS, as well as the full Python source code.
You can:
Upload custom images
Assign macros to any button
Record keypresses directly in the app
Choose colors for display icons
Link profiles to specific applications
Once configured, the app can run silently in the background and handle keystrokes on demand.
Note:
Automatic profile switching currently functions only on Windows. The macOS version has been tested on macOS Big Sur (11.6).
Images
When you upload an image, the software automatically converts it to the correct format and size. You can assign a color during upload, and dark parts of the image will appear in that color. For icons with multiple colors, you can modify the firmware directly.
Macros
Keyboard commands are handled using the pynput library. You can enter macros manually or use the built-in key recorder.
Examples:
Typing a word character by character
Sending key combinations like Control+Shift+S
Triggering external scripts or hotkeys
For complex workflows, you can map keys to unused combinations and handle the rest with tools like AutoHotKey.
Application-Based Switching
Max Deck can adapt its key layout based on what you’re doing. You can assign each profile to a program name, and the desktop app will update the keypad automatically.
There are three optional behaviors:
Open an application when switching folders on the keypad
Focus an app before sending its macros
Change to the correct profile when a program becomes active
Firmware
The firmware runs on an ESP8266-based board and stores bitmap images in SPIFFS so they persist after power-off.
When a key is pressed, the device sends its ID over USB serial. The companion software reacts by triggering the associated macro or command.
All firmware files are included in the code folder, and default builds can be flashed with standard Arduino tools.
MQTT Integration
Max Deck can also operate as a smart home controller. An example firmware version is included that sends button numbers over MQTT to a topic of your choice. This can be used with services like Home Assistant.
Images can still be stored onboard and updated via the desktop app.
Future support may allow MQTT setup directly through the GUI.
Hardware Notes
Refer to the included BOM for all electronic and mechanical parts.
Key components include:
ESP8266 (WEMOS D1 Mini V4 with USB-C)
128×160 TFT display
Low-profile M2 fasteners
Custom PCB
3D printed and/or CNC machined parts
The exact display model and pinout must match the PCB footprint.
Printed & Machined Parts
3D Printed Components
All printed parts are designed to print without supports. Each piece has an optimal orientation shown in the project files.
Machined Components
Carbon fiber top plate (1 mm)
Acrylic keycaps (4.5 mm, identical pieces)
If CNC equipment is unavailable, keycaps can be produced from stacked laser-cut acrylic or printed in clear resin and polished.
PCB Files
A zipped Gerber set is included and ready for board fabrication through any PCB manufacturer.
Advanced Image Customization
For multicolor icons, edits can be made directly in the firmware. The Code folder includes additional details and examples.
