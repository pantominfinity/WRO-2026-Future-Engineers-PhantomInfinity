# WRO-2026-Future-Engineers-PhantomInfinity
# WRO Future Engineers - Team PhantomInfinity 🚀

Welcome to the official repository of **PhantomInfinity**, competing in the **World Robot Olympiad (WRO) - Future Engineers** category. This repository documents our full engineering journey, hardware design, mechanical physics, and software architecture.

---

## 📋 Table of Contents
- [Team Overview & Advanced Roles](#-team-overview--advanced-roles)
- [System Architecture & Hardware Components](#-system-architecture--hardware-components)
- [Physics & Mechanical Engineering Principles](#-physics--mechanical-engineering-principles)
- [Software Architecture & Control Logic](#-software-architecture--control-logic)
- [Obstacle Avoidance & Autonomous Navigation](#-obstacle-avoidance--autonomous-navigation)
- [Repository Structure](#-repository-structure)
- [Build & Setup Guide](#-build--setup-guide)

---

## 👥 Team Overview & Advanced Roles

| Team Member | Primary Role | Advanced Engineering Responsibilities |
| :--- | :--- | :--- |
| **Maryam AlEid** | Lead Software Systems Engineer & Algorithm Designer | Lead Block-based logic architect, sensor data fusion algorithm implementation, feedback control loop engineering, and edge-case execution handling. |
| **Reem AlDossary** | Chief Mechanical Engineer & Structural Architect | Chassis load distribution, center-of-mass optimization, torque-to-speed gear ratios design, and structural resonance/durability testing. |

---

## 🛠 System Architecture & Hardware Components

Our vehicle is built upon the **LEGO® Education SPIKE™ Prime System**, integrating high-precision sensors and actuators managed by the central SPIKE Hub micro-controller.

### Core Hardware Components:
1. **LEGO® SPIKE™ Prime Smart Hub**:
   * Powered by a 100MHz ARM Cortex-M4 processor with an integrated 6-axis Gyroscope/Accelerometer (IMU) for real-time orientation tracking.
2. **Color Sensors**:
   * Measures surface reflectivity, track borders, and color codes for navigation and environmental feedback.
3. **Distance Sensors (Ultrasonic)**:
   * Provides real-time spatial range measurement (cm/inches) for active obstacle detection and dynamic wall-following.
4. **Motion/Gyro Sensor (Integrated IMU)**:
   * Measures rotational velocity, roll, pitch, and yaw angles to maintain linear stability during high-speed maneuvers.
5. **High-Torque / High-Speed Motors**:
   * Encoder-integrated DC motors enabling precise closed-loop speed and position feedback control.

---

## 📐 Physics & Mechanical Engineering Principles

The structural integrity and motion dynamics of our autonomous vehicle were designed around classical mechanics to maximize agility, stability, and speed efficiency.

### 1. Torque ($\tau$) vs. Speed Dynamic Trade-off
To optimize motor efficiency, the mechanical gear reduction was tuned using the torque equation:
$$\tau = r \times F$$
Where $r$ represents the radius of the driven wheel/gear and $F$ represents the tangential force generated. 
* **High Torque Configuration**: Designed for heavy acceleration and obstacle clearance without motor stall.
* **Moment of Inertia Optimization**: Weight distribution was centralized near the base to lower the moment of inertia ($I = \sum m_i r_i^2$), reducing rotational resistance during sharp steering commands.

### 2. Linear & Angular Momentum ($p$ & $L$)
To ensure stability during autonomous drift or rapid direction changes, linear momentum ($p = m \cdot v$) and angular momentum ($L = I \cdot \omega$) were calculated to prevent dynamic tipping. The chassis height was minimized to keep the Center of Mass (CoM) low.

### 3. Frictional Dynamics & Traction Mechanics
Traction forces ($f_s \le \mu_s N$) were calculated to prevent wheel slip during maximum acceleration phases. Wheel friction coefficient ($\mu_s$) was balanced with vehicle mass ($m$) to ensure grip on slick surfaces.

---

## 💻 Software Architecture & Control Logic

The software algorithm was crafted using advanced graphical block-based programming (SPIKE Python-underpinned blocks). The system operates on a state-machine paradigm with modular execution loops.
