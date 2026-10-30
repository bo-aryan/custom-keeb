# custom-keeb
# Custom 8-Key Mechanical Media Macropad

A custom 8-key mechanical macropad designed from scratch as a two-layer PCB around an RP2040-based Orpheus Pico, featuring a diode-isolated switch matrix, per-key RGB lighting, a rotary encoder, and an external OLED display. Designed primarily for controlling music and video playback, with programmable shortcuts for desktop applications.

## Overview

This project is a compact custom mechanical macropad built around an RP2040-based Orpheus Pico.

I designed the electrical system, schematic, PCB layout, component placement, routing, and production files. The board integrates an 8-key switch matrix, addressable RGB lighting, a rotary encoder, and an external I2C OLED display into a compact two-layer PCB.

Unlike a conventional keyboard, the macropad is designed around media and desktop controls. Its keys provide dedicated controls for track navigation, playback, Spotify, and Windows shortcuts, while the rotary encoder handles system volume.

The firmware is being developed using CircuitPython, with USB HID for keyboard and media commands. A companion Windows application communicates with the macropad over USB serial to retrieve active media-session information and display song metadata and playback progress on the OLED.

The goal was to design the complete hardware system, understand how its components interact, and develop firmware that turns the PCB into a functional desktop peripheral.

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

## Key Engineering Decisions

### 1. Diode-Isolated Switch Matrix

The eight mechanical switches are arranged in a three-row, three-column matrix, with the encoder occupying the remaining position in the top row.

Each switch has its own 1N4148 diode to prevent unwanted current paths during simultaneous key presses.

The matrix provides an efficient way to scan multiple switches while minimizing the number of GPIO connections required by the controller.

The firmware maps the populated matrix positions to dedicated media and desktop shortcuts.

### 2. Addressable RGB

The board incorporates 10 SK6812 MINI-E addressable RGB LEDs.

The LEDs are connected in a daisy chain using a single data connection:

```text
GP10
 │
 ▼
LED 1 → LED 2 → LED 3 → ... → LED 10
```

This allows the LEDs to be controlled independently through firmware.

The lighting system is intended to provide visual feedback for playback status, key activity, and other macropad states.

### 3. Rotary Encoder

An EC11 rotary encoder provides three inputs:

- Encoder A → GP7
- Encoder B → GP8
- Encoder switch → GP9

The encoder serves two functions:

- Clockwise and anticlockwise rotation control system volume.
- Pressing the encoder toggles mute/unmute.

This provides dedicated volume control without requiring additional keyboard shortcuts.

### 4. OLED Interface

The 0.91-inch OLED connects through an external 1×4 I2C connector, allowing the display to remain separate from the main PCB.

```text
J1
├── GND
├── 3V3
├── SCL → GP21
└── SDA → GP20
```

The OLED is intended to display live media information retrieved from the connected Windows computer, including:

- Current song title
- Artist name
- Playback status
- Elapsed playback time
- Remaining playback time
- Playback progress bar

The display also provides feedback for volume adjustments and other macropad actions.

A companion Python application retrieves media information through Windows' Global System Media Transport Controls interface and sends updates to the RP2040 over USB serial.

### 5. Mechanical Layout

The PCB accommodates eight MX-style mechanical switches and an EC11 rotary encoder in a compact three-row arrangement.

The supporting components are positioned relative to the switch layout:

- RGB LEDs: +5.08 mm from the switch position
- Diodes: +10.00 mm from the switch position
- Four M3 mounting holes
- Controller positioned at the board edge for USB access

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

## PCB Design

The PCB was designed as a two-layer board using KiCad.

### Routing

The design uses both copper layers for routing, with vias used where necessary to move between layers.

Ground connectivity is provided through copper fills rather than routing every ground connection individually.

### Schematic

The schematic defines the complete electrical system, including:

- RP2040-based controller
- 8-switch matrix
- 1N4148 switch diodes
- SK6812 RGB LED chain
- EC11 rotary encoder
- External OLED connector
- Power and ground connections

## Design Files

All source files are included in the project repository.

| File | Purpose |
|---|---|
| `hardware/` | KiCad source files |
| `production/gerbers.zip` | Manufacturing files |
| `production/bom.csv` | Bill of materials |
| `docs/schematic.pdf` | Readable schematic export |
| `firmware/` | CircuitPython firmware and Windows companion application |

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

## Final Result

The project brings together custom PCB design, mechanical switches, addressable RGB lighting, rotary input, embedded firmware, and desktop software into a dedicated media-control peripheral.

Beyond designing the physical board, the project explores how a custom hardware interface can communicate with a desktop operating system to control applications and display live information.

The KiCad source, manufacturing files, bill of materials, firmware, and supporting documentation are maintained as part of the project repository.

## Acknowledgements

Built using KiCad and inspired by Hack Club's KEEB PCB-design resources.

The project is my own hardware design and implementation.
