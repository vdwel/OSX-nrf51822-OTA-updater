# OSX-nrf51822-OTA-updater
This is just a simple I put together to be able to upload applications build with Arduino IDE and the RedbearLab library for the nrf51822.

I use a nrf51822 board with the RedbearLab bootloader installed on it.

It was made by using the Adafruit example and nrf51_dfu_tool from xiongyihui

You need to install "Adafruit_Python_BluefruitLE" first.

This script was tested on OSX, but it might work on Linux as well. Let me know if it works.

**Usage: ota.py -f hexfile**

You can even add the ota tool to your arduino ide by editing the file:
/Library/Arduino15/packages/RedBearLab/hardware/nRF51822/1.0.6/platform.txt

add a section with the following code:

\#\# ota tool
tools.ota.path={runtime.platform.path}/tools/ota
tools.ota.cmd=ota.py
tools.ota.cmd.linux=ota.py
tools.ota.cmd.windows=ota.py

tools.ota.upload.params.verbose=
tools.ota.upload.params.quiet=
tools.ota.upload.pattern="{path}/{cmd}" -f {build.path}/{build.project_name}.hex

Also edit boards.txt and change the lines with .upload.tool=openocd -> .upload.tool=ota

Next create a directory tools and in this directory an ota directory:
/Library/Arduino15/packages/RedBearLab/hardware/nRF51822/1.0.6/tools/ota

copy ota.py to this directory. Restart your Arduino IDE