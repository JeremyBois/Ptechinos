# Ptechinos
## Description
**Ptechinos** is an ergonomic keyboard inspired by [Pteron36](https://github.com/harshitgoel96/pteron36-split-keyboard) and [Balbuzard](https://github.com/brow/balbuzard):

  - 36 keys (kailh choc v1)
  - 5x3 keys layout + 3 thumb keys
  - 2 optional encoders (EVQWGD001) or keys
  - Outer columns for top pinky (reduce hand torsion)
  - Small splay to adjust to natural hand shape


**Drawings made with love by [pandhara](https://www.artstation.com/pandhara).**

* [QMK layout](https://github.com/JeremyBois/qmk-ptechinos)



# Versions
All production files are in `data/production` :
  - `gerber` : files needed to manufacture the keyboard PCB
  - `plates` : 2D/3D files to build the sandwich case


## V0.6 - 🚧

  - Improve / clean routing
  - Bottom plate
    - Uses 15cm magnet holes
    - Remove standard 1/4 holes
    - Add a hole to fit splitkb tenting kit on the bottom plate
  - Choc v1 spacing (with 1mm between keys)
  - Cirque trackpad support using I2C connection and FPC connector
  - OLED support using I2C connection
  - Board dimensions (hxl): 113.27x158.54mm


**Work in progress.**


## V0.5 - ✅

  - Update ergogen config
    - automatic plates generation (2d/3d)
    - remove pcb components (unused)
    - add bottom magnets / camera mounts holes
    - add preview drawing to make easier to visualize plates stack
  - Update pcb board constraints with more aggressive minimums
  - Update PCB according to new ergogen plate config
  - PCB
    - Improve silkscreens ajustements
    - More aggresive thumb angle
    - Lower thumbs keys
    - Encoder angle is now the same as the thumb key below
    - Update board dimensions
  - Bottom plate uses 15cm magnet holes

**Wired version is fully tested** : see used [QMK layout](https://github.com/JeremyBois/qmk-ptechinos).


Left           |  Right
:-------------------------:|:-------------------------:
![Left](./data/production/v0.5/top.svg?sanitize=true)  |  ![Right](./data/production/v0.5/bottom.svg?sanitize=true)

![Electrical schema](./data/production/v0.5/schema.svg?sanitize=true)



## V0.4 - ⚰️

  - Update Readme
    - Add credits
    - Add pictures
    - Add notes for available mask colors
  - Update silkscreen drawings with final version
  - Consistent hole size in switch footprints
  - Generate STL files for plate mounting
  - Make encoder (EVQWGD001) footprint reversible using SMD jumpers
    - Require to bridge jumpers on the same side as the encoder
  - Bottom plate uses 10cm or 15cm magnet holes

**Untested.**



## V0.3 - ⚰️

  - Replace vertical encoder (EC11) with horizontal one (EVQWGD001)
  - Better tracing
  - Add teardrops
  - Mounting
    - Correct mounting holes size
    - Add MCU guard holes
    - Complete plates (top / bottom)
  - Add logo to silkcreen (draft)
  - Find keyboard name
  - Bottom plate uses 10cm magnet holes

**Untested.**



## V0.2 - ⚰️

  - Add bluetooth components
    - On/off switch
    - Capacitor
    - Battery support
      - JST female to avoid to solder the battery
      - pins also available if soldering is needed/wanted
  - Mounting
    - Add Mounting holes (draft)
    - Add plates (draft)

**No production files.**



## V0.1 - ⚰️

  - 36 keys + 2 optional encoder (EC11)
  - Pro micro footprint
  - TRRS / TRS jack to connect both halves
  - Reset

**No production files.**




### Notes
  - Choc spacing at least vertically
    - 💚 easier vertical combos
    - 💚 less finger extension

  - Try [chicago stenographer](https://www.asymplex.xyz/product/cs-chicago-stenographer-profile) keycaps
    - R2  == row3 (schema) == bottom row
    - R3  == row2 (schema) == home row
    - R4  == row1 (schema) == top row
    - Thumbs
      - 1 x [R3X Convex 1U](https://www.asymplex.xyz/product/chicagosteno-convex-caps)
      - 2 x [T15 Thumb](https://www.asymplex.xyz/product/chicagosteno-convex-caps)

  - [Avoid Trrs shorting](https://www.reddit.com/r/MechanicalKeyboards/comments/a641ls/split_keyboard_trrs_shorting_and_protection/)

  - Add support for a GlidePoint Cirque circular trackpad (35mm) using I2C
    - Models
      - [Adhesive overlay](https://www.mouser.fr/ProductDetail/Cirque/TM035035-2024-001?qs=wd5RIQLrsJjQWLerbkGS5g%3D%3D)
      - [Curved overlay](https://eu.mouser.com/ProductDetail/Cirque/TM035035-2024-003?qs=wd5RIQLrsJiMSFF94ofOQw%3D%3D)
      - [Haptic response](https://eu.mouser.com/ProductDetail/Alps-Alpine/AFT14A903A?qs=CiayqK2gdcIKZolCNjqbxg%3D%3D)
    - 4.7k pull up resistor required for I2C connection
      - SDA <--> VCC
      - SCL <--> VCC
    - Connector adapter from
    - Trackpad PCB must be adapted
      - Remove **R1** (SPI --> I2C)
      - Remove **R7** and **R8** (3.3V --> 5V VCC)
    - Keeping serial to connect both halves
    - Components on PCB
      - [FPC Connectors 0.5MM 12 POS](https://eu.mouser.com/ProductDetail/Hirose-Connector/FH12-12S-0.5SH55?qs=Ux3WWAnHpjA1i1nP49r1%2FQ%3D%3D) (footprint already in Kicad)
      - [4.7ohm resistor SMD CaseCode=2012mm](https://eu.mouser.com/c/passive-components/resistors/?case%20code%20-%20mm=2012&resistance=4.7%20Ohms&termination%20style=SMD%2FSMT&instock=y)
    - References
      - [qmk support](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_pointing_device.md)
      - [build log corne](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)
      - [Chunky V2](https://kbd.news/Chunky-V2-1219.html)
      - [i2c wiring](https://docs.qmk.fm/#/feature_split_keyboard)
      - buzzard (Correct trrs pins, resistors)



# PCB/Solder Mask Colors
![HackADay](https://hackaday.com/wp-content/uploads/2018/05/colorswatches.jpg?w=800)

A detail description of available colors for PCB manufacturing by [Ben Vallack](https://www.youtube.com/watch?v=3PSUh6gRJk8).


