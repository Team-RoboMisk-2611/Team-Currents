# CURRENT --- WRO Future Engineers 2026

## Contemplate · Create · Conquer

**Team:** Current\
**Category:** WRO Future Engineers\
**Season:** 2026

------------------------------------------------------------------------

## 1. About the Team

Current is a WRO Future Engineers team working on an autonomous
self-driving robot for the 2026 season.

Our documentation is organized around the complete engineering process:
planning, mechanical design, electronics, sensing, software, testing,
failures, improvements, and final reproducibility.

The purpose of this repository is not only to show the final robot. It
is intended to explain **why** the team made important engineering
decisions and how another team could reproduce the system.

### Team Roles

  Member   Main responsibility
  -------- ----------------------------------------------
  Darsh    Coding / Programming
  Ehaan    Electronics, construction, and documentation

> **To complete:** Add the official team member names/spelling exactly
> as used for WRO registration, coach/organization information, and team
> photo.

------------------------------------------------------------------------

## 2. Project Goal

The goal of Current is to develop a reliable autonomous vehicle capable
of completing the WRO Future Engineers challenge while making decisions
from onboard sensing and control software.

The robot is developed as an integrated system consisting of:

-   Mechanical chassis and drive system
-   Steering system
-   Motor and motor-control electronics
-   Power distribution
-   Sensors
-   Onboard computing
-   Camera/vision processing
-   Orientation/heading estimation
-   Autonomous decision-making
-   Testing and calibration

The team follows an iterative engineering process:

**Plan → Build → Test → Measure → Identify failure → Modify → Retest**

------------------------------------------------------------------------

## 3. Repository Structure

``` text
CURRENT-WRO-FE-2026/
│
├── README.md
│
├── engineering-journal/
│   ├── 01_team-and-project.md
│   ├── 02_mechanical-design.md
│   ├── 03_power-and-sensors.md
│   ├── 04_software-and-obstacle-strategy.md
│   ├── 05_systems-thinking.md
│   ├── 06_testing-and-iterations.md
│   └── 07_reproducibility.md
│
├── src/
│   └── README.md
│
├── schemes/
│   └── README.md
│
├── models/
│   └── README.md
│
├── t-photos/
│   └── README.md
│
├── v-photos/
│   └── README.md
│
├── video/
│   └── README.md
│
└── other/
    └── README.md
```

The folder structure follows the useful organization of the WRO Future
Engineers engineering-materials template: team photos, vehicle photos,
video, electrical schemes, source code, manufacturing models, and other
technical files.

------------------------------------------------------------------------

## 4. Engineering Approach

Current does not treat the robot as a collection of independent parts.
Mechanical, electrical, sensing, computation, and control decisions
affect one another.

For example:

-   Sensor placement affects what the camera can see.
-   Camera position affects the reliability of computer vision.
-   Power distribution affects the stability of the Raspberry Pi and
    motors.
-   Mechanical geometry affects turning behavior.
-   Heading estimation affects repeatability of turns.
-   Software decisions affect the required sensor update rate and
    processing load.
-   Testing results are used to decide whether a design should be kept
    or changed.

Every major design change should therefore be recorded with:

1.  The problem observed.
2.  Possible solutions considered.
3.  The selected solution.
4.  Why it was selected.
5.  Test conditions.
6.  Measured result.
7.  What changed in the next version.

------------------------------------------------------------------------

## 5. Mechanical Design

### 5.1 Chassis

**To complete with measured information:**

-   Overall chassis dimensions:
-   Wheelbase:
-   Track width:
-   Robot mass:
-   Ground clearance:
-   Chassis material:
-   Wheel type:
-   Drive motor:
-   Gear ratio:
-   Steering mechanism:

The final section must explain not only what the chassis looks like, but
why the dimensions and mechanism were selected.

### 5.2 Drive and Steering

Document:

-   How propulsion is generated.
-   How steering is generated.
-   How left/right or steering commands are converted into motor
    commands.
-   Motor speed and torque requirements.
-   Gear ratio reasoning.
-   Turning radius.
-   Mechanical limitations.
-   Stability during acceleration and turning.

### 5.3 Mechanical Iterations

