# Warehouse Robotics Project

**Platform:** Unity 2022.3.62f3  
**Robot:** Clearpath Husky A200  
**Project Duration:** 4–5 weeks  
**Environment:** Warehouse Simulation

## 1. Project Overview

The objective of this project is to develop and extend a warehouse robotics simulation involving a Clearpath Husky A200 mobile robot.

The Unity environment, a sample operator interface, and a basic robot URDF model (with attached sensors) are already provided. Students will implement specific functionalities related to robot control, environment interaction, sensor visualization, static/dynamic obstacle visualization, and operator interaction.

The goal is **to extend the existing simulation rather than build a new project from scratch**.

*[[](https://github.com/subhransu10/Indoor_Warehouse_Robotics_Project/blob/main/Main%20Poster.png)]*

## 2. Getting Started

### 2.1 Project Setup

1. Download and install **Unity 2022.3.62f3** using [Unity Hub](https://unity.com/download).
2. Download the project from this [OneDrive link](). Request access from the instructor if necessary.
3. Open the project in Unity Hub and load the `Environment_Warehouse` scene (if it is not already open).

### 2.2 Required Packages

Once the project is loaded, check whether the following packages are installed. Install any missing packages using **Window → Package Manager**.

**A. URDF Importer**

1. In Package Manager, click **+ → Add package from git URL**.
2. Paste the following URL:

   `https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer#v0.5.2`

3. Click **Add** and wait for installation.

**B. Unity glTFast**

1. In Package Manager, click **+ → Add package by name**.
2. Enter:

   `com.unity.cloud.gltfast`

3. Click **Add** to install.

**C. Universal Render Pipeline (URP)**

1. Open **Window → Package Manager → Packages: Unity Registry**.
2. Search for **Universal RP** and click **Install** (if not already installed).
3. In the Project window, check whether a URP Render Pipeline Asset already exists.
4. If none exists, right-click → **Create → Rendering → URP Asset (with Universal Renderer)**.
5. Go to **Edit → Project Settings → Graphics** and assign the URP Asset to **Scriptable Render Pipeline Settings**.
6. In **Edit → Project Settings → Quality**, ensure the active quality level uses the URP Asset (or inherits the Graphics default).

**Note:** Do not create a new URP Asset if the provided project already has one correctly assigned. If materials appear pink, check the material shaders and convert incompatible Built-in materials using **Window → Rendering → Render Pipeline Converter**.


### 2.3 Unity Project Structure

Familiarize yourself with the **Scene, Hierarchy, Inspector, and Project** windows.

Locate the following objects and components:

| Object / Component | Description |
|---|---|
| `Husky_a200` | Mobile robot model with attached sensors |
| `StudentModules_DROPIN` | Student module objects and interface components |
| `StudentUI_Canvas` | Sample operator interface |
| `HuskyDifferentialDrive` | Robot movement controller script |
| `Assets` | Imported vehicles, pedestrian characters, and other reusable assets |

**Note:** Some components may be located under child GameObjects or attached as scripts in the Inspector.

*[Insert Screenshot 3: Unity Hierarchy showing the relevant objects]*

## 3. Student Tasks

The project is divided into four modules. Each student is responsible for implementing and testing their assigned module.

### Student 1 — Robot Control and Environment

**Objective:** Enhance the warehouse environment and implement robot movement and navigation.

**Tasks:**
- Implement forward, backward, and rotational movement using WASD.
- Ensure that the robot follows differential-drive kinematics.
- Implement stopping when an obstacle or collision is detected.
- Introduce additional obstacles and/or expand the existing environment.
- Test robot movement in both manual and simple autonomous navigation modes (e.g., waypoint following).

**Expected Result:** A controllable Husky robot capable of navigating the warehouse manually and autonomously while responding to obstacles.

### Student 2 — Sensor (Camera and LiDAR) and Map Visualization

**Objective:** Visualize sensor data and mapping information to improve environmental awareness.

**Tasks:**
- Display a point-cloud map (`/pcd_map`).
- Display a voxel map (`/voxel_map_pcd`).
- Implement controls to enable or disable each visualization.
- Allow adjustment of visualization density or appearance.
- Implement a scenario-based sensor visualization feature. For example, in low-light conditions, the interface should automatically prioritize LiDAR visualization over the camera feed. Students may propose an alternative relevant scenario.

**Expected Result:** A Unity interface for visualizing sensor and map data, including an adaptive visualization feature.

### Student 3 — Static and Moving Object Visualization

**Objective:** Distinguish stationary and moving objects within the warehouse.

**Tasks:**
- Add stationary and moving objects (e.g., vehicles and pedestrians) to the environment.
- Implement object-level visualization using different colors or markers.
- Visualize static and moving point-cloud data when available.
- Provide a toggle to show or hide static and dynamic elements.

**Suggested Colors:**
- **Green:** Static objects
- **Red:** Moving objects

**Expected Result:** A visualization system that clearly distinguishes static and moving objects.

**Note:** Developing or training a moving-object segmentation model is not required. Simulated or predefined object classifications may be used.

### Student 4 — Operator Interface

**Objective:** Improve the robot operator's interaction with the simulation.

**Tasks:**
- Implement or extend camera adjustment controls using the provided sample UI canvas (`StudentUI_Canvas`).
- Add interface elements for controlling visualization modes.
- Improve the interface to simplify teleoperation and reduce operator workload.
- Display useful robot or system status information.

**Expected Result:** An intuitive and functional operator interface for monitoring and interacting with the Husky robot.

*[Insert Screenshot 4: Example of the UI and relevant module settings]*

## 4. General Requirements

- Use the provided Unity project and existing robot model.
- Keep all implementations modular and organized. **Name each module and its scripts clearly** to simplify evaluation.
- Avoid unnecessary modifications to unrelated components.
- Ensure that the implemented functionalities work correctly in Unity Play mode.
- Students working with ROS topics may use provided sample or simulated data when a live ROS connection is unavailable.
- Coordinate with other students to ensure compatibility between the modules.

## 5. Evaluation and Grading

Each module will be graded out of **100 points**.

| Criteria | Points |
|---|---:|
| Correct implementation of assigned tasks | 30 |
| Functionality and integration | 25 |
| Code organization and explanation | 20 |
| Final demonstration | 25 |
| **Total** | **100** |

## 6. Final Submission

Each student must submit:

1. **Unity Implementation:** Completed scripts, modified assets, and relevant project files.
2. **Demonstration Videos:** A short individual demonstration (2–3 minutes) and a combined working prototype video (no fixed time limit).
3. **Final Presentation and Report:** A concise explanation of the implementation, testing, results, and any limitations.

The final demonstration should show the assigned functionality working in the existing warehouse scene and, where applicable, integrated with the other modules.

**Important:** The evaluation will focus on correct functionality, integration with the provided project, and the student's understanding of their implementation. Unnecessary complexity is not expected.
