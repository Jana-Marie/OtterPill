# OtterPill

OtterPill is a 3$ STM32F072 devboard featuring USB 2.0 full-speed, a DFU Bootloader, a USB-PD Phy and Arduino nano alike pinout and size.

Changelog V1.2: BOM cost reduction by ~40%, PCB can be fully populated by JLCSMT, more efficient buck converter (PCB gets less warm at 20V), GND-hook for probing, Reset-Pin exposed as pad, power pads for 20V/5A

**How do I get an OtterPill?** 

Via [tindie](https://www.tindie.com/products/jan_henrik/otterpill/) (if sold out DM via Twitter, I might have a few left ;))

## Building, Flashing and Frameworks

### Via Makefile and DFU (C, C++)

Or you can generate a basic firmware, with HAL init and Makefile, with CubeMX. The binary can then be build with make and flashed with dfu-utils. To enter DFU mode, press and hold the Button while plugging in power.

    $ make
    $ dfu-util -a 0 -s 0x08000000:leave -D build/firmware.bin

### Via Arduino

[You can build and flash the firmware via Arduino as described here.](https://github.com/stm32duino/Arduino_Core_STM32)

### Via PlatformIO

[https://gist.github.com/ansemjo/ab1c12f7c78abb140f7272501aff2a55](https://gist.github.com/ansemjo/ab1c12f7c78abb140f7272501aff2a55) Thank you [ansemjo](https://github.com/ansemjo) :3

### Via Nodate (野点) (C++, Ada)

[https://github.com/MayaPosch/Nodate](https://github.com/MayaPosch/Nodate)

### Rust

Thank you [@jamesmunns](https://github.com/jamesmunns)! :3

[https://github.com/jamesmunns/OtterPill-rs](https://github.com/jamesmunns/OtterPill-rs)

## Schematic

[HW v1.2/OtterPill.pdf](HW%20v1.2/OtterPill.pdf)

## Pinout

![](pinout.png)

Pinout by [SarahhhhFoster](https://github.com/SarahhhhFoster) :)

## Examples and projects

### Blink example firmware

[Blink/](Blink/)

### STM workshop based on OtterPill

[https://github.com/Jan--Henrik/hackerhotel-stm-workshop](https://github.com/Jana-Marie/hackerhotel-stm-workshop)

![](https://github.com/Jana-Marie/hackerhotel-stm-workshop/blob/master/monochrome_c.gif)

### USB-PD example firmware

This is a working USB-PD example using ChibiOS, a new voltage can be requested by pressing the Button.

[https://github.com/Jan--Henrik/USB-PD-Firmware](https://github.com/Jana-Marie/USB-PD-Firmware)

### IBM dials retrofit

[https://github.com/Jan--Henrik/IBM-dials-retrofit](https://github.com/Jana-Marie/IBM-dials-retrofit)

<img src="https://raw.githubusercontent.com/Jan--Henrik/IBM-dials-retrofit/4c27e5c5fda3bd528e12d15f71b0f5aaa8c24b97/images/1.jpeg" width="600">

## Shields and addons

Most Arduino shields should be compatible.

#### [USB-to-CAN-adapter](https://github.com/Jana-Marie/OtterPill-CAN-Adapter)

## Todo for HW v1.3

 - [x] Replace U1 with ESDU5V0H4
 - [x] ~~Add a TVS Diode to VBUS (e.g. SJD12A22L01)~~ -> Added series resistor to reduce ringing
 - [ ] Remove R8, R9
 - [x] ~~Redraw the FUSB302B Symbol~~ -> forgot why, works great
 - [x] ~~Consider switching to STUSB4500 (Easier PD requesting, same price)~~ -> FUSB works great, no need to change
 - [x] Add VBUS ADC
 
 
## Special thanks

[@jamesmunns](https://github.com/jamesmunns) for creating the Rust examples.

[@MayaPosch](https://github.com/MayaPosch) for creating the Nodate framework and adding the OtterPill.

[@ansemjo](https://github.com/ansemjo) for creating a PlatformIO configuration.

[@SarahhhhFoster](https://github.com/SarahhhhFoster) for creating the awesome pinout diagram.


## Images

![](images/1.jpg)
![](images/2.jpg)

### Rev 1.1

![](images/3.jpg)
![](images/4.jpg)

### Rev 1.2


![](images/2_1.jpg)
![](images/2_2.jpg)
