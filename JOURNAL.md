Journal

September 1, 2026 — Initial Schematic
Time spent: ~1 hour

Started designing the control interface PCB in KiCad.
Completed:
- 10-key 2×5 switch matrix
- 1N4148 diodes
- Orpheus Pico pin mapping
- EC11 rotary encoder
- 0.91" OLED connector

I initially wired part of the matrix incorrectly, then corrected it so
all five columns share ROW0/ROW1 properly.

Next:
- Add SK6812 MINI-E LEDs
- Finish schematic
- Run ERC
<img width="1231" height="805" alt="image" src="https://github.com/user-attachments/assets/29657d00-6524-4fd6-a6bc-74eaa1aa28b2" />

September 7, 2026 — RGB LEDs and Mechanical Setup

Time spent: 45 mins

Continued the KiCad schematic for the custom keyboard/control interface.

Completed:
- Added 10 SK6812 MINI-E RGB LEDs using the marbastlib symbols
- Connected the LEDs in a DIN → DOUT daisy chain
- Connected RGB data to GP10
- Powered the LEDs from VBUS and connected them to GND
- Added 4 mounting holes for the case
- Annotated the schematic components

Next:
- Assign footprints to all components
- Verify the schematic
- Run ERC
- Begin PCB layout
<img width="1307" height="480" alt="image" src="https://github.com/user-attachments/assets/30ddfbaf-7ecb-4de3-ab64-db30ef2121bb" />
