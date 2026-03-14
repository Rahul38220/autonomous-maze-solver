# Autonomous Maze-Solver Robotic Car
**Autonomous Robotics • C++ • Pathfinding Algorithms**

## 📌 Overview
An autonomous maze-solving robotic platform built on the Arduino architecture. The system utilizes ultrasonic sensor feedback to navigate complex environments, featuring an intelligent backtracking algorithm that detects dead-ends, marks non-traversable paths, and re-routes in real-time to ensure efficient traversal.

## 🚀 Key Features
- **Autonomous Navigation:** Real-time distance mapping using ultrasonic feedback.
- **Intelligent Backtracking:** Dynamically identifies dead-ends and executes corrective maneuvers (90° and 180° turns) to find viable paths.
- **Non-Blocking Logic:** Modular motor control functions allow for precise movement synchronization.
- **Fail-Safe Mechanism:** Timeout-based sensor readings ensure the system remains responsive even if no echo is received.

## 🛠 Tech Stack
- **Platform:** Arduino (IDE/C++)
- **Sensors:** HC-SR04 Ultrasonic Sensor
- **Actuators:** DC Gear Motors with L298N/L293D Motor Driver
- **Algorithm:** Backtracking/Depth-First Search (DFS) implementation for pathfinding

## 📁 Repository Structure
- `src/`: Core Arduino firmware (.ino file).
- `docs/`: Circuit schematics and pin mapping documentation.
- `assets/`: Images of the physical robot and testing environments.

## 📊 System Flow
- **Distance Sampling:** The robot continuously pulses the trigPin and measures echo duration to calculate proximity.
- **Obstacle Detection:** If the distance falls below the defined threshold (4cm), the movement loop halts.
- **Corrective Maneuver:** The robot performs a right-hand turn to explore alternative directions.
- **Path Verification:** If the path remains blocked after turning, the system initiates a 180° "U-turn" or secondary left-hand exploration to find a clear route.

##💡 Engineering Note
The logic uses a One-Shot Snapshot approach for obstacle avoidance. By decoupling the distance calculation from the motor control, the robot can make discrete, logical decisions at intersections rather than simply reacting to proximity.
