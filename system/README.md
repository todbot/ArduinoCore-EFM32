The `system` directory contains the `Gecko_SDK` library from https://github.com/SiliconLabs/Gecko_SDK

FIXME: make script to include this or actually commit it to the repo

For now: do this:
```
cd ~/projects/efm32
git clone https://github.com/SiliconLabs/Gecko_SDK
cd ~/projects/ArduinoCore-EFM32/system
ln -s ~/projects/efm32/Gecko_SDK .
```
