# NASSCOM-SoC
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
Fig.8 Systhesis Results
![image](https://github.com/user-attachments/assets/75a3120f-4422-41ad-9074-acd3fb21f4d6)
Fig.9 Synthesis resultant files exploration

Flop ratio = 1613/14876 = 0.10842968539930088733530518956709 = 10.84%

# Day 2 - Floorplanning
## Overview
- Define the width and height of the core and die
- Specify the location of preplaced cells
- Insert decoupling capacitors (DeCap cells) for power integrity
- Perform power planning (including power/ground rails and straps)
- Assign pin placement along the die boundaries
- Define logical cell placement blockages to control placement regions
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
Fig.16 Exploring the Input metal (Vertical)

