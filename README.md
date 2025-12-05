Obstacle Avoidance Robotic Car Using Arduino

This project presents the design and implementation of an autonomous obstacle avoidance robotic vehicle using an Arduino UNO microcontroller.
The system integrates an ultrasonic distance sensor, a servo-based scanning mechanism, and an L298N motor driver to enable real-time navigation and intelligent path selection.

All images and circuit diagrams have been uploaded to the repository and will appear below in their respective sections.

**Overview**

The robotic car moves forward under normal conditions and continuously monitors the distance to obstacles using the HC-SR04 ultrasonic sensor.
When an obstacle is detected within 30 cm, the vehicle performs a scanning routine using a servo motor, analyzes left and right clearance, and turns accordingly.

This project demonstrates concepts in embedded systems, real-time control, actuator interfacing, and autonomous robotics.

Working Principle (Based on the Code)

The car moves forward at a predefined speed.

The ultrasonic sensor checks for obstacles.

If the obstacle distance is less than 30 cm:

The car stops.

The car reverses slightly.

The servo rotates left (180°) and records the distance.

The servo rotates right (0°) and records the distance.

The servo returns to center (90°).

Decision-Making Logic

If left distance is zero → turn right.

If right distance is zero → turn left.

If left distance is greater or equal → turn left.

Otherwise → turn right.

After turning, the robot resumes forward motion.

This logic is implemented exactly as defined in the robotic_car.ino file.

Hardware Components

Arduino UNO

HC-SR04 Ultrasonic Sensor

SG90 Servo Motor

L298N Dual H-Bridge Motor Driver

Two DC gear motors

Battery pack

Jumper wires and chassis components

Pin Configuration (Matches Code)
Ultrasonic Sensor

TRIG → Pin 11

ECHO → Pin 12

VCC → 5V

GND → GND

Servo Motor

Signal → Pin 3

VCC → 5V

GND → GND

Right Motor (L298N)

ENA → Pin 5

IN1 → Pin 7

IN2 → Pin 8

Left Motor (L298N)

ENB → Pin 6

IN1 → Pin 9

IN2 → Pin 10

Required Libraries

Install the following Arduino libraries:

Servo

NewPing (by Tim Eckel)

Code Reference

Key definitions from the actual implementation:

#define SERVO_PIN 3
#define ULTRASONIC_SENSOR_TRIG 11
#define ULTRASONIC_SENSOR_ECHO 12
#define MAX_REGULAR_MOTOR_SPEED 75
#define MAX_MOTOR_ADJUST_SPEED 150
#define DISTANCE_TO_CHECK 30

**
The full source code is available in the code/robotic_car.ino file.**

Project Structure
project-root/
│
├── code/
│   └── robotic_car.ino
│
├── robot.jpg
├── circuit-diagram.jpg
├── README.md
└── LICENSE

Demo Video

*YouTube Link:
https://youtu.be/BB8Q-wxkxsg

Robot Image

(Automatically displayed from uploaded file)

Circuit Diagram

(Automatically displayed from uploaded file)

Conclusion

This project demonstrates a complete autonomous navigation system using fundamental principles of robotics and embedded programming.
It includes obstacle detection, directional scanning, decision-making logic, and differential motor control.
The implementation reflects strong understanding of microcontroller programming, sensor integration, and real-time robotic movement.

Prepared By

Hemant Shelar, Zeal College of Engineering, Pune
