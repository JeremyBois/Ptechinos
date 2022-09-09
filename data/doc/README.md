# Documentation

## Whislist

  - Trackball
    - [ ] Ball 25mm
    - [ ] Bearing balls 2.5mm zirconium oxide (G5)
    - [ ] Headers male for SPI + cables
    - [ ] Cable female headers to connect to male exposed on PCB
    - [ ] Breakout board
      - [PMW3360](https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor)
      - [PMW3389](https://www.tindie.com/products/jkicklighter/pmw3389-motion-sensor/)


## RP2040

   - QMK
     - [Conversion from Promicro (cocot46plus)](https://zhan.co.nl/posts/2022-08-24-cocot46plus-build-notes/#converting-to-rp2040)
    - [Conversion from Promicro (gherkin)](https://learn.adafruit.com/using-qmk-on-rp2040-microcontrollers?view=all)

   - Trackball
     - [Nano trackball + lot of projects / 3D](https://github.com/jfedor2/rp2040-pmw3360)


## Components
### Adafruit KB2040
  - [Product](https://www.adafruit.com/product/5302)
  - [Tutorial](https://learn.adafruit.com/adafruit-kb2040)

  - QMK support
    - [Pull request](https://github.com/qmk/qmk_firmware/pull/14877)

  - Builds
    - [Unichunky](https://www.reddit.com/r/ErgoMechKeyboards/comments/wizqo8/the_unichunky/)


### Trackball Pixart PMW3360 Motion sensor
  - Breakout board
    - [PMW3360](https://www.tindie.com/products/jkicklighter/pmw3360-motion-sensor)
    - [PMW3389](https://www.tindie.com/products/jkicklighter/pmw3389-motion-sensor/)

  - PCB
    - [3.3V](https://github.com/jfedor2/pmw3360-breakout)
    - [3.3V or 5V](https://github.com/Ariamelon/Ogen)
    - [Circular - Charybdis keyboard](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb)

  - Bearing ball
    - [1/8Inch bearing balls](https://www.amazon.fr/c%C3%A9ramique-roulement-pr%C3%A9cision-Nitrure-silicium/dp/B073XKSK2F)
    - [2.5mm zirconium oxide bearing balls](https://www.amazon.fr/map-roulement-c%C3%A9ramique-zirconium-pr%C3%A9cision/dp/B081SNSRYH/ref=sr_1_18?__mk_fr_FR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=2I8JTB4UX6ATJ&keywords=2.5mm+zirconium+oxide&qid=1661682383&sprefix=2.5mm+zirconium+oxide%2Caps%2C153&sr=8-18)

  - Ball
    - [25mm ball](https://www.amazon.com/CAOREN-16pcs-Billiard-Children-Accessories/dp/B0836WQQF5)
    - [34mm ball](https://www.amazon.fr/Perixx-PERIPRO-303-GBK-34mm-Trackball/dp/B08DD6GQRV/ref=sr_1_12?__mk_fr_FR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=D6O7OH602GWM&keywords=34mm+trackball&qid=1661681459&sprefix=34mm+trackballs%2Caps%2C271&sr=8-12)

  - CAD
    - [Oddball project](https://github.com/atulloh/oddball)
      - PMW3360 cover
      - Bearing mount

### Adafruit OLED SSD1306 Monochrome 1.3" 128x64
  - [Product](https://www.adafruit.com/product/938)

  - QMK support
    - [OLED](https://docs.qmk.fm/#/feature_oled_driver?id=basic-configuration)
    - [I2C wiring](https://docs.qmk.fm/#/feature_split_keyboard)


### Joystick SparkFun Qwiic (COM-15168)
  - [Product](https://www.sparkfun.com/products/15168)
    - **Seems to not be available in France at least on Mouser**

  - QMK support
    - [Joystick](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_joystick.md)
      - Can use I2C and send HID data to computer (ADC not required and not supported yet on QMK)
      - ADC does not yet works on QMK with RP2040
    - [I2C wiring](https://docs.qmk.fm/#/feature_split_keyboard)


### GlidePoint Cirque Trackpad TM035035
  - QMK support
    - [Trackpad](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_pointing_device.md)
    - [I2C wiring](https://docs.qmk.fm/#/feature_split_keyboard)
    - Trackpad PCB must be adapted to be used with KB2040
      - Remove **R1** (SPI --> I2C)

  - Documentation
    - [Secifications](https://www.dropbox.com/s/2l2cywvwxdfnoyw/GP-DS-170409%20TM035035%20SPI-I2C%20PINN%20Trackpad%20Spec.pdf?dl=0)
    - [Schematic](https://www.dropbox.com/s/vk752nkoqo7jbqw/02-000611-00RevA01_TM035035-2024-000_SCH.pdf?dl=0)

  - Builds
    - [On corne](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)
    - [On Chunky V2](https://kbd.news/Chunky-V2-1219.html)


### Others

   - Socket strips
     - [Low Profile Socket Strip (squared pins)](https://www.mouser.fr/ProductDetail/Samtec/CES-104-01-L-S?qs=PB6%2FjmICvI1cSb0fQjZcig%3D%3D)
   - Reset button (top or right angle)
     - [Trough hole](https://splitkb.com/collections/keyboard-parts/products/reset-buttons)
   - Tact switches for mouse buttons (requires a new row on pin 18)
     -  [Tact switches](https://en.jian-fu.com/product/48.html)
   - Male header right angle (Trackball pins)
     - [Sparkfun](https://www.sparkfun.com/products/553)

## Tools
  - [Ergogen (online)](https://ergogen.cache.works/)
  - [OpenScad](https://openscad.org/)
  - [Gerber viewer (online)](https://www.gerberviewer.io/view)


## References

  - [Dilemma](https://kbd.news/Dilemma-keyboard-1557.html)
  - [UniChunky](https://kbd.news/UniChunky-1579.html)
  - [Santoku](https://kbd.news/Santoku-Gen-2-842.html)
  - [Pteron36](https://github.com/harshitgoel96/pteron36-split-keyboard)
  - [Buzzard](https://github.com/crehmann/Buzzard)


## PCB manufacturing
  - [Comparator](https://pcbshopper.com/)
  - [PCBWay](https://www.pcbway.com/orderonline.aspx)
  - [Elecrow](https://www.elecrow.com/pcb-manufacturing.html)

### PCB/Solder Mask Colors
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


## Keycaps
  - [Asymplex](https://www.asymplex.xyz)


## Utilities
  - [Binding barrels](https://www.mcmaster.com/binding-barrels/)
  - [Female Threaded Hex Standoffs ](https://www.mcmaster.com/standoffs/thread-size~1-4-20/length~1-4/)
  - [Choc to MX converter](https://www.thingiverse.com/thing:4504072)

## Mounting system

  - [Modular Mounting System](https://www.thingiverse.com/thing:2194278)

## Notes
### I2C and pull-up
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

