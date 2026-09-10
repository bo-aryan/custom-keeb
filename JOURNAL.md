Journal

September 1, 2026
Time spent: ~1 hour

i've started designing the control interface PCB in KiCad.
Completed:
- 10-key 2×5 switch matrix
- 1N4148 diodes
- Orpheus Pico pin mapping
- EC11 rotary encoder
- 0.91" OLED connector

i initially wired part of the matrix incorrectly, then corrected it so
all five columns share ROW0/ROW1 properly.

Next:
- Add SK6812 MINI-E LEDs
- Finish schematic
- Run ERC
<img width="1231" height="805" alt="image" src="https://github.com/user-attachments/assets/29657d00-6524-4fd6-a6bc-74eaa1aa28b2" />

September 7, 2026
Time spent: 45 mins

i continued the KiCad schematic for the custom keyboard.

Completed:
- Added 10 SK6812 MINI-E RGB LEDs using the marbastlib symbols
- Connected the LEDs in a DIN to DOUT daisy chain
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

September 8, 2026

Time spent: 1.5hrs in the morning-afternoon

I continued working on the PCB design in KiCad.

Completed:
- Assigned footprints to all schematic components
- Added M3 mounting-hole footprints
- Assigned the EC11 rotary encoder and OLED connector footprints
- Updated the PCB from the schematic
- Created the initial board outline
- Arranged the 10 MX switches into a 5×2 layout
- Set exact 19.05 mm center-to-center switch spacing
- Placed the Orpheus Pico, rotary encoder, and OLED connector
- Started placing the SK6812 MINI-E LEDs and 1N4148 diodes
- Verified the intended marbastlib LED offset of 5.08 mm from the MX switch center

Notes:
- Took extra care to verify component placement before continuing to avoid mechanical alignment issues.
- The board outline is still temporary and will be resized after component placement is finalized.

Next:
- Numerically verify LED placement for each switch
- Finish placing LED6–LED10 and D6–D10
- Place the mounting holes
- Finalize the board outline
- Begin routing

September 9, 2026 
Time spent: 1.5 hrs

i continued routing the PCB in KiCad.

Completed:
- Routed all 10 switch-to-diode connections
- Routed ROW0 to GP0
- Routed ROW1 to GP1
- Routed COL0–COL4 to GP2–GP6
- Used F.Cu and B.Cu to avoid routing conflicts
- Routed the EC11 encoder signals to GP7, GP8, and GP9
- Left encoder ground connections for the later GND copper fill
- Verified the matrix and encoder routing as I went

Next:
- Route OLED SDA/SCL
- Route OLED power
- Route the SK6812 MINI-E LED chain
- Add GND copper fill
- Run DRC and fix any errors
<img width="1085" height="768" alt="image" src="https://github.com/user-attachments/assets/858b1a82-c268-4423-9535-c8ea36e91b77" />

September 10, 2026

Time spent: 2 hrs

i continued routing and finishing the PCB in KiCad.

Completed:
- Finished the OLED 3V3 connection
- Routed the SK6812 MINI-E LED data chain
- Confirmed LED10 DOUT is intentionally left unconnected
- Routed the RGB VBUS power network to the Pico
- Added B.Cu and F.Cu GND copper fills
- Verified that copper gaps around traces/keepouts are expected
- Ran DRC for the first time

Current issue:
- DRC reports 74 errors and 19 warnings
- I have not started fixing these yet because I want to classify the errors first instead of changing things blindly

Next:
- Review the DRC error list
- Group errors by type
- Fix clearance/short/unconnected issues systematically
- Re-run DRC until clean
- Final silkscreen/board cleanup
- Export Gerbers and final project files
<img width="676" height="438" alt="image" src="https://github.com/user-attachments/assets/189bd666-b45b-4cbe-9844-554f983e478e" />
