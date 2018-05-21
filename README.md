
# ArduinoCore-EFM32 -- Arduino core for Tomu and EFM32HG boards

WORK IN PROGRESS

This repo will eventually house a working Arduino core for [Tomu](https://tomu.im/)
and similar [EFM32HG](https://www.silabs.com/products/mcu/32-bit/efm32-happy-gecko) boards.

The EFM32HG is a pretty great chip:
- ARM Cortex-M+ @ 25 MHz
- Crystalless USB w/ built-in 3.3V regulator for minimal part count
- 64 kB flash / 8 kB RAM
- Capacitive touch sensors
- Super low-power

And thanks to the Tomu project:
- [USB DFU bootloader - "toboot"](https://github.com/im-tomu/tomu-bootloader/)


This README will serve as a notepad as I work through the process.


Cribbing a lot from:
- https://github.com/adafruit/ArduinoCore-samd
- https://github.com/arduino-org/arduino-core-stm32f4


Also see:
- https://github.com/arduino/Arduino/wiki/Arduino-IDE-1.5-3rd-party-Hardware-specification
- https://github.com/arduino/Arduino/wiki/Build-Process
- https://github.com/arduino/Arduino/wiki/Unofficial-list-of-3rd-party-boards-support-urls


----
## Plan:
- Start by cribbing basic boards.txt & platform.txt from other ARM Cortex-M0+ projects
- To start, use [Gecko SDK](https://github.com/SiliconLabs/Gecko_SDK) instead of [libopencm3](https://github.com/libopencm3) (which supports EFM32HG now) because libopencm3 doesn't have all the peripheral libraries built out yet (particularly interesting to me are LEUART, USART (for SPI & UART), MSC (for self-programming of flash to emulate EEPROM).
- Embed Gecko SDK for now, in pre-release I believe the license can allow for this. Eventually make it a separate package that's downloaded?
- Rely on Tomu's toboot for DFU upload. It seems a good DFU implementation.
- Rely on Arduino's [dfu-util package](https://github.com/arduino/dfu-utils-cross). Be sure to check out `dfu-prefix` and `dfu-suffix` commands to use before `dfu-util`.

## Progress:
- Create directory structure skeleton
- Copied bits of SAMD and STFM32 cores to platform.txt and boards.txt
- Enabled it with:
    ```
    cd ~/Documents/Arduino/hardware
    mkdir todbot && cd todbot
    ln -s ~/projects/ArduinoCore-EFM32 .
    ```
    And then getting it to be seen by opening Boards Manager window then closing it
    (protip: Use System keyboard shortcuts to assign Cmd-Shift-B to "Board Manager...")


