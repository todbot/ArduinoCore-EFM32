
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
- https://github.com/arduino/Arduino/wiki/Unofficial-list-of-3rd-party-boards-support-urls


