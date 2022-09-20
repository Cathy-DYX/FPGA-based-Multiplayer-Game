# FPGA-based Multi-player Game
This is a game produced as part of the EIE 2nd Year Information Processing coursework.

## Overview
This project is an IoT system where multiple FPGA boards (DE10-lite), which act as controllers, are connected to PCs, which act as client nodes and communicate with a UDP server on AWS. The server handles communication between the player nodes, synchronising the data to run the game.

## To run the game


## Directories

### doc
This folder contains the project requirement specification, the final report of the project and an explanation video showing how the game is run.

### AWS_Server
This folder contains the code stored in the AWS cloud. It includes:
  - the code to create and use the noSQL dynamoDB database, storing game and user data.
  - two versions of the cloud server: one only allows 1-vs-1 game, the other one allows multiplayer-vs-multiplayer team competition

### Unity_LocalGameHost

### LocalProcessing_LocalFPGAHost

### Nios2_FPGA

### Testing
