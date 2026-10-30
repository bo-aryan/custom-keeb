# custom-keeb

A custom 8-key mechanical macropad designed from scratch as a two-layer PCB around an RP2040-based Orpheus Pico, featuring a diode-isolated switch matrix, per-key RGB lighting, a rotary encoder, and an external OLED display. Designed primarily for controlling music and video playback, with programmable shortcuts for desktop applications.
<img width="680" height="901" alt="image" src="https://github.com/user-attachments/assets/04112c28-2fbd-4ab1-be7f-af00e3cb38d8" />

## Overview
- Designed an 8-key mechanical media macropad around an RP2040-based Orpheus Pico.
- Designed the complete two-layer PCB, including schematic, component placement, routing, and manufacturing files using KiCad.
- Integrated an MX switch matrix, SK6812 RGB LEDs, EC11 rotary encoder, and external I2C OLED.
- Developing CircuitPython firmware for media controls, programmable shortcuts, volume adjustment, and RGB lighting.
- Building a Python companion application to retrieve Windows media metadata and display song information and playback progress on the OLED.

## What I Learned

This project took me through the complete PCB design process rather than just the schematic stage.

The main learning areas included:

- Designing and routing a diode-isolated switch matrix
- Understanding PCB footprints and physical component placement
- Managing a two-layer PCB
- Routing around dense components
- Using vias and copper fills
- Connecting addressable RGB LEDs as a chain
- Integrating an encoder and I2C peripheral
- Understanding USB HID and media-control commands
- Developing firmware for an RP2040 microcontroller
- Integrating hardware with a Windows application through USB serial
- Running design-rule checks before manufacturing
- Preparing a PCB for fabrication

## PCB Design

The PCB was designed as a two-layer board using KiCad.
<img width="1176" height="813" alt="image" src="https://github.com/user-attachments/assets/faa14f22-027c-49e9-b503-3551ce2206c4" />


### Routing

The design uses both copper layers for routing, with vias used where necessary to move between layers.

Ground connectivity is provided through copper fills rather than routing every ground connection individually.

### Schematic
<img width="811" height="678" alt="image" src="https://github.com/user-attachments/assets/e4e067c9-d523-4f6f-8ad8-c9f8c10dfc2c" />

The schematic defines the complete electrical system, including:

- RP2040-based controller
- 8-switch matrix
- 1N4148 switch diodes
- SK6812 RGB LED chain
- EC11 rotary encoder
- External OLED connector
- Power and ground connections

## Case Design
<img width="1042" height="862" alt="image" src="https://github.com/user-attachments/assets/780291fb-5050-4de3-85ba-de4706a1434d" />

The macropad enclosure was designed using **Autodesk Fusion**, with the case modelled to accommodate the PCB, mechanical switches, rotary encoder, and external OLED display.

The enclosure was designed around the PCB dimensions and component placement to ensure proper fitment and accessibility. Particular attention was given to the switch openings, encoder placement, OLED visibility, and USB access.

The design brings the electronics and mechanical components together into a compact enclosure while maintaining the overall layout and functionality of the macropad.


## At a Glance

| Component | Specification |
|---|---|
| Controller | Orpheus Pico (RP2040) |
| Layout | 8-key macropad + encoder |
| Switches | 8 × MX-style mechanical switches |
| Key matrix | 3 rows × 3 columns, 8 populated positions |
| Switch diodes | 1N4148 |
| RGB | 10 × SK6812 MINI-E |
| Rotary encoder | EC11 |
| Display | 0.91" I2C OLED |
| PCB | 2-layer |
| EDA | KiCad |
| Firmware | CircuitPython |
| Communication | USB HID + USB serial |
| Companion software | Python (Windows) |

## Media-Control Functionality

The macropad is designed primarily as a dedicated music and video controller.

| Control | Function |
|---|---|
| Key 1 | Previous track |
| Key 2 | Play / Pause |
| Key 3 | Next track |
| Encoder press (Key 4) | Mute / Unmute |
| Key 5 | Launch Spotify Desktop |
| Key 6 | Windows + Shift + S (Snipping Tool) |
| Key 7 | Windows + Shift + T |
| Key 8 | Configurable shortcut |
| Key 9 | Configurable shortcut |
| Encoder clockwise | Volume up |
| Encoder anticlockwise | Volume down |

The two configurable keys can be assigned custom keyboard shortcuts through the firmware configuration.

USB HID allows the macropad to send standard keyboard and media-control commands without requiring a dedicated application for basic functionality.

## Firmware Architecture

The firmware is being developed using CircuitPython for the RP2040.

The software is divided into two components:

**1. Macropad Firmware**

- Matrix scanning and switch debouncing
- USB HID media and keyboard commands
- Rotary encoder input handling
- RGB LED control
- OLED updates
- USB serial communication

**2. Windows Companion Application**

- Retrieves active media-session information
- Reads song title and artist metadata
- Retrieves playback position and duration
- Calculates elapsed and remaining playback time
- Sends media information to the macropad over USB serial

This separation allows the hardware to handle physical inputs and outputs while the Windows application provides access to desktop media information.


## Design Files

All source files are included in the project repository.

| File | Purpose |
|---|---|
| `hardware/` | KiCad source files |
| `production/gerbers.zip` | Manufacturing files |
| `production/bom.csv` | Bill of materials |
| `docs/schematic.pdf` | Readable schematic export |
| `firmware/` | CircuitPython firmware and Windows companion application |

## Final Result

The project brings together custom PCB design, mechanical switches, addressable RGB lighting, rotary input, embedded firmware, and desktop software into a dedicated media-control peripheral.

Beyond designing the physical board, the project explores how a custom hardware interface can communicate with a desktop operating system to control applications and display live information.

The KiCad source, manufacturing files, bill of materials, firmware, and supporting documentation are maintained as part of the project repository.

## Acknowledgements

Built using KiCad and inspired by Hack Club's KEEB PCB-design resources.

The project is my own hardware design and implementation.
