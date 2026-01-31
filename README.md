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
The development of this Power Distribution Board (PDB) began with a strategic component selection phase. The primary requirement was a central processing unit capable of managing current sensor data and communicating with external boards via CAN bus. I selected the Nucleo L432KC for its compact form factor and specific pinout capabilities.

The integration phase involved configuring the CAN transceiver and mapping the current sensors' outputs to the Nucleo. However, a hardware bottleneck emerged: the number of sensor outputs exceeded the available analog input pins on the microcontroller. To resolve this, I implemented a multiplexer (MUX) to expand the input capacity. By utilizing a Nucleo output pin to drive the MUX selector bits through a custom switching function, I was able to cycle through and sample all sensor data sequentially.

I validated the system by developing a test suite that compared real-time sensor data against theoretical current calculations, ensuring the accuracy of the board’s monitoring capabilities.

## Design
![alt text](https://github.com/Atul-Pethe/Power-Distribution-Board/blob/main/Power%20Distribution%20Board%20Schematic.png?raw=true)

## Overall Result
The result of this, was that my board was crucial to our entire team placing 18th out of 101 teams for the electric vehicle competition at FSAE, and we ranked 38th out of 101 teams for design, as well as 3rd in efficiency.
## Major Problems that I faced
The major problem that I faced when designing this portion of the board was managing the pins, because the Nucleo had less pins than inputs that I needed. In order to solve this problem, I had to look back on my engineering coursework in order to utilize a multiplexer to select the correct pins. In order to select the correct pin, I had to code a function in my CMake program.
