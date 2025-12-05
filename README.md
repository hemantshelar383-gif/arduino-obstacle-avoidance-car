🚗 Obstacle Avoidance Robotic Car Using Arduino

This project implements an intelligent autonomous navigation system using Arduino, where the robotic car detects obstacles using ultrasonic sensing, performs directional scanning using a servo motor, and makes real-time path decisions through a programmed control algorithm.
The system integrates motor actuation, distance measurement, and servo-based environmental scanning to achieve smooth and adaptive obstacle avoidance.

Images and circuit diagrams have already been uploaded and will appear below this documentation automatically.

📘 Project Overview

The robot is designed to operate fully autonomously.
Using the HC-SR04 ultrasonic sensor, the car continuously measures distance ahead. When an obstacle is detected within the predefined threshold (30 cm), the robot engages a servo-mounted scanning system to evaluate left and right paths and choose the optimal direction.

The decision-making process is driven by precise sensor measurements using the NewPing library, combined with differential motor control through an L298N motor driver.

This approach demonstrates fundamental concepts in:

Embedded systems

Autonomous robotics

Real-time decision algorithms

Sensor fusion

Actuator control

Mechatronics system integration

🧠 Working Algorithm (Based Entirely on Your Code)
1️⃣ Forward Motion

Motors run at constant speed until an obstacle is detected.

2️⃣ Obstacle Detection

If distance < 30 cm → robot stops.

3️⃣ Avoidance Maneuver

Reverse briefly to create safe turning space.

Servo rotates left (180°) → reads distance.

Servo rotates right (0°) → reads distance.

Servo re-centers (90°).

4️⃣ Decision Logic

Based on your code:

Condition	Action
Left distance = 0	Turn right
Right distance = 0	Turn left
Left ≥ Right	Turn left
Else	Turn right
5️⃣ Resume Navigation

After completing the turn, motors resume forward movement.

This logic creates a reactive and adaptive navigation system capable of handling unknown environments without prior mapping.

🎡 Hardware Architecture
Microcontroller

Arduino UNO – central control unit, executes logic and controls sensors and motors.

Sensing

HC-SR04 Ultrasonic Sensor for distance measurement

Servo Motor (SG90) for directional scanning

Motor Drive

L298N Motor Driver Module

Enables speed control (PWM)

Handles forward/reverse motor rotation

Actuators

Two DC Gear Motors for differential drive steering

Power

External battery pack for motor load

USB or 5V rail for Arduino logic

🔌 Pin Configuration (Verified From Your Code)
Ultrasonic Sensor
Pin	Arduino
TRIG	11
ECHO	12
Servo Motor
Pin	Arduino
Signal	3
VCC	5V
GND	GND
Right Motor (L298N)
Function	Arduino Pin
ENA	5
IN1	7
IN2	8
Left Motor (L298N)
Function	Arduino Pin
ENB	6
IN1	9
IN2	10
📂 Project Structure
📦 Obstacle Avoidance Robotic Car
 ┣ 📂 code
 ┃ ┗ robotic_car.ino
 ┣ README.md
 ┣ LICENSE
 ┣ robot.jpg
 ┣ circuit-diagram.jpg

📚 Required Libraries

Install Via Arduino Library Manager:

Servo (preinstalled)

NewPing by Tim Eckel
→ Used for accurate ultrasonic distance measurement and faster sensing cycles.

🛠 Core Code (Aligned With Your Implementation)
#include <Servo.h>
#include <NewPing.h>

#define SERVO_PIN 3
#define ULTRASONIC_SENSOR_TRIG 11
#define ULTRASONIC_SENSOR_ECHO 12
#define MAX_REGULAR_MOTOR_SPEED 75
#define MAX_MOTOR_ADJUST_SPEED 150
#define DISTANCE_TO_CHECK 30


Your full logic includes:

Intelligent reverse maneuvering

Direction-based turning

Adaptive scanning

PWM motor speed control

Signed speed handling for direction

🎥 Demo Video

▶ Watch on YouTube

📸 Robot Image (Uploaded)

📘 Circuit Diagram (Uploaded)

📝 Conclusion

This project demonstrates a strong understanding of:

Embedded C programming

Robotic motion control

Real-time obstacle detection

Intelligent decision-making algorithms

Sensor-actuator integration

Hardware interfacing and robotics system design

It serves as a solid foundation for advanced robotics work such as autonomous mapping, PID navigation, SLAM, or AI-driven motion planning.

✍️ Project Author

Hemant Shelar From Zeal College

