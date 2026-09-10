# rp2350-fsr

USB HID native code for RP-2350 based boards designed for DDR dance pads that
use FSR sensors.

This is a fork of [teejusb/fsr](https://github.com/teejusb/fsr), reworked to
run on RP2350 boards which the original did not support out of the box.

## Changes from upstream

- RP2350 platform support (Arduino-Pico Joystick, 1000Hz HID polling)
- Per-panel threshold adjustments
- Serial protocol rewrite

## License

GPL-3.0-or-later. See [LICENSE](LICENSE).

Upstream copyright and license are retained per the terms of the GPL-3.0.
