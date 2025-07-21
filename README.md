# 🧠 Object Detection and Distance Monitoring System using STM32

This is a real-time embedded project using **STM32F401RE**, **Ultrasonic Sensor (HC-SR04)**, **Servo Motor**, and **OLED Display (SSD1306 I2C)**.  
It detects nearby objects, measures distance in centimeters, and displays the result on the OLED screen. If the object is closer than a certain threshold (10 cm), the servo rotates to indicate detection.

---

## 🔧 Components Used

| Component           | Purpose                                        |
|---------------------|-----------------------------------------------|
| STM32F401RE         | Main microcontroller                          |
| HC-SR04             | Distance measurement (Ultrasonic sensor)      |
| SG90 Servo Motor    | Indicates object presence by rotating         |
| SSD1306 OLED (I2C)  | Displays object status and distance           |
| Jumper Wires        | Connections                                   |
| Power Supply        | 5V for sensor + servo                         |

---

## 🧠 Features

- 📏 **Accurate object distance measurement** using ultrasonic sensor
- 🖨️ **OLED Display output** with object status and real-time distance
- ⚙️ **Servo motor rotation** to signal nearby object
- 🕐 **Microsecond-precision delay** using DWT (Data Watchpoint & Trace)
- 📦 Clean STM32 HAL-based code, compatible with STM32CubeIDE

---

## 📐 Pin Configuration

| Module        | STM32F401RE Pin | Description              |
|---------------|------------------|--------------------------|
| TRIG (Ultrasonic) | PB0           | Trigger signal           |
| ECHO (Ultrasonic) | PB1           | Echo signal input        |
| Servo Motor   | TIM1 CH1 (PA8)   | PWM output to servo      |
| OLED (I2C)    | PB8 (SCL), PB9 (SDA) | I2C communication    |

---

## 🧪 Working Logic

1. Ultrasonic sensor measures distance.
2. If object detected < 10 cm:
   - Rotate servo to 45°
   - Show `Object Detected!` on OLED
3. Else:
   - Rotate servo back to 0°
   - Show `Scanning...` on OLED
4. Distance in cm is printed continuously.

---
## 🛠️ Project Setup

1. Clone this repo into your STM32CubeIDE workspace
2. Connect the hardware as per the table
3. Flash the firmware to STM32F401RE board
4. Power up and monitor OLED + Servo reaction

---

## 📚 Libraries Used

- [SSD1306 OLED I2C Driver](https://github.com/afiskon/stm32-ssd1306) – afiskon
- STM32 HAL Drivers (CubeMX Generated)
- DWT-based `delay_us()` implementation

---

## 🧩 Real-World Applications

- Smart Parking System
- Automatic Obstacle Detection
- Object-based Trigger Systems
- DIY Robotics / Surveillance Scanners

---

## 📜 License

This project is open source and available under the MIT License.

---

## 🤝 Contribution

Feel free to fork this repo, raise issues, or submit PRs if you want to improve or extend the functionality (e.g., add buzzer/alert/wireless communication etc.)

---

## 👤 Author

**Kunal Raj**  
Embedded Systems Developer | IoT Enthusiast   
Email: Kunalraj1699@gmail.com


