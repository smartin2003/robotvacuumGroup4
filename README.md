# Robot Vacuum Coverage Simulation  
*A ROS 2 Humble + Gazebo project for autonomous floor coverage, height-clearance awareness, and performance evaluation.*

---

## Project Overview

This project simulates an autonomous robot vacuum using **ROS 2 Humble**, **Gazebo**, and the **Nav2** navigation stack.  
The robot is tasked with cleaning a room by maximizing floor coverage while respecting **height-clearance constraints** (e.g., fitting under furniture) and avoiding collisions.

The system uses:
- TurtleBot3 robot platform  
- Depth camera + LiDAR sensing  
- Custom Gazebo environments  
- Coverage algorithms  
- Clearance mapping  
- Metrics tracking (coverage %, collisions, run time)

## System Components

### **1. Clearance Mapper**
Processes depth/LiDAR data to estimate free space under furniture and classify areas based on clearance height.  
Used to determine which regions the robot can safely enter.

### **2. Coverage Planner**
Generates systematic waypoint patterns (e.g., boustrophedon lawnmower patterns) to maximize room coverage.  
Integrates with Nav2's waypoint follower.

### **3. Metrics Logger**
Records all performance data:
- Total area covered  
- Percentage coverage  
- Collisions  
- Time to completion  
- Path length / efficiency  

Outputs CSV/JSON or ROS bag for analysis.

### **4. Navigation Stack (Nav2)**
Handles:
- Obstacle avoidance  
- Global/Local planning  
- Waypoint following  
- Controller tuning  

### **5. Simulation Environment**
Custom Gazebo world containing:
- Walls  
- Tables  
- Chairs  
- Obstacles  
- Furniture with known height clearances  

## Project Directory Structure

```
robot_vacuum_ws/
└── src/
    ├── clearance_mapper/       # Node for height clearance mapping
    ├── coverage_planner/       # Coverage waypoint generation logic
    ├── metrics_logger/         # Coverage/time/collision metrics
    ├── vacuum_navigation/      # Nav2 configs & launch files
    └── vacuum_simulation/      # Gazebo world, models, spawners

