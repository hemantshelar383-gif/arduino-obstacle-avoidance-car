Obstacle Avoidance Robotic Car Using Arduino

This project presents the design and implementation of an autonomous obstacle avoidance robotic vehicle using an Arduino UNO microcontroller.
The system integrates an ultrasonic distance sensor, a servo-based scanning mechanism, and an L298N motor driver to enable real-time navigation and intelligent path selection.

The robot image and circuit diagram have been uploaded to the repository.

1. Overview

The robotic car moves forward under normal operation while continuously monitoring the distance to obstacles using the HC-SR04 ultrasonic sensor.
When an obstacle is detected within 30 cm, the servo motor performs a scanning routine to evaluate left and right clearance and determine the optimal direction.

This project demonstrates concepts in embedded systems, real-time control, actuator interfacing, and autonomous robotics.

2. Working Principle (Based on the Code)
2.1 Normal Operation

The robot moves forward at a predefined speed.

The ultrasonic sensor monitors the distance ahead.

2.2 Obstacle Detection (< 30 cm)

The robot stops.

The robot reverses briefly.

The servo rotates left (180°) to measure distance.

The servo rotates right (0°) to measure distance.

The servo returns to center (90°).

2.3 Decision Logic

If left distance is zero → turn right

If right distance is zero → turn left

If left distance ≥ right distance → turn left

Else → turn right

2.4 Resume Forward Motion

After turning, the robot continues moving forward.

This logic is implemented exactly in the robotic_car.ino file.

3. Hardware Components

Arduino UNO

HC-SR04 Ultrasonic Sensor

SG90 Servo Motor

L298N Motor Driver

Two DC gear motors

Battery pack

Jumper wires and chassis components

4. Pin Configuration (Matches Code)
4.1 Ultrasonic Sensor

TRIG → Pin 11

ECHO → Pin 12

VCC → 5V

GND → GND

4.2 Servo Motor

Signal → Pin 3

VCC → 5V

GND → GND

4.3 Right Motor (L298N)

ENA → Pin 5

IN1 → Pin 7

IN2 → Pin 8

4.4 Left Motor (L298N)

ENB → Pin 6

IN1 → Pin 9

IN2 → Pin 10

5. Required Libraries

Install the following Arduino libraries:

Servo

NewPing (by Tim Eckel)

6. Code Reference

Key definitions from the implementation:

#define SERVO_PIN 3
#define ULTRASONIC_SENSOR_TRIG 11
#define ULTRASONIC_SENSOR_ECHO 12
#define MAX_REGULAR_MOTOR_SPEED 75
#define MAX_MOTOR_ADJUST_SPEED 150
#define DISTANCE_TO_CHECK 30


Full implementation is available in the code/robotic_car.ino file.

7. Project Structure
arduino-obstacle-avoidance-car/
│
├── code/
│   └── robotic_car.ino
│
├── robotimage.jpg
├── circuit diagram.png
├── README.md
└── LICENSE

8. Demo Video

YouTube Video Link:
https://youtu.be/BB8Q-wxkxsg

9. Uploaded Files

Robot Image: uploaded to repository

Circuit Diagram: uploaded to repository

10. Conclusion

This project showcases an autonomous robotic system using ultrasonic sensing, servo-based directional scanning, and motor control through an L298N driver.
The design demonstrates embedded programming skills, real-time decision-making, and hardware integration required for basic autonomous navigation.

Prepared By

Hemant Shelar
Zeal College of Engineering, Pune

