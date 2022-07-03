# Ptechinos

## Description
A crossover between Pteron36 and Balbuzard with 36 keys (kailh choc v1).
  - 5x3 keys layout + 3 thumb keys
  - 2 optional encoders (EVQWGD001) or keys
  - Outer columns for top pinky (reduce hand torsion)
  - Small splay to adjust to natural hand shape


**Drawings made with love by [pandhara](https://www.artstation.com/pandhara).**



# Versions
All production files are in `data/production` :
  - `gerber` : files needed to manufacture the keyboard PCB
  - `plates` : 2D/3D files to build the sandwich case


## V0.1 - ⚰️

  - 36 keys + 2 optional encoder (EC11)
  - Pro micro footprint
  - TRRS / TRS jack to connect both halves
  - Reset

**No production files.**

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



## V0.6 - 🚧

  - Improve routing
  - Bottom plate uses 15cm magnet holes
  - Choc v1 spacing

**Work in progress.**


# PCB/Solder Mask Colors

![HackADay](https://hackaday.com/wp-content/uploads/2018/05/colorswatches.jpg?w=800)

A detail description of available colors for PCB manufacturing by [Ben Vallack](https://www.youtube.com/watch?v=3PSUh6gRJk8).
