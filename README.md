# NASSCOM-SoC
This is a record of work done in the Digital VLSI Design & SoC Planning course, 5-day workshop by VSD and NASSCOM.

![image](https://github.com/user-attachments/assets/fab2dc75-9195-43dd-b76a-751e12790aa5)
# VM installation
![image](https://github.com/user-attachments/assets/da8fa522-23cc-4639-9d97-f2c231a486c5)
Fig.1 Oracle Virtual Box Manager
![image](https://github.com/user-attachments/assets/86670c10-00ca-4688-8ac3-7918df065792)
Fig.2 Ubuntu VM
# Day 1 - Synthesis
## Overview

- Introduction to open-source SoC design tools and ecosystem (OpenLane, OpenROAD, SkyWater, Efabless)
- Overview of the OpenLane flow: RTL → synthesis → floorplanning → placement → routing → GDSII
- Tool installation and setup instructions
- Exploring the OpenLane tool directory and configuration files
- Running the interactive flow and preparing the design
- Running synthesis and reviewing output files and reports

## Commands Used

- docker
- pwd
- ls -ltr
- flow.tcl -interactive
- package require openlane 0.9
- prep -design picorv32a
- For running Synthesis => run_synthesis

## Documentation of work
![image](https://github.com/user-attachments/assets/cbc43c3c-7015-46e1-b502-9275cd8ce921)
Fig.3 Open source EDA tools
![image](https://github.com/user-attachments/assets/22a2a7c0-5ea9-4da9-9d2d-ffa2affc595a)
Fig.4 RTL to GDS Flow
![image](https://github.com/user-attachments/assets/91f96225-ec2b-4c35-afc2-94785ee69f9c)
Fig.5 OpenLANE ASIC Flow
![image](https://github.com/user-attachments/assets/07059687-6f7f-48eb-a8cb-ea1783a8208a)
Fig.6 Opening OpenLANE
![image](https://github.com/user-attachments/assets/a6ded809-2361-4ba5-8a7e-ce16066646ae)
Fig.7 OpenLANE directory
![image](https://github.com/user-attachments/assets/97a41d55-17a5-4a5f-9b6f-7f761d67f65e)
Fig.8 Synthesis Results
![image](https://github.com/user-attachments/assets/75a3120f-4422-41ad-9074-acd3fb21f4d6)
Fig.9 Synthesis resultant files exploration

Flop ratio = 1613/14876 = 0.10842968539930088733530518956709 = 10.84%

# Day 2 
# Floorplanning
## Overview
- Define the width and height of the core and die
- Specify the location of preplaced cells
- Insert decoupling capacitors (DeCap cells) for power integrity
- Perform power planning (including power/ground rails and straps)
- Assign pin placement along the die boundaries
- Define logical cell placement blockages to control placement regions
- Die area = (660685/1000)(671405/1000) = 443,587.212425 sq um
## Commands used
- For running floorplan => run_floorplan
- For opening in magic =>  magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
## Documentation
![image](https://github.com/user-attachments/assets/1da34782-1a83-4621-8557-0eda5609d6b9)
Fig.10 Floorplanning
![image](https://github.com/user-attachments/assets/8e20ae9a-5c68-4174-9d5b-210411fc0e35)
Fig.11 Floorplanning log file
![image](https://github.com/user-attachments/assets/ca0047ef-7c75-42ee-bd63-47961259567e)
Fig.12 Floorplanning log file 
![image](https://github.com/user-attachments/assets/93cce535-32ff-4088-b5df-dc71f28e3c93)
Fig.13 Floorplanning logs
![image](https://github.com/user-attachments/assets/e4115fc8-622c-450a-bf58-cae4a61471cf)
Fig.14 Floorplanning layout
![image](https://github.com/user-attachments/assets/b68831e8-045b-48b9-88cb-7673935ad872)
Fig.15 Floorplanning layout Zoomed in
![image](https://github.com/user-attachments/assets/2291fb7b-fc38-4188-8b7b-6fc7ef289ad8)
Fig.16 Exploring the Input metal (Horizontal)
![image](https://github.com/user-attachments/assets/a052703c-5a62-4396-96e1-a1b72b0ae7f5)
Fig.17 Exploring the Input metal (Vertical)
# Placement
## Overview
- Bind the netlist to physical standard cells
- Optimize placement to reduce wire length and manage capacitance
- Insert repeaters to maintain signal integrity (with some area trade-off)
- Manage capacitance effects to control signal slew and timing
## Commandes used 
- For running placement => run_placement
- For opening in magic => magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
## Documentation
![image](https://github.com/user-attachments/assets/424277bc-cd93-4e62-8dc6-cd381b1606e8)
![image](https://github.com/user-attachments/assets/dccecf85-3dcc-4139-a0ff-ba598bb0ff6c)
![image](https://github.com/user-attachments/assets/3531c24d-83a1-4025-982d-91a1b45fbfd2)
# Library characterization and modelling
![image](https://github.com/user-attachments/assets/53f2fae4-60e1-4f93-8140-70aa16edb1bd)
- Cell Design flow
  ![image](https://github.com/user-attachments/assets/faaab290-6464-44d0-82cf-0f0c47bb9265)
  ## Characterization flow overview
- Read the model file
- Read the extracted SPICE netlist
- Define buffer behavior and parameters
- Read the buffer subcircuit
- Load the necessary power supply setup
- Attach stimulus to the characterization setup
- Apply the required output capacitance
- Run simulation commands (.trans, .dc)
- Input parameters (1–8) into GUNA software (see figure below)
- Generate timing, noise, and power characterization outputs
![image](https://github.com/user-attachments/assets/d1f1b929-a4d5-480f-aeac-f3b0804d45e4)
![image](https://github.com/user-attachments/assets/80cf522e-89dd-4b1c-afbf-562e4d237aff)
  ## Timing introduction
- Timing threshold definitions
![image](https://github.com/user-attachments/assets/e39e5158-c2ae-4b6e-94f1-f609dd468399)
## Timing characterization
- Propagation delay
![image](https://github.com/user-attachments/assets/7a66dd44-4352-4d19-b96b-6e862eb8918a)
## Transition time
![image](https://github.com/user-attachments/assets/2849db5a-3b90-4c86-a54f-36dccdf57e04)
# Day 3
## Standard Cell Design
### available at https://github.com/nickson-jose/vsdstdcelldesign
- Study spice deck for cell
- Study cell model files
- Evalute size effect of PMOS and NMOS
![image](https://github.com/user-attachments/assets/08895727-ceac-4cf1-9a48-eea9405077ea)
![image](https://github.com/user-attachments/assets/8080949d-7851-4d15-9e51-9ab10d4844c8)
![image](https://github.com/user-attachments/assets/948e28fd-ee4d-4dfc-a935-107b6d7a85bc)
### Basics of the fabrication process
#### 16 mask CMOS process
- Selecting a substrate
- N well and P well formation
- Creating active region for transistors (mask1)
- Gate Formation
- Light doped drain (LDD) formation
- Source and drain formation
- Forming contacts and local interconnects
- Higher level metal formation
![image](https://github.com/user-attachments/assets/ec6a2b01-d20f-4188-9ff6-3191579cdfad)
Fig.  Custom cel
## Commandes used
- git clone https://github.com/nickson-jose/vsdstdcelldesign.git
- cp sky130A.tech /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
- magic -T sky130.tech sky130_inv.mag 
- magic -T sky130A.tech sky130_inv.mag ngspice sky130_inv.spice
## Extracting cell to use in design
### Extract the custom inverter cell using ext2spice
- Extract cell
![image](https://github.com/user-attachments/assets/ff1cf367-803f-4ae9-b489-7ca5a8a63f25)
- run ngspice simulation
![image](https://github.com/user-attachments/assets/8d64b405-85f1-4888-b0fc-c39bed688009)

# Day 4
## Lef file extraction
- For PnR (Place and Route), only VDD, GND, input, and output information is needed
- This information is provided in the LEF file (no logic details, helping protect IP)
- Extract the LEF file and integrate it into the PicoRV32 flow
- Input and output ports must be placed at intersections of vertical and horizontal power tracks
- Standard cell dimensions: width should be an odd multiple of the horizontal track pitch, height should be an odd multiple of the vertical track pitch
- In standard cell design, ports should align at the intersections of horizontal and vertical routing tracks
- Typical track spacing: ~0.34 μm vertical, ~0.46 μm horizontal for each metal layer
## Running the openlane flow with our custom cell
![image](https://github.com/user-attachments/assets/02d97e06-ce98-418b-bbe5-ed92d4ddd70f)
![image](https://github.com/user-attachments/assets/74aad0f2-f3f9-4c0c-a313-18cfa8e97bf4)
