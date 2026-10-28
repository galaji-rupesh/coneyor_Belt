# Smart Conveyor Belt — Wokwi Project

## Project aim
To demonstrate an automated conveyor control system that detects an object using an ultrasonic sensor, stops the simulated belt indicator, activates an alarm, and moves a servo-operated diverter gate.

## Files
- `sketch.ino` — Arduino program
- `diagram.json` — Wokwi circuit and wiring
- `libraries.txt` — required libraries (Servo is included with the Arduino environment)
- `PROJECT_REPORT.md` — project documentation for submission

## Components
1. Arduino Uno R3
2. HC-SR04 ultrasonic distance sensor
3. Micro servo motor (sorting gate)
4. Green LED and 220-ohm resistor
5. Red LED and 220-ohm resistor
6. Piezo buzzer
7. Jumper wires (represented by diagram connections)

## How it works
1. The ultrasonic sensor measures the distance in front of the conveyor.
2. When the distance is 15 cm or less, the system detects an object.
3. The green LED turns OFF to represent the belt stopping.
4. The red LED turns ON, the buzzer sounds briefly, and the servo moves to 90 degrees.
5. When the distance reaches 18 cm or more, the system resumes and resets the diverter.
6. The 15 cm stop and 18 cm resume thresholds reduce rapid switching near the boundary.

## Test in Wokwi
1. Open https://wokwi.com/projects/new/arduino-uno
2. Open `sketch.ino` and replace the example program with this project's code.
3. Open `diagram.json` and replace the example diagram with this project's diagram.
4. Start the simulation.
5. Click the HC-SR04 sensor and adjust its distance slider:
   - 100 cm: belt running (green LED ON)
   - 10 cm: object detected (green OFF, red ON, servo moves, buzzer sounds)
   - 25 cm: belt resumes
6. Open the Serial Monitor at 9600 baud to see the status.

## Important simulation limitation
The green LED represents the conveyor motor's ON/OFF state. This simulation does not contain a real DC conveyor motor. A physical model needs a suitable motor driver, a motor with an appropriate external power supply, a common ground, and safe mechanical mounting. Do not power a DC motor directly from an Arduino I/O pin.
