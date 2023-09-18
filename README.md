# Ox64 Friend
Debug and UART probe intended to be used with the PINE64 Ox64 development board. \
Based on [the Rapsberry Pi Picoprobe](https://github.com/raspberrypi/picoprobe) and [sanjay900's ox64-uart](https://github.com/sanjay900/ox64-uart), with bits from [DapperMime](https://github.com/majbthrd/DapperMime).

## Features
- 2 USB-CDC to UART interfaces
- CMSIS-DAP (HID) debug probe, supporting:
    - JTAG (what the Ox64 uses)
    - SWD

## Usage
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

### Ox64 wiring
The JTAG port of the BL808 on the Ox64 can be accesed through the following pins:
| JTAG | BL808 GPIO | Ox64 board pin |
|------|------------|----------------|
| TCK  | GPIO12     | 4              |
| TMS  | GPIO6      | 27             |
| TDO  | GPIO7      | 26             |
| TDI  | GPIO13     | 5              |

By default, the PINMUX of the BL808 connects these pins to the M0 core. To connect with the openocd included in [bouffalo-sdk](https://github.com/bouffalolab/bouffalo_sdk), the following command line can be used: `openocd -c "adapter driver cmsis-dap" -c "transport select jtag" -c "adapter speed 4000" -f "target\tgt_e907.cfg"`


