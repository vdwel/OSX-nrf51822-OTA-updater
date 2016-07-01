# OSX-nrf51822-OTA-updater
This is just a simple I put together to be able to upload applications build with Arduino IDE and the RedbearLab library for the nrf51822.

I use a nrf51822 board with the RedbearLab bootloader installed on it.

It was made by using the Adafruit example and nrf51_dfu_tool from xiongyihui

You need to install "Adafruit_Python_BluefruitLE" first.

This script was tested on OSX, but it might work on Linux as well. Let me know if it works.

**Usage: ota.py -f hexfile**