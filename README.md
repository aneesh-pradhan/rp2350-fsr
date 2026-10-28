# rp2350-fsr

USB HID native code for RP-2350 based boards designed for DDR dance pads that
use FSR sensors.

This is a fork of [teejusb/fsr](https://github.com/teejusb/fsr), reworked to
run on RP2350 boards which the original did not support out of the box.

## Changes from upstream

- RP2350 platform support (Arduino-Pico Joystick, 1000Hz HID polling)
- Per-panel threshold adjustments
- Serial protocol rewrite

## Hardware

Four FSRs, one per panel, read on `A0`-`A3`. To change the number of panels
or their pins, edit `kSensors` in `fsr_usbserial_rp2350.ino`.

## Flashing

1. Install the [Arduino-Pico](https://github.com/earlephilhower/arduino-pico)
   core in the Arduino IDE.
2. Select your RP2350 board.
3. Open `fsr_usbserial_rp2350.ino` and upload.

The board shows up as a USB joystick, one button per panel, and as a serial
port at 115200 baud.

## Serial commands

Each command is a single character, so tools can send them without waiting
for a newline:

| Send | Does |
|---|---|
| `v` | Print the current sensor values |
| `t` | Print the current thresholds |
| `o` | Recalibrate the sensor offsets |
| `s` | Save the thresholds to EEPROM |
| `3 180` | Set panel 3's threshold to 180 (0-1023) |

## License

GPL-3.0-or-later. See [LICENSE](LICENSE).

Upstream copyright and license are retained per the terms of the GPL-3.0.
