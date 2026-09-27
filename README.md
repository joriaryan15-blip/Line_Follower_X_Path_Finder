# Modular Line Follower & Path Finder Robot

A modular autonomous competition robot developed from scratch using an ESP32.
The robot is designed to participate in both line-following and path-finding
competitions by changing the sensing module and selecting the corresponding
control software.

The complete robot was designed and developed by me, including the electronics,
sensor integration, embedded software, control algorithms, wiring, and robot
assembly.

---

## 🤖 Project Overview

The main objective of this project was to build a single robot platform that
can be adapted for different autonomous robotics competitions.

The robot uses a normal 2-wheel differential drive with high-speed N20 geared
motors.

Two different sensing configurations can be used:

- **Line Following:** 5-element IR sensor array
- **Path Finding:** 3 × VL53L0X ToF sensors

The sensor module can be changed depending on the competition, while the
corresponding control software is selected for the required task.

This allows the same robot platform to be used for multiple competition
formats without redesigning the complete robot.

---

## 🔄 Modular Competition Architecture

```text
                    Same Robot Platform
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       LINE FOLLOWING              PATH FINDING
              │                         │
              ▼                         ▼
     5-Element IR Array          3 × VL53L0X ToF
              │                         │
              ▼                         ▼
        PID Control               Wall Following
              │                         │
              └────────────┬────────────┘
                           ▼
                    Motor Control
                           │
                           ▼
                       Robot
