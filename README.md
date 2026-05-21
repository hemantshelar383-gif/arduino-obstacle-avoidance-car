# 🤖 Autonomous Obstacle Avoidance Robotic Car

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Stars](https://img.shields.io/github/stars/hemantshelar383-gif/arduino-obstacle-avoidance-car?style=flat-square)

Autonomous robotic car using Arduino UNO, HC-SR04 ultrasonic sensor, SG90 servo for scanning, and L298N motor driver. The car detects obstacles, scans left/right, makes a navigation decision, and self-corrects its path in real time.

---

## 🎥 Demo

▶️ **[Watch on YouTube](https://youtu.be/BB8Q-wxkxsg)**

---

## 📌 Overview

The car continuously monitors its surroundings using an HC-SR04 ultrasonic sensor mounted on a servo motor. When an obstacle is detected within 30 cm, the car stops, reverses, and performs a bilateral scan — then decides which direction offers more clearance and turns accordingly. This mimics basic autonomous navigation decision-making.

---

## ⚙️ Working Principle

```
Moving Forward
      │
      ▼
Obstacle Detected < 30 cm?
      │ YES
      ▼
Stop → Reverse briefly
      │
      ▼
Servo scans LEFT (180°) → record distance
Servo scans RIGHT (0°)  → record distance
Servo returns to CENTER (90°)
      │
      ▼
Left > Right?  ──YES──► Turn Left
      │ NO
      ▼
          Turn Right
      │
      ▼
Resume Forward Motion
```

---

## 🔩 Hardware Components

| Component | Specification | Purpose |
|-----------|--------------|---------|
| Arduino UNO | ATmega328P | Main microcontroller |
| HC-SR04 | 2–400 cm range | Obstacle distance sensing |
| SG90 Servo Motor | 180° rotation | Sensor pan for bilateral scan |
| L298N Motor Driver | Dual H-bridge | DC motor speed and direction control |
| 2× DC Gear Motors | N20 / TT type | Drive wheels |
| Battery Pack | 7.4V or 9V | Power supply |
| Robot Chassis | 2WD or 4WD | Physical frame |

---

## 📌 Pin Configuration

### Ultrasonic Sensor (HC-SR04)

| HC-SR04 Pin | Arduino Pin |
|-------------|------------|
| TRIG | D11 |
| ECHO | D12 |
| VCC | 5V |
| GND | GND |

### Servo Motor (SG90)

| Servo Pin | Arduino Pin |
|-----------|------------|
| Signal | D3 |
| VCC | 5V |
| GND | GND |

### L298N Motor Driver

| L298N Pin | Arduino Pin | Function |
|-----------|------------|----------|
| ENA | D5 (PWM) | Right motor speed |
| IN1 | D7 | Right motor direction |
| IN2 | D8 | Right motor direction |
| ENB | D6 (PWM) | Left motor speed |
| IN3 | D9 | Left motor direction |
| IN4 | D10 | Left motor direction |

---

## 📂 Project Structure

```
arduino-obstacle-avoidance-car/
│
├── coderoboticcar.ino    ← Main Arduino source code
├── circuit diagram.png   ← Wiring diagram
├── robotimage.jpg        ← Physical build photo
├── README.md
└── LICENSE
```

---

## 🚀 How to Run

### Step 1 — Clone the Repository

```bash
git clone https://github.com/hemantshelar383-gif/arduino-obstacle-avoidance-car.git
```

### Step 2 — Install Required Libraries

In Arduino IDE: `Tools → Manage Libraries`

- **Servo** — built-in, no install needed
- **NewPing** by Tim Eckel — search and install

### Step 3 — Upload the Code

1. Open `coderoboticcar.ino` in Arduino IDE
2. Select **Board:** Arduino UNO | **Port:** your COM port
3. Click **Upload**

### Step 4 — Assemble and Power

1. Assemble robot chassis with motors and mount sensor on servo
2. Connect all components per the pin table above
3. Power with 7.4V or 9V battery pack
4. Place on a flat surface and observe autonomous navigation

---

## 🔑 Key Code Constants

```cpp
#define SERVO_PIN              3
#define ULTRASONIC_SENSOR_TRIG 11
#define ULTRASONIC_SENSOR_ECHO 12
#define MAX_REGULAR_MOTOR_SPEED  75   // Normal forward speed (0–255)
#define MAX_MOTOR_ADJUST_SPEED  150   // Turning speed
#define DISTANCE_TO_CHECK       30    // Obstacle threshold in cm
```

---

## 📸 Build Photos

Robot build and circuit diagram images are included in the repository root.

---

## 🎓 Concepts Demonstrated

- Ultrasonic distance sensing
- PWM-based DC motor speed control
- Servo-based sensor panning
- Decision-making logic in embedded C
- Differential steering for autonomous navigation

---

## 🔮 Future Enhancements

- Add IR sensors for line following
- Integrate Bluetooth / Wi-Fi for remote override
- Add OLED display for real-time distance readout
- Upgrade to PID-based motor speed control
- Multi-sensor fusion (ultrasonic + IR)

---

## 👤 Author

**Hemant Shelar**  
Electronics & Telecommunication Engineering  
Zeal College of Engineering, Pune  
🔗 [LinkedIn](https://www.linkedin.com/in/hemant-shelar-l07)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
