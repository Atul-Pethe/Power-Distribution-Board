# Power-Distribution-Board

#TLDR
Worked in a team of 4 people to design, implement, and program a board to distribute Low Voltage power throughout a race car in C/C++ for the University of California, Santa Cruz’s Formula SAE (Society of Automotive Engineer’s) Electric Vehicle team.

#Purpose
To distribute critical Low Voltage power throughout the race car to allow the car to function properly.

#My Main Parts
CD74HC4067M Multiplexer: To help select the proper values to input into the Nucleo
Nucleo L432KC: Used to read the current and voltages and send data into the CAN transceiver
ISO1050DUB CAN Transceiver: Used to send the current and voltage readings through CAN into another board for data processing
