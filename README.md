# Sunshine Scooters Control Code

Arduino UNO device control code for the Sunshine Scooters project.

This project contains the Arduino controller code to modify a [Hot Wheels Wild Thing](https://fisher-price.mattel.com/shop/en-us/fp/power-wheels/power-wheels-wild-thing-orange-dfv03) ride-on vehicle for children with mobility needs. Original credits for this project go to [FRC Team 1939](https://www.frcteam1939.com) who outlined [how to do the modification](https://www.instructables.com/id/Wild-Thing-Modification/). This project code follows this approach. However for this project, the Arduino UNO controller code was modified to suit our needs.

## DISCLAIMER / AGREEMENT

**The use of this code is bound not only by the MIT license included but also by the legal agreement listed in the AGREEMENT file. This code is utilized to control a device that comes with certain risks. Utilization, compilation, and execution of this code for such purpose to control a mobility device is permitted with adhereance to the terms listed in the `AGREEMENT` file in this code repository.**

## Hardware Required

To use this code, you will need an [Arduino UNO](https://www.arduino.cc/en/Guide/ArduinoUno) and a [Cytron PS2 Shield](https://www.cytron.io/p-cytron-ps2-shield).

## How to Use

To use this code you need to utilize the [Arduino Create IDE](https://www.arduino.cc/en/Main/Create). Once you have the IDE installed and have successfully run one of the test programs you will be ready to utilize this project.

In addition, the project code assumes that the Arduino and PS2 Shield as wired according the  wiring diagram in the included Wiring Diagram.pdf file.

1. Ensure you can follow the general [Arduino UNO getting started instructions](https://www.arduino.cc/en/Guide/ArduinoUno).
2. To utilize this code, add the three source code files included in the `src/` directory to your project. These include:
- `control.ino` - The main control code
- `Cytron_PS2Shield.cpp` - The Cytron PS2 Shield code
- `Cytron_PS2Shield.h` - The header file for the PS2 Shield code
3. Connect your Arduino UNO to your PC via USB and ensure the IDE can see the Arduino board.
4. Ensure the jumpers on the Cytron PS2 Shield board are connected to D3 (TX) and D2 (RX) for the code upload.
5. Click the Right Arrow to Upload and Save.
6. After the code is uploaded, move the jumpers on the Cytron PS2 Shield board to D1 (TX) and D0 (RX).

![Jumper Illustration](https://i2.wp.com/tutorial.cytron.io/wp-content/uploads/2015/06/Picture11.jpg?resize=400%2C316&ssl=1 "Jumper Illustration")


## Notes on Cytron PS2 Shield Dependency

This code depends on the Cytron PS2 Shield driver code which is available here:

https://github.com/CytronTechnologies/Cytron_PS2Shield

It is included in this repository as a convenience since the Cytron code has not been updated in over 5 years. However, any future revisions to that code should be referenced back to the original repository located above.

## Modifications from FRC Team 1939 Code

The original codebase can be found here: [FIRST1939/GoBabyGo](https://github.com/FIRST1939/GoBabyGo). This codebase includes the following modifications.

* Inclusion of the [Cytron_PS2Shield](https://www.cytron.io/p-cytron-ps2-shield) C++ code and header files for convenience.
* Introduction of diagonal joystick orientation support.
* Removal of servo steering option and rewrite of motor control for better ramping support
* Introduction of flag to disable backward motion for child
* Turn speed factor and minimum
* Reverse speed minimum
* Parent override implemented with wireless PS2 controller and Cytron PS2_Shield.
