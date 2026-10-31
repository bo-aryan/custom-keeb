Journal

September 1, 2026
Time spent: ~1 hour

i've started designing the control interface PCB in KiCad.
Completed:
- 8-key 2×5 switch matrix
- 1N4148 diodes
- Orpheus Pico pin mapping
- EC11 rotary encoder
- 0.91" OLED connector

i initially wired part of the matrix incorrectly, then corrected it so
all five columns share ROW0/ROW1 properly.
<img width="1231" height="805" alt="image" src="https://github.com/user-attachments/assets/29657d00-6524-4fd6-a6bc-74eaa1aa28b2" />

September 7, 2026
Time spent: 45 mins

i continued the KiCad schematic for the custom keyboard.

Completed:
- Added 8 SK6812 MINI-E RGB LEDs using the marbastlib symbols
- Connected the LEDs in a DIN to DOUT daisy chain
- Connected RGB data to GP10
- Powered the LEDs from VBUS and connected them to GND
- Added 4 mounting holes for the case
- Annotated the schematic components
<img width="1307" height="480" alt="image" src="https://github.com/user-attachments/assets/30ddfbaf-7ecb-4de3-ab64-db30ef2121bb" />

September 8, 2026

Time spent: 1.5hrs in the morning-afternoon

i continued working on the PCB design in KiCad.

Completed:
- Assigned footprints to all schematic components
- Added M3 mounting-hole footprints
- Assigned the EC11 rotary encoder and OLED connector footprints
- Updated the PCB from the schematic
- Created the initial board outline
- Arranged the 8 MX switches into a 3×3 layout
- Set exact 19.05 mm center-to-center switch spacing
- Placed the Orpheus Pico, rotary encoder, and OLED connector
- Started placing the SK6812 MINI-E LEDs and 1N4148 diodes
- Verified the intended marbastlib LED offset of 5.08 mm from the MX switch center

Notes:
- Took extra care to verify component placement before continuing to avoid mechanical alignment issues.
- The board outline is still temporary and will be resized after component placement is finalized.

September 9, 2026 
Time spent: 1.5 hrs

i continued routing the PCB in KiCad.

Completed:
- Routed all 8 switch-to-diode connections
- Routed ROW0 to GP0
- Routed ROW1 to GP1
- Routed COL0–COL4 to GP2–GP6
- Used F.Cu and B.Cu to avoid routing conflicts
- Routed the EC11 encoder signals to GP7, GP8, and GP9
- Left encoder ground connections for the later GND copper fill
- Verified the matrix and encoder routing as I went
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

Current issues:
- DRC reports 74 errors and 19 warnings
- I have not started fixing these yet because I want to classify the errors first instead of changing things blindly
<img width="676" height="438" alt="image" src="https://github.com/user-attachments/assets/189bd666-b45b-4cbe-9844-554f983e478e" />
<img width="841" height="702" alt="errors pic" src="https://github.com/user-attachments/assets/6b47c350-3a3b-4b7f-a319-54bb7f6543fc" />



September 23, 2026

Time spent: ~70 mins

I started preparing the dimensions for the MacroPad's 3D case.

Completed:

Measured the PCB dimensions in KiCad
Created the initial sketch using the PCB dimensions
Added an external sketch with 0.2 mm relief on each end
Created the boundary sketch
<img width="764" height="743" alt="image" src="https://github.com/user-attachments/assets/a829daef-24c4-4167-a1cd-8471ec7d9ed7" />


September 24, 2026

Time spent: ~85 mins

I continued developing the initial case structure.

Completed:

Added mounting holes according to the PCB dimensions
Adjusted hole diameters by 0.1 mm for a better fit
Curved the edges of the boundary
Added holes to connect the boundary with the top layer
<img width="483" height="539" alt="image" src="https://github.com/user-attachments/assets/7cae8bf4-ab5f-4192-8f9e-29445678cb4c" />


September 25, 2026

Time spent: ~60 mins

I started developing the bottom case structure.

Completed:

Added the area on which the PCB would rest
Extruded the initial structure by 2 mm
Created the PCB relief area
Started developing the base structure
<img width="889" height="577" alt="image" src="https://github.com/user-attachments/assets/ad2f3523-41ed-4575-908d-8ffe2b92f500" />


September 28, 2026

Time spent: ~75 mins

I continued designing the bottom case and its internal supports.

Completed:

Extruded the main structure
Added stands on which the PCB would rest
Created supports for the top layer
Imported the PCB STEP file into the CAD assembly
<img width="989" height="666" alt="image" src="https://github.com/user-attachments/assets/33235e92-3cf1-42e8-a21c-7c14a31ae8de" />


September 29, 2026

Time spent: ~80 mins

I worked on integrating the PCB into the case design.

Completed:

Checked the PCB placement inside the base
Verified that the PCB fitted correctly
Created the opening for the USB-C connection
Worked on refining the case edges
<img width="797" height="617" alt="image" src="https://github.com/user-attachments/assets/3802b978-008c-409b-987d-0a861b00b8b2" />

September 30, 2026

Time spent: ~65 mins

I continued developing the remaining parts of the case.

Completed:

Curved the remaining case edges
Created the layer that holds the PCB
Added the PCB holding layer to the assembly
Reviewed the overall case structure
<img width="724" height="561" alt="image" src="https://github.com/user-attachments/assets/765011dc-4ce3-4868-b961-85a368fbe92b" />


October 1, 2026

Time spent: ~55 mins

I started designing the top layer of the MacroPad case.

Completed:

Created a separate sketch for the top layer
Extruded the top layer to 2.5 mm thickness
Adjusted the support height to ensure it remained hidden
Reviewed the top and bottom case alignment

