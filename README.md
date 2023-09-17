# Ox64 Friend
### Work in progress, testing and feedback welcome (and encouraged)!
Debug probe intended to be used with the PINE64 Ox64 development board. \
Based on [the Rapsberry Pi Picoprobe](https://github.com/raspberrypi/picoprobe) and [sanjay900's ox64-uart](https://github.com/sanjay900/ox64-uart).

## Features
- 2 USB-CDC to UART interfaces
- CMSIS-DAP (HID) debug probe, supporting:
    - JTAG (what the Ox64 uses)
    - SWD

## Usage

### The JTAG functionality hasn't been tested with the Ox64 yet (but it's confirmed on a STM32F4 target)
The pinout of the probe can be configured in the [picoprobe_config.h](src/picoprobe_config.h) file. By default, it is set as follows:
- UART 1:
    - TX: GPIO4
    - RX: GPIO5
- UART 2:
    - TX: GPIO12
    - RX: GPIO13
- SWD/JTAG:
    - TCK/SWCLK: GPIO2
    - TMS/SWDIO: GPIO3
    - TDO: GPIO6
    - TDI: GPIO7

