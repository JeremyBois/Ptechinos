# Ptechinos
## Description
**Ptechinos** is an ergonomic keyboard inspired by [Pteron36](https://github.com/harshitgoel96/pteron36-split-keyboard) and [Balbuzard](https://github.com/brow/balbuzard):



**Hardware**

  - 36 keys (kailh choc v1)
  - 5x3 keys layout + 3 thumb keys
  - 2 optional encoders (EVQWGD001) or keys (36 --> 38)
  - Outer columns for top pinky (reduce hand torsion)
  - Small splay to adjust to natural hand shape
  - Cirque trackpad
  - OLED screen

**Software**

  - [QMK layout](https://github.com/JeremyBois/qmk-ptechinos)

***
**Drawings and 3D case design made with love by [pandhara](https://www.artstation.com/pandhara).**
***


# Versions
All production files are in `data/production` :
  - `gerber`: files needed to manufacture the keyboard PCB
  - `plates`: 2D/3D files to build the **sandwich** case
  - `unibody`: 2D/3D files to build the **3D** case (starting from v0.6)


## V0.6 - 🚧

**Work in progress.**

### Changes

  - **PCB**
    - Improve / clean routing
    - Dimensions (hxl): 111x159mm
    - Choc v1 spacing (with 1mm between keys added)
    - Add support for I2C components:
      - Cirque trackpad with FFC/FPC connector
      - OLED with socketing / QWIIC (Require KP2040)
    - Update guard holes position and add another at the bottom (3 in total)
    - MCU and TRRS are now aligned to PCB top edge and each protrude slightly
    - Add support for [Asymplex ChicagoSteno T15 Thumb](https://www.asymplex.xyz/product/cs-ergo-sets)
      - Change right/left thumbs orientation (+-90°)
      - Increase spacing between thumbs (+5mm)
      - Reduce rotation between thumbs (-5°)
    - Change board connection for encoders to free KB2040 only 4 analog pins
      - From F5/F4 to D4/C6 pins
    - Make more space for encoder / optional key for MX keycaps (using [this adapter](https://www.thingiverse.com/thing:4504072))

  - **Sandwich case**
    - Bottom plate
      - Uses 15cm magnet holes
      - Replace standard 1/4 holes by splitkb tenting kit hole
    - Top plate
      - Encoder / Key (above thumbs cluster) excluded from plate

  - **Unibody case**
    - 3D case added
    - Support for both OLED and Cirque 35mm trackpad modules


  - **Misc**
    - Add bill of material (BOM)


Left           |  Right
:-------------------------:|:-------------------------:
![Left](./data/production/v0.6/top.svg?sanitize=true)  |  ![Right](./data/production/v0.6/bottom.svg?sanitize=true)

![Electrical schema](./data/production/v0.6/schema.svg?sanitize=true)

![Orientation](./data/production/v0.6/orientation.svg?sanitize=true)


### Bill of materials (BOM)

#### Base
Part name | Amount | Reference sourced | Notes | Links
:------------------------|:-------------------------:|:-------------------------:|:-------------------------|:-------------------------
PCB  | 2 | | See `data/production/v0.6/gerber` folder | [PCBWay](https://www.pcbway.com/), [JLCPCB](https://jlcpcb.com/), ...
*(Optional)* Hot Swap Sockets | 36 | Kailh Choc hotswap sockets | Choc version only | [Splikb](https://splitkb.com/collections/keyboard-parts/products/kailh-hotswap-sockets?variant=39472161456205)
Diodes | 38 | 1N4148_SOD-123 | You can either use through hole or surface mount diodes (SMD) | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/smd-diodes)
Kailh Choc switch | 36 (38) | PG1350 | Only choc switches not MX | [Splitkb](https://splitkb.com/collections/switches-and-keycaps/products/kailh-low-profile-choc-switches)
Encoder horizontal | 1/2 | Panasonic_EVQWGD001 | Both sides on QMK and only the master side on ZMK | [Aliexpress](https://fr.aliexpress.com/item/1005003613012575.html)
*(Optional)* Tactile push button | 1/2 | 1TS002A-2500-4300 | Can be replaced with a pair of tweezer or using on board push buttons if any | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/reset-buttons?variant=42291963527427)
*(Optional)* Tenting puck | 1/2 | Splitkb_TentingPuck | 1/4th inch threaded tripod mounting hole | [Splitkb](https://splitkb.com/products/tenting-puck)


#### Bluetooth
Part Name | Amount | Reference sourced | Notes | Links
:------------------------|:-------------------------:|:-------------------------:|:-------------------------|:-------------------------
Battery | 2 | DEAH 301030 | This size could fit under the microcontroller but be free to order another one | [Aliexpress](https://fr.aliexpress.com/item/1005003635594999.html)
*(Optional)* On/Off switch | 2 | TLZWLA_MSK22D18<br>NewRise_MSS22D18 | Allow to turn off the battery power drain during transport | [Aliexpress](https://fr.aliexpress.com/item/4000681551007.html)<br>[Aliexpress](https://fr.aliexpress.com/item/32819941320.html)
*(Optional)* Battery JST PH connector | 0/1/2 | S2B-PH-K-S(LF)(SN) | You can also solder the battery directly to the pins of the PCB | [Splitkb](https://splitkb.com/products/wireless-controller-expansion-bundle)
Nice!nano | 2 | | Cannot be used with QMK due to license issues but works with ZMK | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/nice-nano)
*(Optional)* Decoupling capacitor 4.7uF | 2 | Samsung Electro-Mechanics CL21A475KPFNNNE  | The capacitors mitigate power surge when turning on the battery (already present on Nice!nano boards) | [Mouser](https://eu.mouser.com/ProductDetail/Samsung-Electro-Mechanics/CL21A475KPFNNNE?qs=yOVawPpwOwmSlN4VFiPp3g%3D%3D)

#### Wired
Part Name | Amount | Reference sourced | Notes | Links
:-------------------------|:-------------------------:|:-------------------------:|:-------------------------|:-------------------------
TR(R)S cable | 1 | TRRS | Both TRS or TRRS will work but only tested with a TRRS | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/braided-trrs-cable)
TRRS connectors  | 2  | PJ-320A | | [Splikb](https://splitkb.com/collections/keyboard-parts/products/trrs-jacks)
MCU board with ProMicro footprint | 0/2 | Adafruit_KP2040-RP2040 | ProMicro ATmega32u4 (AVR) <br>EliteC ATmega32u4 (AVR)<br>SparkFun Pro Micro - RP2040 (ARM)<br>Adafruit KP2040 - RP2040 (ARM) | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/pro-micro-atmega32u4-5v-16mhz)<br>[Splitkb](https://splitkb.com/collections/keyboard-parts/products/elite-c-low-profile-rev4-microcontroller)<br>[Mouser](https://eu.mouser.com/ProductDetail/SparkFun/DEV-18288?qs=sGAEpiMZZMuqBwn8WqcFUipNgoezRlc4noxtIIPbKIobERy9diiGVg%3D%3D)<br>[Adafruit](https://www.adafruit.com/product/5302)


#### Trackpad
Part Name | Amount | Reference sourced | Notes | Links
:-------------------------|:-------------------------:|:-------------------------:|:-------------------------|:-------------------------
Cirque trackpad | 1/2 | Cirque_TM035035-2024-002 | Unibody case required 35mm version but any size would work on the sandwich case | [Mouser](https://eu.mouser.com/ProductDetail/355-TM0350352024-002)
FFC jumper cable | 1/2 | Molex_15166-0123 | One on each side where a trackpad is added | [Mouser](https://eu.mouser.com/ProductDetail/538-15166-0123)
FPC connector | 1/2 | GCT_FFC2B35-12-G | One on each side where a trackpad is added | [Mouser](https://eu.mouser.com/ProductDetail/640-FFC2B35-12-G)
4.7kΩ Resistor (I2C) | 2/4 | Panasonic_ERA-6AEB472V | 2 Pull-up resistors for I2C connection are required at least on the master side | [Mouser](https://eu.mouser.com/ProductDetail/667-ERA-6AEB472V)


#### OLED screen
Part Name | Amount | Reference sourced | Notes | Links
:-------------------------|:-------------------------:|:-------------------------:|:-------------------------|:-------------------------
SSD1306 OLED 128x32 | 1/2 | | Works with both ARM and AVR MCU on QMK | [Splitkb](https://splitkb.com/collections/keyboard-parts/products/oled-display?variant=31716335616077)
4.7kΩ Resistor (I2C) | 2/4 | Panasonic_ERA-6AEB472V | 2 Pull-up resistors for I2C connection are required at least on the master side | [Mouser](https://eu.mouser.com/ProductDetail/667-ERA-6AEB472V)


#### 3D case
Part Name  | Amount | Notes | Links
:-------------------------|:-------------------------:|:-------------------------|:-------------------------
Top plate | 2 | See `data/production/v0.6/unibody` folder for DXF / STL files |
3D Case (left) | 1 | See `data/production/v0.6/unibody` folder for DXF / STL files |
3D Case (right) | 1 | See `data/production/v0.6/unibody` folder for DXF / STL files |
M2 Screws | 16 |  For M2 spacers | [Splitkb](https://splitkb.com/products/m2-screws?variant=42429972709635)
M2 Case Spacers | 10 | 6mm works fine (PCB = 1.6mm, PCB to switch  = 2.2mm, socket = 1.8mm) | [Splitkb](https://splitkb.com/products/brass-m2-spacers?_pos=2&_sid=9df1e01bc&_ss=r)
M2 Guard Spacers | 6 | TODO |


#### Sandwich case
Part Name  | Amount | Notes | Links
:-------------------------|:-------------------------:|:-------------------------|:-------------------------
Top plate  | 2 | See `data/production/v0.6/plates` folder for DXF / STL files |
Bottom plate  | 2 | See `data/production/v0.6/plates` folder for DXF / STL files |
M2 Screws | 16 |  For M2 spacers | [Splitkb](https://splitkb.com/products/m2-screws?variant=42429972709635)
M2 Case Spacers | 10 | 4/6mm works fine depending of the length of used M2 screws| [Splitkb](https://splitkb.com/products/brass-m2-spacers)
M2 Guard Spacers | 6 | TODO |



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


Left           |  Right
:-------------------------:|:-------------------------:
![Left](./data/production/v0.5/top.svg?sanitize=true)  |  ![Right](./data/production/v0.5/bottom.svg?sanitize=true)

![Electrical schema](./data/production/v0.5/schema.svg?sanitize=true)

![Orientation](./data/production/v0.5/orientation.svg?sanitize=true)

**Wired version is fully tested** : see used [QMK layout](https://github.com/JeremyBois/qmk-ptechinos).



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

  - 36 keys + 2 optional encoders (EC11)
  - Pro micro footprint
  - TRRS / TRS jack to connect both halves
  - Reset

**No production files.**




# Notes

## Todo (v0.6)

  - [x] Add support for a GlidePoint Cirque circular trackpad using I2C
    - [Secifications](https://www.dropbox.com/s/2l2cywvwxdfnoyw/GP-DS-170409%20TM035035%20SPI-I2C%20PINN%20Trackpad%20Spec.pdf?dl=0)
    - [Schematic](https://www.dropbox.com/s/vk752nkoqo7jbqw/02-000611-00RevA01_TM035035-2024-000_SCH.pdf?dl=0)
    - Trackpad PCB must be adapted to be used with Elite-C MCU
      - Remove **R1** (SPI --> I2C)
      - Remove **R7** and **R8** (3.3V --> 5V VCC)
    - References
      - [QMK - trackpad support](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_pointing_device.md)
      - [QMK - i2c wiring](https://docs.qmk.fm/#/feature_split_keyboard)
      - [Trackpad on corne](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)
      - [Trackpad on Chunky V2](https://kbd.news/Chunky-V2-1219.html)

  - [x] Drawings on silkscreen should be more uniform on stroke thickness

  - [x] Add RP2040 MCU board in a ProMicro footprint
    - More SRAM to enable more stuff (RGB leds, pointing devices, OLED, ...)
    - Better pointing device experience ([smoother trackpad experience](https://www.reddit.com/r/ErgoMechKeyboards/comments/w6r7on/comment/ihfko44/?utm_source=share&utm_medium=web2x&context=3))
    - **QWIIC** connector for easy to plug I2C devices

   - [x] Add OLED support
     - [QMK support](https://docs.qmk.fm/#/feature_oled_driver?id=basic-configuration)
     - [SSD1306 Monochrome 1.3" 128x64 - QWIIC](https://www.adafruit.com/product/938)
     - [SSD1306 Monochrome 0.96" 128x64 - pins](https://splitkb.com/products/oled-display?variant=31226608549965)
     - [SSD1327 Grayscale 1.5" 128x128 - QWIIC (RP2040 required and no QMK support)](https://www.adafruit.com/product/4741)

  - [x] Try [chicago stenographer](https://www.asymplex.xyz/product/cs-chicago-stenographer-profile) keycaps
    - R2  == row3 (schema) == bottom row
    - R3  == row2 (schema) == home row
    - R4  == row1 (schema) == top row
    - Thumbs
      - 1 x [R3X Convex 1U](https://www.asymplex.xyz/product/chicagosteno-convex-caps)
      - 2 x [T15 Thumb](https://www.asymplex.xyz/product/chicagosteno-convex-caps)
      - [x] Check stem required orientation for outer and inner thumbs (see with asymplex)

  - [ ] Try **QWIIC** as a hotswapable I2C with integrated pull-up resistors
    - [Joystick](https://www.sparkfun.com/products/15168)
    - [Adapter](https://www.sparkfun.com/products/14495)
      - SDA and SCL are reversed making it non-compatible with OLED exposed connectors
      - Using a [4-pins jumper](https://www.sparkfun.com/products/14425) is a better idea

  - [ ] Try Female Threaded 1/4" Standoffs in Unibody case instead of Splikb tenting puck
    - [Female Threaded Hex Standoffs ](https://www.mcmaster.com/standoffs/thread-size~1-4-20/length~1-4/)

  - [ ] Try [Choc to MX converter](https://www.thingiverse.com/thing:4504072) with custom artisan

  - [ ] Handle software difference between RP2040 and Atemega32U4 on QMK side



## PCB/Solder Mask Colors
![HackADay](https://hackaday.com/wp-content/uploads/2018/05/colorswatches.jpg?w=800)

A detail description of available colors for PCB manufacturing by [Ben Vallack](https://www.youtube.com/watch?v=3PSUh6gRJk8).
Following colors can be used to get a correct approximation (without the gloss effect):

  - Yellow = `#D5B619`
  - Blue = `#213754`
  - Red = `#cc0000`
  - White = `#A7B5C2`
  - Black (matte) = `#353B3E`
  - Black (gloss) = `#131718`
  - Green (matte) = `#006F52`
  - Green (gloss) = `#005A44`
  - Copper Pad (gloss grey) = `#AFAF98`
  - Purple = `#4b0082`




## I2C and pull-up
  - [I2C tutorial](https://learn.sparkfun.com/tutorials/i2c)
  - [Good explanation of I2C pull-up resistors](https://www.bluedot.space/tutorials/how-many-devices-can-you-connect-on-i2c-bus/)
    - The I2C bus specification defines a maximum of *0.4V* for the low-level output voltage
    - Multiple devices can be on the same line if pull-up resistors are big enough

$$
\begin{aligned}
& R_{VCC} = \frac{VCC - 0.4}{3mA} \\\\
& R_{5} = \frac{5 - 0.4}{3} = 1.53kΩ \\\\
& R_{3.3} = \frac{3.3 - 0.4}{3} = 967Ω
\end{aligned}
$$

  - By connecting each device in parallel we decreased by the same amount the total resistance

  - Ptechinos use 4.7kΩ resistors for the second I2C line (SDA1 / SCL1)
    - 4.7kΩ resistors on 3.3V VCC allows up to $4$ devices ($\frac{1}{\frac{4}{4.7}} = 1.175kΩ$)

  - [SSD1306 Monochrome 1.3" 128x64 - QWIIC](https://www.adafruit.com/product/938)
    - Include with [2K resistors](https://cdn-shop.adafruit.com/datasheets/UG-2864HSWEG01+user+guide.pdf)
    - Address is software controled allowing multiple screen to be connected on the same bus/line
    - At most 2 screens (($\frac{1}{\frac{2}{2.2}} = 1.1kΩ$)) with a KB2040 board

  - [Sparkfun joystick](https://www.sparkfun.com/products/15168) with QWIIC interface
    - Op-out I2C pullup (2.2kΩ)[](https://cdn.sparkfun.com/assets/7/4/a/6/8/Qwiic_Joystick.pdf)
    - At most 2 joystick (($\frac{1}{\frac{2}{2.2}} = 1.1kΩ$)) with a KB2040 board


## V0.5 VS v0.6

Distance              | v0.6            | v0.5             | Result    |
|---------------------|-----------------|------------------|-----------|
Top to FarThumbs      | [69.31, 88.91]  | [70.905, 93.735] |  [✅, ✅] |
Top to InnerThumbs    | [28.970, 67.89] | [31.885, 72.075] |  [😑, ✅] |
Encoder to HomeThumbs | [3.432]         | [4.096]          |  [😑, 😑] |
Top to OuterPinky     | [58.57, 37.64]  | [59.665, 40.315] |  [✅, ✅] |
Home to HomeThumbs    | [30.11, 52.55]  | [32.246, 54.7]   |  [✅, ✅] |
