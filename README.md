# Power-Distribution-Board
## TLDR
Worked in a team of 4 people to design, implement, and program a board to distribute Low Voltage power throughout a race car in C/C++ for the University of California, Santa Cruz’s Formula SAE (Society of Automotive Engineer’s) Electric Vehicle team.

## Purpose
To distribute critical Low Voltage power throughout the race car to allow the car to function properly.

## My Main Parts
- CD74HC4067M Multiplexer: To help select the proper values to input into the Nucleo
- Nucleo L432KC: Used to read the current and voltages and send data into the CAN transceiver
- ISO1050DUB CAN Transceiver: Used to send the current and voltage readings through CAN into another board for data processing

## My main tools
The main tools that I used was KiCAD for the circuit design, as well as CMake for the embedded system design. I also used a multimeter and an oscilloscope in order to test the actual PCB and make sure that the board is properly distributing and emitting the proper power throughout the car.

## Engineering Process
The first step towards building this Power Distribution Board was simply to identify which components were needed. I knew that it was necessary to have a nucleo to send the data to another board, as well as to process the readings from the current sensors in another part of the board. In order to do this, I settled on using the Nucleo L432KC, because it had the necessary pins. My next major step was to wire the configuration for the CAN transceiver, and to wire up the current sensors' outputs to the Nucleo. Unfortunately, this was where I came cross my first major problem, in that I had less input pins on the Nucleo than the output pins of the current sensors. In order to solve this, I used a multiplexer to select which output I am currently reading, and I determined the selector bits by using an output pin on the Nucleo and using a function to determine which pin is being selected. After this, I tested out my program by writing up some code that calculates the correct theoretical current readings and checking this with the actual readings of the current sensor.

## Design

## Programming

## Overall Result
The result of this, was that my board was crucial to our entire team placing 18th out of 101 teams for the electric vehicle competition at FSAE, and we ranked 38th out of 101 teams for design, as well as 3rd in efficiency.
## Major Problems that I faced
The major problem that I faced when designing this portion of the board was managing the pins, because the Nucleo had less pins than inputs that I needed. In order to solve this problem, I had to look back on my engineering coursework in order to utilize a multiplexer to select the correct pins. In order to select the correct pin, I had to code a function in my CMake program.
