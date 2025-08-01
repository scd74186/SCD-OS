# SCD-OS
An operating system written in CircuitPython for the ESP32-S3 with some extra hardware

# Main Features:
  Easy to program - plug your hardware into your computer to edit the python files
  Seperate programs - programs are stored as .py files, and are executed inside of a 'main' script
  Easy to control - device uses a Wii Nunchuck (3.3v, analog joystick, two buttons, accelerometre, uses I2C)
  "Interesting" hardware - features a radio transmitter and NFC module
  Dual-Processor - there is an esp32-Wrover-E with a camera running arduino that communicates with the main esp32 (circuitpython) to use the camera and also an nRF24l01 for walkie talkie channels
  Colour touchscreen - the screen is a 320x480 SPI ILI9488 colour touchscreen, which is good because it has colour and touch!

# Why?
  This originally started because I wanted to emulate amiibo without using an nfc card (because I had none) using an nfc module, but found out that it was unfortunately not possible. I found a project for this for a microcontroller that I didn't have, and that inspired me to make my own device with modules for doing various tasks, similar to the Flipper-Zero

# Universal Bluetooth Library - BlueGums
  BlueGums is a bluetoth library that runs on the device. the way that it works is by having a list of bluetooth devices, each of them stored in a .json file that is converted to a python object. Each of these objects are an individual connection, containing important information about the device. There is also a list stored in ram containing current connected bluetooth devices - due to the device running apps and programs inside of the main script, variables are shared across scripts. the purpose of this is to avoid programs requiring you to connect to the same bluetooth device over and over.

# What use is this?
  This device/operating system has an SD card slot, and _does_ come with built in programs in the flash memory. These programs would be pretty normal, with simple features such as nfc, .wav audio playback and file transfer between flash memory and SD cards.
