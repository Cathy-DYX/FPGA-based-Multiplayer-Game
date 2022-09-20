# FPGA-based Multi-player Game
In this project, an IoT system is established to allow multiple users to play a car-racing game. It is produced as part of the EIE 2nd Year Information Processing coursework. 

## Overview
This project is an IoT system where multiple FPGA boards (DE10-lite), which act as controllers, are connected to PCs, which act as client nodes and communicate with a UDP server on AWS. The server handles communication between the player nodes, synchronising the data to run the game.

## To run the game
To run the AWS cloud server:
1. Start an instance on AWS and create the database tables.
2. Run the server code <code>AWS_Server/AWSserver_1-vs-1</code> or <code>AWS_Server/AWSserver_multi-vs-multi</code>.

On local computer:
1. The .sof file <code>Nios2_FPGA/Golden_Top/DE10_LITE_Golden_Top.sof</code> is the programming image file obtained by compiling the Quartus hardware design files. To get it  downloaded in the FPGA, launch 'Tools -> Programmer' and click 'start'. Now the FPGA is programmed and the hardware is operating.
2. Next, download the software executable file (.elf) into the Nios II processor: The .elf file <code>Nios2_FPGA/Golden_Top/software/cwgamefpga/cwgamefpga.elf</code> is obtained by compiling the software application and the BSP. Launch the Nios II Command Shell in the directory <code>Nios2_FPGA/Golden_Top/software/cwgamefpga</code> and enter <code>nios2-download -g cwgamefpga.elf</code>. This downloads it onto the FPGA to run the compiled C code on the NIOS II processor.
3. Then, run the local processing code (<code>LocalProcessing_LocalFPGAHost/LocalFPGAHost_localprocessing.py</code>).
4. Finally, open <code>Unity_LocalGameHost</code> in Unity and the game starts.

## Directories

### doc
This folder contains the project requirement specification, the final report of the project and an explanation video showing how the game is run.

### AWS_Server
This folder contains the code stored in the AWS cloud. It includes:
  - the code to create and use the noSQL dynamoDB database, storing game and user data.
  - two versions of the cloud server: one only allows 1v1 game, the other one allows multiplayer-vs-multiplayer team competition

### Unity_LocalGameHost
This directory contains the Unity project files for the game.

### LocalProcessing_LocalFPGAHost
This is the code running on each local client node, processing raw data from the FPGA and relaying data to the local game host - Unity.

### Nios2_FPGA
This folder contains the quartus files and the platform designer files for the FPGA board.

### Testing
This folder contains the testing programs used in the development stage. 