For every version, record:

  Version   Problem       Change        Test          Result
  --------- ------------- ------------- ------------- -------------
  V1        To complete   To complete   To complete   To complete
  V2        To complete   To complete   To complete   To complete
  V3        To complete   To complete   To complete   To complete

------------------------------------------------------------------------

## 6. Power and Sensor Architecture

The power system must be documented as an architecture rather than only
a component list.

Include:

-   Main battery
-   Motor power path
-   Logic/electronics power path
-   Voltage regulators/buck converters
-   Motor controller
-   Raspberry Pi supply
-   Sensor supply
-   Grounding
-   Switches
-   Protection considerations
-   Estimated current draw

### Power Budget

  Subsystem          Voltage   Estimated current   Peak current Supply
  ---------------- --------- ------------------- -------------- --------
  Drive motors           TBD                 TBD            TBD TBD
  Steering servo         TBD                 TBD            TBD TBD
  Raspberry Pi           TBD                 TBD            TBD TBD
  Camera                 TBD                 TBD            TBD TBD
  IMU                    TBD                 TBD            TBD TBD
  Other sensors          TBD                 TBD            TBD TBD

### Sensor Documentation

For each sensor, explain:

-   What it measures.
-   Why it was selected.
-   Where it is mounted.
-   What field geometry it covers.
-   How it is calibrated.
-   What can cause incorrect readings.
-   What happens if the sensor fails.

Known development information to verify and document with the final
hardware photos/wiring is the use of a Raspberry Pi 5 (4 GB), Pi Camera
Module 3 Wide, and MPU6050 orientation sensing.

------------------------------------------------------------------------

## 7. Software Architecture

The software should be documented as modules rather than presented as
one large code listing.

Recommended structure:

``` text
src/
├── main.py
├── vision/
│   ├── color_detection.py
│   ├── obstacle_detection.py
│   └── camera.py
├── sensors/
│   └── imu.py
├── control/
│   ├── steering.py
│   ├── speed.py
│   └── heading.py
└── robot/
    └── state_machine.py
```

> Adjust this structure to match the actual repository. Do not create
> files that do not exist.

### State Machine

A final state diagram should explain states such as:

``` text
START
  |
  v
INITIALIZE
  |
  v
CALIBRATE
  |
  v
SEARCH / DETECT
  |
  +----> LANE / WALL FOLLOW
  |
  +----> OBSTACLE DETECTED
  |          |
  |          v
  |      AVOID OBSTACLE
  |          |
  |          v
  +------> RECOVER
             |
             v
          CONTINUE
```

Replace these names with the actual software states used by Current.

### Algorithms

For each algorithm, document:

-   Input
-   Processing
-   Output
-   Why the algorithm was selected
-   Alternatives considered
-   Tuning parameters
-   Failure cases
-   Test results

------------------------------------------------------------------------

## 8. Vision and Obstacle Strategy

The documentation must explain how the robot interprets the field rather
than simply saying that a camera is used.

For each visual feature/color/object:

  --------------------------------------------------------------------------
  Feature        Detection      Decision       Failure        Mitigation
                 method                        condition      
  -------------- -------------- -------------- -------------- --------------
  Red obstacle   TBD            TBD            TBD            TBD

  Green obstacle TBD            TBD            TBD            TBD

  Blue reference TBD            TBD            TBD            TBD

  Orange         TBD            TBD            TBD            TBD
  reference                                                   

  Black          TBD            TBD            TBD            TBD
  wall/lane                                                   
  --------------------------------------------------------------------------

Where computer vision is used, include:

-   Camera resolution
-   Region of interest
-   Color space
-   Threshold values
-   Filtering/morphology
-   Contour/object selection
-   Minimum/maximum object size
-   Decision thresholds
-   Lighting conditions
-   Calibration procedure
-   False-positive cases

------------------------------------------------------------------------

## 9. Heading and Turning

The Current development has used an MPU6050 for robot
orientation/movement work.

The final documentation should show:

1.  Sensor initialization.
2.  Bias/calibration procedure.
3.  Heading reset procedure.
4.  Heading measurement.
5.  Turn target.
6.  Turn completion condition.
7.  How drift/noise is handled.
8.  Testing results for repeated turns.

