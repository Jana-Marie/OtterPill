# OtterPill

OtterPill is a 3$ STM32F072 devboard featuring USB 2.0 full-speed, a DFU Bootloader, a USB-PD Phy and Arduino nano alike pinout and size.

Changelog V1.2: BOM cost reduction by ~40%, PCB can be fully populated by JLCSMT, more efficient buck converter (PCB gets less warm at 20V), GND-hook for probing, Reset-Pin exposed as pad, power pads for 20V/5A

**How do I get an OtterPill?** 

Via [tindie](https://www.tindie.com/products/jan_henrik/otterpill/) (if sold out DM via Twitter, I might have a few left ;))

## Building and Flashing

### Via Makefile and DFU

Or you can generate a basic firmware, with HAL init and Makefile, with CubeMX. The binary can then be build with make and flashed with dfu-utils. To enter DFU mode, press and hold the Button while plugging in power.

    $ make
    $ dfu-util -a 0 -s 0x08000000:leave -D build/firmware.bin

### Via Arduino

[You can build and flash the firmware via Arduino as described here.](https://github.com/stm32duino/Arduino_Core_STM32)

### Via PlatformIO

[https://gist.github.com/ansemjo/ab1c12f7c78abb140f7272501aff2a55](https://gist.github.com/ansemjo/ab1c12f7c78abb140f7272501aff2a55) Thank you [ansemjo](https://github.com/ansemjo) :3

## Schematic

[HW v1.2/OtterPill.pdf](HW%20v1.2/OtterPill.pdf)

## Pinout

![](pinout.png)

Pinout by [SarahhhhFoster](https://github.com/SarahhhhFoster) :)

## Blink example firmware

[Blink/](Blink/)

## Rust example

Thank you [@jamesmunns](https://github.com/jamesmunns)! :3

[https://github.com/jamesmunns/OtterPill-rs](https://github.com/jamesmunns/OtterPill-rs)

## STM workshop based on OtterPill

[https://github.com/Jan--Henrik/hackerhotel-stm-workshop](https://github.com/Jan--Henrik/hackerhotel-stm-workshop)

![](https://github.com/Jan--Henrik/hackerhotel-stm-workshop/blob/master/monochrome_c.gif)

## USB-PD example firmware

This is a working USB-PD example using ChibiOS, a new voltage can be requested by pressing the Button.

[https://github.com/Jan--Henrik/USB-PD-Firmware](https://github.com/Jan--Henrik/USB-PD-Firmware)

## IBM dials retrofit

[https://github.com/Jan--Henrik/IBM-dials-retrofit](https://github.com/Jan--Henrik/IBM-dials-retrofit)

<img src="https://raw.githubusercontent.com/Jan--Henrik/IBM-dials-retrofit/4c27e5c5fda3bd528e12d15f71b0f5aaa8c24b97/images/1.jpeg" width="600">


## Shields and addons

Most Arduino shields should be compatible.

#### [USB-to-CAN-adapter](https://github.com/Jan--Henrik/OtterPill-CAN-Adapter)

## Todo for HW v1.3

 - [ ] Replace U1 with ESDU5V0H4
 - [ ] Add a TVS Diode to VBUS (e.g. SJD12A22L01)
 - [ ] Remove R8, R9
 - [ ] Redraw the FUSB302B Symbol
 - [ ] Consider switching to STUSB4500 (Easier PD requesting, same price)

## Images

![](images/1.jpg)
![](images/2.jpg)

### Rev 1.1

![](images/3.jpg)
![](images/4.jpg)

### Rev 1.2


![](images/2_1.jpg)
![](images/2_2.jpg)
