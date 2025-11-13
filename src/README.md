# Robot Vacuum Coverage Simulation

This project implements a ROS 2 Humble + Gazebo simulation of a robot vacuum designed to maximize floor coverage while respecting height-clearance constraints under furniture.

## Features
- TurtleBot3 simulation in Gazebo
- Nav2 navigation stack
- Clearance mapping from depth/LiDAR data
- Coverage planner for systematic cleaning
- Metrics logger for coverage %, collisions, and run time
- Unified launch system for reproducible experiments

## Workspace Structure
src/
├── clearance_mapper/ # Height clearance mapping
├── coverage_planner/ # Coverage waypoint generation
├── metrics_logger/ # Performance metrics
├── vacuum_navigation/ # Nav2 configs & launches
└── vacuum_simulation/ # Gazebo worlds & models