For a 90-degree turn, record the commanded angle and measured final
angle over multiple trials rather than reporting only one successful
run.

------------------------------------------------------------------------

## 10. Testing and Measurement

Testing is a required part of the engineering story.

Use measurable quantities such as:

-   Lap completion rate
-   Number of obstacle-detection errors
-   Number of unnecessary steering corrections
-   Turn-angle error
-   Average lap time
-   Maximum deviation from desired path
-   Motor temperature
-   CPU usage
-   Power stability
-   Sensor failure rate

### Test Log

  Test   Configuration     Runs   Successes   Failure Change
  ------ --------------- ------ ----------- --------- --------
  T01    TBD                TBD         TBD       TBD TBD
  T02    TBD                TBD         TBD       TBD TBD
  T03    TBD                TBD         TBD       TBD TBD

------------------------------------------------------------------------

## 11. Engineering Decisions and Trade-offs

For every important choice, use the format:

### Decision: \[Name\]

**Problem:**\
What problem did the team have?

**Options considered:**\
- Option A - Option B

**Chosen solution:**\
What was selected?

**Why:**\
Explain using measurements, testing, reliability, cost, weight,
processing, power, or field geometry.

**Result:**\
What changed after the decision?

**Remaining limitation:**\
What is still imperfect?

This format should be used for major mechanical, electrical, sensor,
software, and control decisions.

------------------------------------------------------------------------

## 12. Risk and Failure Analysis

  Failure mode          Cause   Effect   Detection   Mitigation   Test result
  --------------------- ------- -------- ----------- ------------ -------------
  Sensor misdetection   TBD     TBD      TBD         TBD          TBD
  Power instability     TBD     TBD      TBD         TBD          TBD
  Heading drift         TBD     TBD      TBD         TBD          TBD
  Wheel slip            TBD     TBD      TBD         TBD          TBD
  Camera glare          TBD     TBD      TBD         TBD          TBD

------------------------------------------------------------------------

## 13. Reproducibility

Another team should be able to understand and rebuild the robot from
this repository.

The repository should contain:

-   Complete source code
-   Wiring diagrams
-   CAD/STL files where applicable
-   Robot photographs
-   Software installation instructions
-   Hardware list
-   Sensor calibration procedure
-   Build/assembly information
-   Testing procedure
-   Version/release information

### Software Setup

**Operating system:** TBD\
**Python version:** TBD\
**Required libraries:** TBD\
**Camera setup:** TBD\
**GPIO configuration:** TBD\
**I2C configuration:** TBD\
**How to run:** TBD

------------------------------------------------------------------------

## 14. Version History

  Version   Date   Major change          Reason           Result
  --------- ------ --------------------- ---------------- --------
  V0.1      TBD    Initial prototype     Starting point   TBD
  V0.2      TBD    TBD                   TBD              TBD
  V1.0      TBD    Competition version   TBD              TBD

------------------------------------------------------------------------

## 15. Git Commit Strategy

Use meaningful commits instead of generic messages.

Good examples:

``` text
Initial robot documentation structure
Added mechanical CAD and dimensions
Added electrical wiring diagram
Implemented camera color detection
Added MPU6050 heading calibration
Improved obstacle detection thresholds
Added state machine for autonomous control
Documented testing results
Updated final competition configuration
```

At least three meaningful commits should show the development process.

------------------------------------------------------------------------

## 16. Final Documentation Checklist

-   [ ] Team information completed
-   [ ] Robot dimensions added
-   [ ] Mechanical diagrams added
-   [ ] Torque/speed reasoning added
-   [ ] Power diagram added
-   [ ] Power budget added
-   [ ] Sensor placement documented
-   [ ] Sensor calibration documented
-   [ ] Software flowchart added
-   [ ] Obstacle strategy explained
-   [ ] Testing data added
-   [ ] Design iterations documented
-   [ ] Trade-offs explained
-   [ ] Risk/failure analysis added
-   [ ] CAD files uploaded
-   [ ] Wiring files uploaded
-   [ ] Complete code uploaded
-   [ ] Robot photos uploaded
-   [ ] Video link added
-   [ ] README is at least 5000 characters
-   [ ] At least 3 meaningful commits are present
-   [ ] Another team can understand how to reproduce the robot
