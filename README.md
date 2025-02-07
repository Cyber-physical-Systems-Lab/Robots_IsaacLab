# Robots_IsaacLab

This repository contains URDF files, mesh files, and USD files for various robotic components. The URDF files define the robot structure, while the meshes and USD files provide the visual and collision models.

## Usage Instructions

1. **Load URDF in Simulation**
   - The URDF files define the robot's kinematics and link the appropriate mesh files.
   - To visualize the URDF, use a tool like RViz (for ROS) or import it into Isaac Sim.
   - Example command for ROS:
     ```sh
     roslaunch urdf_tutorial display.launch model:=urdf/nova5_robot.urdf
     ```

2. **Import into Isaac Sim**
   - The `.usd` files in `IsaacUSD/` are intended for direct import into NVIDIA Isaac Sim.
   - Ensure that mesh paths in the URDF and USD files correctly point to `meshes/` or provide an absolute path.

3. **Pending to Fix Broken Mesh Links**
   - Some URDF files reference meshes that may not be found due to relative path issues.
   - If your URDF model is missing parts:
     - Open the URDF file and check `<mesh filename="..."/>` paths.
     - Verify that the corresponding `.dae` or `.stl` files exist in `meshes/`.
     - Update paths to match your directory structure.

4. **Modify and Extend**
   - You can modify the URDF files to add new components or adjust joint parameters.
   - If using Isaac Sim, update `.usd` files accordingly and regenerate mesh references if needed.

## Troubleshooting

- **Mesh Not Found Error**: Ensure that the URDF file points to the correct relative path in `meshes/`.
- **Missing Visuals in Isaac Sim**: Some USD files might not properly reference the intended meshes; open the USD in a text editor and adjust paths.

## Directory Structure
```
robot_description/
├── IsaacUSD/             # USD files for Isaac Sim
│   ├── myAGV/
│   ├── nova5_robot/
│   ├── nova5_robot_2f85/
├── meshes/               # Mesh files (STL/DAE) for visualization and collision
│   ├── myAGV/
│   ├── myCobot280_gripper/
│   ├── myCobot280_pi/
│   ├── nova5/
│   ├── robotiq_2f85/
├── urdf/                 # URDF files defining the robot model
│   ├── myAGV.urdf
│   ├── mycobot_280_pi.urdf
│   ├── nova5_robot_2f85.urdf
│   ├── nova5_robot.urdf
│   ├── robotiq_2f85.URDF
└── README.md             # This documentation file
```