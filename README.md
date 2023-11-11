# FreeRTOS Traffic Light Control System
This project implements a traffic light control system using the FreeRTOS real-time operating system on Arduino. The system consists of two Arduino boards, one acting as a transmitter (Tx) and the other as a receiver (Rx).

## Project Overview
The project is designed to simulate a traffic light intersection with four sets of traffic lights. The transmitter Arduino (Tx) controls the traffic light sequence, and the receiver Arduino (Rx) receives updates on the sequence timing wirelessly. Additionally, both Tx and Rx have manual override switches to control the traffic lights manually.

## Hardware Setup
* Tx Board:
  * Connect LEDs for traffic lights (pins 2-13).
  * Connect switches (SW1-SW5) for manual control.
  * Connect a pull-up resistor to each switch.
  * Connect an additional switch (SW5) for toggling a special mode.
* Rx Board:
  * Connect LEDs for traffic lights (pins 2-13).
  * Connect switches (SW1-SW5) for manual control.
  * Connect a pull-up resistor to each switch.

## Components Used
* Arduino boards (2)
* LEDs (12)
* Resistors
* Pushbuttons (5)
* Jumper wires

## Libraries Used
* [Arduino FreeRTOS](https://github.com/feilipu/Arduino_FreeRTOS_Library)

## Code Overview
### Tx (Transmitter) Board
* `FreeRTOS_Switch_TrafficTx.ino` contains the code for the transmitter board.
* Traffic light sequence control using FreeRTOS tasks.
* Manual override with switches SW1-SW4.
* Special mode toggle with switch SW5.
* Serial communication to send timing adjustments.
### Rx (Receiver) Board
* FreeRTOS_Switch_TrafficRx.ino contains the code for the receiver board.
* Traffic light sequence control using FreeRTOS tasks.
* Manual override with switches SW1-SW4.
* Special mode toggle with switch SW5.
* Serial communication to receive timing adjustments.

## Serial Communication
* The transmitter (Tx) periodically sends updates on the traffic light sequence to the receiver (Rx) through serial communication.
* The receiver (Rx) can receive manual override commands through serial communication from  transmitter (Tx)

## Task Synchronization
* FreeRTOS tasks are used for task synchronization, ensuring smooth operation of the traffic light control system.

## How to Run
1. Upload the FreeRTOS_Switch_TrafficTx code to the transmitter Arduino.
2. Upload the FreeRTOS_Switch_TrafficRx code to the receiver Arduino.
3. Ensure all wiring connections are correctly set up.
4. Power on both Arduinos.

## License
This project is open-source and available under the MIT License. Feel free to modify and distribute the code.

## Acknowledgments
Special thanks to the FreeRTOS community and Arduino for providing the tools and resources to implement this project.
