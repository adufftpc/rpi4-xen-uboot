# Build Xen for Raspberry Pi 4

This script builds Xen, a 64-bit linux kernel from the Raspberry Pi tree, and packages a minimal 64-bit Ubuntu 18.04 rootfs for the Raspberry Pi 4.
A recent version of Ubuntu is required to run the build script. An internet connection is required. 8 GB RAM or more is recommended, and 10GB+ free disk space.

Usage:

    $ ./rpixen.sh

When the script is finished, flash to SD card with (for example):

    $ umount /dev/sdX1
    $ umount /dev/sdX2
    $ sudo dd if=rpixen.img of=/dev/sdX bs=8M
    $ sync

Xen will print messages to the UART.

This script is a little bit like [https://github.com/mirage/xen-arm-builder](https://github.com/mirage/xen-arm-builder) and [https://github.com/RPi-Distro/pi-gen](https://github.com/RPi-Distro/pi-gen) but for Xen+Ubuntu instead of Raspbian.
More info about Ubuntu Base is available here [https://wiki.ubuntu.com/Base](https://wiki.ubuntu.com/Base).

## Limitations

* System RAM limited to 1024M
* PCIe not working
* HDMI not working
* Raspberry Pi kernel not suitable for domU