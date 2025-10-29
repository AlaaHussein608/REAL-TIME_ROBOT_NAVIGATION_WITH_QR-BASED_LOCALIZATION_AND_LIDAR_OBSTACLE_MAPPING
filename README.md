# REAL-TIME_ROBOT_NAVIGATION_WITH_QR-BASED_LOCALIZATION_AND_LIDAR_OBSTACLE_MAPPING
This project implements a real-time navigation stack for a differential-drive robot. It combines precise pose estimation from ArUco markers fused with an IMU via a Kalman filter, with a LIDAR-based obstacle avoidance system, using a Dynamic Window Approach (DWA) variant for path planning for safe indoor navigation.

## 📋 Project Overview

The system features a hybrid computational architecture where:

- **Raspberry Pi 4** handles high-level tasks:  
  - ArUco marker detection  
  - Pose estimation

- **Arduino Uno R3** manages low-level operations:
- Fusion of sensor data
- Control of motors

The robotic platform is differential-drive and includes the following components:

- **Arducam** for visual input  
- **MPU6050** IMU for orientation sensing  
- **RPLIDAR A1M8** for obstacle detection  
- **L298** motor driver for motion control

---

## 🚀 Key Features

- Real-time visual localization employing ArUco markers
- Sensor fusion combining visual and inertial measurements via **Kalman filter**
- Obstacle avoidance powered by LIDAR and an algorithm inspired by the **Dynamic Window Approach**
- Goal-based navigation with **proportional controller** for waypoint following

---

## 🛠️ Hardware Requirements

- Raspberry Pi 4 (2GB+ RAM)  
- Arduino Uno R3  
- Arducam (compatible with Raspberry Pi)  
- MPU6050 IMU sensor  
- RPLIDAR A1M8  
- L298 Motor Driver  
- DC Motors (differential drive configuration)  
- Power supply (6–12V)

---

## 🔧 Software Dependencies

### Raspberry Pi (Python)

pip install opencv-python picamera2 numpy pyserial
## 🧰 Arduino Libraries

- BasicLinearAlgebra library
- MPU6050_light library
- Standard Arduino libraries: Wire, Serial

---

## 🎯 Getting Started Guide

### 🛠️ Assembly Instructions

- Wire all sensors to their designated connection points
- Confirm adequate power distribution across all system components
- Install the camera with predetermined positioning parameters

### 🎥 Calibration Process

- Execute `take_photo.py` to gather calibration imagery
- Launch `calibrate.py` to determine camera intrinsic parameters
- Implement the resulting calibration data in primary application files

### 🧩 Environment Marking

- Deploy ArUco markers throughout the operating space with established coordinates
- Synchronize marker location data within the Arduino programming

### 🚦 System Launch

- Load the microcontroller with Arduino program code
- Initiate the primary navigation algorithm on the Raspberry Pi
- Track serial data streams for system diagnostics

---

## 📊 Architectural Design

The framework implements a **distributed computing** methodology:

### 🔍 Sensory Processing Tier (Raspberry Pi)

- Image acquisition and visual data interpretation
- Marker identification and spatial positioning
- LIDAR information gathering

### 🧠 Operational Management Tier (Arduino)

- Multi-sensor data integration through **Kalman filtering**
- Movement coordination and actuator management
- Bidirectional data exchange with the processing unit

---

## 🔄 Operational Pipeline

1. Visual input is acquired through camera frame capture and marker recognition
2. Spatial positioning algorithms determine robot orientation relative to markers
3. Coordinate information transfers to the control unit via serial interface
4. The controller merges visual positioning with inertial measurements
5. Pathfinding mechanisms determine optimal trajectories while avoiding obstructions
6. Movement instructions are created and implemented by the drive system

---

## ⚙️ System Parameters

Essential customizable settings (modify within source code):

- Camera intrinsic properties and lens distortion values
- Marker dimensional specifications and encoding format
- Mechanical characteristics (axle length, propulsion wheel dimensions)
- Navigation control sensitivity settings
- Filter noise characteristics for data fusion
- Collision prevention sensitivity ranges

---

## 🧪 Verification Procedures

- Employ `animate.py` for LIDAR data representation
- Observe serial monitoring for positioning feedback and guidance status
- Conduct trials in structured settings with predefined marker arrangements
- Verify collision prevention effectiveness across diverse obstacle patterns

---

## 📈 System Capabilities

The platform delivers:

- Continuous functionality at sustainable processing rates
- Position tracking maintaining **sub-centimeter accuracy**
- Reliable obstruction evasion in **changing surroundings**
- Consistent trajectory execution between target locations

---

## 🔮 Development Roadmap

Possible upgrade paths and feature expansions:

- Comprehensive simultaneous localization and mapping
- Concurrent tracking of multiple reference markers
- Sophisticated route optimization methods (such as A* or RRT)
- Artificial intelligence integration for advanced perception
- Collaborative functionality across multiple robotic units
- Web-based remote supervision capabilities

---

## 📚 Technical Resources

For comprehensive theoretical foundations and practical implementation notes, consult `Report.docx`, containing:

- Structural design summary
- Algorithmic formulations
- Empirical findings
- Complete bibliographical references

---

## 👥 Development Team

- **Alaa Hussein**
- **Baraa Lazkani**
- **Haidar Saad**
- **Humam Yehia**

**Project Supervision:**

- Dr. **Fadi Muttawag**
- Eng. **Baher Kher-Bek**

---

## 📄 Usage Rights

This platform is designated for **educational and investigative applications**.
Appropriate attribution is requested when referenced in scholarly works.

---

## 🤝 Community Participation

Enhancement proposals for this initiative are appreciated.
We encourage submission of **technical issues** and **code modifications** for functionality improvements and error resolution.
