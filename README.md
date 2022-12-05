```bash

cargo build

arm-none-eabi-objcopy -O ihex ../target/thumbv7em-none-eabihf/debug/blinky-button-demo blinky.hex
 
adafruit-nrfutil dfu genpkg --dev-type 0x0052 --application blinky.hex blinky-dfu-package.zip
 
adafruit-nrfutil dfu serial -pkg blinky-dfu-package.zip -p /dev/tty.usbmodem124401 -b 115200

```

