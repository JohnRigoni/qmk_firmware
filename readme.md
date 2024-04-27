### RETRO_TAPPING Retrofittings 

This fork contains a fix for dropped characters when key rolling and the edition of RETRO_TAPPING_TIMEOUT.  
It has exclusively been tested with the setting RETRO_TAPPING enabled and 
with all modifier keys being invoked by dual funtion keys (the layout below).
No testing has been done on RETRO_TAPPING_PER_KEY, AUTO_SHIFT_ENABLE, or RETRO_SHIFT.

Please see the other branches in the repository for the isolated modifications.

## Key Roll Fix

Fix the condition found with RETRO_TAPPING enabled when key rolling. The dual function
keys's retro tap keycode is not fired when a different key has been released
between the dual function keys's down and up events.

Any modifiers held during the key down event of a dual function key will be applied if/when the
retro tap keycode is sent.

## RETRO_TAPPING_TIMEOUT

With RETRO_TAPPING enabled, holding and releasing a dual function key without pressing another key will result
in the key's tap keycode being sent even if outside the tapping term. With RETRO_TAPPING_TIMEOUT enabled as well,
holding a dual function key for longer than the specified timeout duration will result in no keycode being sent
when the key is released.

This setting can be enabled in 'keyboards/<>/keymaps/config.h' with RETRO_TAPPING
and takes an integer that is the timeout duration in milliseconds.

```c
#define RETRO_TAPPING_TIMEOUT 500
```

### Aside

I use a tapping term of 180ms on my bottom-row-mods and 150ms on the thumb keys.
This will likely work for RETRO_TAPPING_PER_KEY.

## Media

### Before Key Roll Fix: Single to Dual Function
![single-dual_before](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/c35d61b2-b747-4631-99ab-3824578c59c2)

### After Key Roll Fix: Single to Dual Function
![sigle-dual_after](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/632795aa-3f7f-4114-b10e-ecd8a44eb565)

### Before Key Roll Fix: Dual to Dual Function
![dual-dual_before](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/378f80b2-175e-40a4-b5ef-55ac031cd5bc)

### After Key Roll Fix: Dual to Dual Function
![dual-dual_after](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/2c4dfd69-8b80-4f70-9ba4-a7c580634c7d)

### Before RETRO_TAPPING_TIMEOUT
![retro-timeout_before](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/302d71b5-96a0-4221-94cd-2c31279ae99c)

### After RETRO_TAPPING_TIMEOUT 😴
![retro-timeout_after](https://github.com/JohnRigoni/qmk_firmware/assets/38547951/4a79ced1-cf52-4c8f-b978-7a475f381753)


# Quantum Mechanical Keyboard Firmware

[![Current Version](https://img.shields.io/github/tag/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/tags)
[![Discord](https://img.shields.io/discord/440868230475677696.svg)](https://discord.gg/Uq7gcHh)
[![Docs Status](https://img.shields.io/badge/docs-ready-orange.svg)](https://docs.qmk.fm)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_firmware.svg?style=social&label=Fork)](https://github.com/qmk/qmk_firmware/)

This is a keyboard firmware based on the [tmk\_keyboard firmware](https://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers, and more specifically, the [OLKB product line](https://olkb.com), the [ErgoDox EZ](https://ergodox-ez.com) keyboard, and the Clueboard product line.

## Documentation

* [See the official documentation on docs.qmk.fm](https://docs.qmk.fm)

The docs are powered by [Docsify](https://docsify.js.org/) and hosted on [GitHub](/docs/). They are also viewable offline; see [Previewing the Documentation](https://docs.qmk.fm/#/contributing?id=previewing-the-documentation) for more details.

You can request changes by making a fork and opening a [pull request](https://github.com/qmk/qmk_firmware/pulls), or by clicking the "Edit this page" link at the bottom of any page.

## Supported Keyboards

* [Planck](/keyboards/planck/)
* [Preonic](/keyboards/preonic/)
* [ErgoDox EZ](/keyboards/ergodox_ez/)
* [Clueboard](/keyboards/clueboard/)
* [Cluepad](/keyboards/clueboard/17/)
* [Atreus](/keyboards/atreus/)

The project also includes community support for [lots of other keyboards](/keyboards/).

## Maintainers

QMK is developed and maintained by Jack Humbert of OLKB with contributions from the community, and of course, [Hasu](https://github.com/tmk). The OLKB product firmwares are maintained by [Jack Humbert](https://github.com/jackhumbert), the Ergodox EZ by [ZSA Technology Labs](https://github.com/zsa), the Clueboard by [Zach White](https://github.com/skullydazed), and the Atreus by [Phil Hagelberg](https://github.com/technomancy).

## Official Website

[qmk.fm](https://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.