October 2, 2026

Time spent: ~85 mins

I continued working on the case assembly and integrated the rotary encoder.

Completed:

Added the rotary encoder to the case design
Checked its placement
Reviewed the complete case assembly
Checked the overall appearance of the MacroPad
<img width="750" height="648" alt="image" src="https://github.com/user-attachments/assets/6df3f0a1-0524-43ce-9bad-6cebf33a2e95" />


October 5, 2026

Time spent: ~70 mins

I reviewed the case dimensions and identified calculation errors in the previous design.

Completed:

Checked the dimensions of the case
Identified areas requiring corrections
Started revising the affected parts
Worked on improving the overall fit
<img width="861" height="469" alt="image" src="https://github.com/user-attachments/assets/76acc6eb-c9d9-491c-8446-6dc6c6e55bec" />

October 6, 2026

Time spent: ~60 mins

I continued refining the case after identifying issues with the original design.

Completed:

Corrected problematic case dimensions
Reworked the affected sections
Checked the PCB fit again
Improved the overall case structure
<img width="840" height="692" alt="image" src="https://github.com/user-attachments/assets/7cd715de-fec0-4d37-bf55-9df4a7119f05" />


October 7, 2026

Time spent: ~75 mins

I started exploring firmware development for the MacroPad.

Completed:

Explored CircuitPython and QMK
Looked into RP2040 compatibility
Considered OLED display support
Reviewed switch matrix handling

October 8, 2026

Time spent: ~65 mins

I continued working on the firmware approach.

Completed:

Selected QMK for firmware development
Reviewed its compatibility with the RP2040
Considered OLED display requirements
Planned the switch and rotary encoder functionality

October 9, 2026

Time spent: ~80 mins

I worked on the initial firmware functionality.

Completed:

Started developing the firmware
Worked on basic input and output behaviour
Explored the boot behaviour required for the MacroPad

October 12, 2026

Time spent: ~55 mins

I received the fabricated PCB and started inspecting it before assembly.

Completed:

Received the fabricated PCB
Inspected the board
Performed an initial fit check
Checked the PCB against the case design


October 13, 2026

Time spent: ~70 mins

I started checking the PCB connections using a multimeter.

Completed:

Inspected the electrical connections
Identified an issue with the OLED display footprint
Compared the footprint connections with the schematic
Confirmed that the OLED connections were reversed in the footprint


October 14, 2026

Time spent: ~85 mins

I worked on correcting the OLED connection issue on the PCB.

Completed:

Scraped away the copper near the affected OLED pins
Worked on isolating the incorrect connections
Repeated the process on both sides
Checked the connections using a multimeter
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/ed920e8c-1b2d-4580-b126-b48a369b3dfb" />

October 15, 2026

Time spent: ~60 mins

I started soldering the SK6812 MINI-E LEDs onto the PCB.

Completed:

Applied flux to the LED soldering pads
Identified the GND orientation of the LEDs
Started soldering the LEDs individually
Inspected the PCB after soldering the third, fifth and eighth LEDs
Identified two damaged LEDs during the process
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/623d9b75-b92d-4462-8b3b-90e750aea324" />
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/da78f913-c3e5-453a-9f95-932f975c5994" />


October 16, 2026

Time spent: ~75 mins

I started assembling the PCB by soldering the hot-swap sockets.

Completed:

Pre-soldered the connector points
Positioned the hot-swap sockets
Heated the connectors to secure the sockets
Completed the socket soldering
Identified an incorrectly soldered fifth socket
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/22179d95-fe84-4a0c-9330-c9f93beb38c9" />

October 19, 2026

Time spent: ~65 mins

I corrected the hot-swap socket soldering issue and continued PCB assembly.

Completed:

Desoldered the incorrectly positioned fifth socket
Cleaned the affected soldering area
Repositioned the socket
Completed the corrected soldering
<img width="370" height="279" alt="image" src="https://github.com/user-attachments/assets/024a4dcc-31cb-44fb-80a2-a3fc3dfcf1a0" />


October 20, 2026

Time spent: ~80 mins

I continued assembling the PCB by soldering the diodes and rotary encoder.

Completed:

Positioned the diodes in their respective locations
Trimmed the excess diode leads
Soldered the diodes
Positioned and soldered the rotary encoder
Inspected the completed soldering
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/3e833c9e-943e-4da4-9e0a-26be71f0319a" />


October 21, 2026

Time spent: ~70 mins

I started soldering the XIAO RP2040 and OLED display connections.

Completed:

Soldered pin headers to the XIAO RP2040
Soldered the OLED connector pins
Trimmed excess connector pins to prevent interference with the case
Soldered the OLED display
Connected the OLED pins externally to the XIAO RP2040
<img width="279" height="370" alt="image" src="https://github.com/user-attachments/assets/89138fba-ff57-43f7-b51c-28435ae9131b" />


October 22, 2026

Time spent: ~85 mins

I continued troubleshooting the OLED connections and worked on the firmware functionality.

Completed:

Identified three disconnected OLED pins
Investigated the GND connection and its multiple connections from both ends
Scraped the copper layer from both ends to isolate the connections
Verified that the unwanted connections were removed
Reworked parts of the firmware
Implemented the working-time display on the OLED screen
Configured the rotary encoder to control system volume
Configured the switches to open specific websites
Configured the LEDs to display random colours with a maximum brightness of 10%
<img width="676" height="910" alt="image" src="https://github.com/user-attachments/assets/366708b3-0b07-4c63-be87-56a85af6c3ed" />



