# 04 --- Software Architecture and Obstacle Strategy

## 4.1 Software Overview

The software is responsible for:

1.  Initializing hardware.
2.  Reading sensors.
3.  Capturing camera frames.
4.  Detecting field features/obstacles.
5.  Estimating robot state.
6.  Selecting an autonomous behavior.
7.  Controlling drive and steering.
8.  Recovering from incorrect or unexpected conditions.

## 4.2 Software Modules

Document the actual files used by the final code.

  Module          Responsibility
  --------------- ----------------
  Main            TBD
  Camera          TBD
  Vision          TBD
  IMU             TBD
  Motor control   TBD
  Steering        TBD
  State machine   TBD

## 4.3 State Machine

The final repository should include a state-machine diagram.

Suggested documentation structure:

``` text
INITIALIZE
   |
   v
CALIBRATE
   |
   v
DETECT FIELD
   |
   +----> FOLLOW
   |
   +----> OBSTACLE
              |
              v
           AVOID
              |
              v
           RECOVER
              |
              v
           FOLLOW
```

Replace with the actual Current state machine.

## 4.4 Computer Vision

Document:

-   Camera resolution
-   ROI
-   Color space
-   Threshold values
-   Image filtering
-   Morphological processing
-   Contour detection
-   Object selection
-   Decision logic
-   False detections
-   Lighting tests

The team should include actual before/after images for important vision
improvements.

## 4.5 Obstacle Strategy

For each obstacle type, document:

-   How it is detected.
-   Where it is located in the image.
-   How its position is calculated.
-   How the robot decides which side to pass.
-   How the robot returns to the desired path.
-   What happens if the obstacle is only partially visible.

## 4.6 Heading and Turns

Document the MPU6050 heading process:

-   Calibration
-   Heading reset
-   Target angle
-   Turn control
-   Stop condition
-   Drift correction
-   Repeated-turn test results

## 4.7 Tuning

Record software tuning as experiments rather than only final values.

  Parameter     Old value   New value Test result   Reason
  ----------- ----------- ----------- ------------- --------
  TBD                 TBD         TBD TBD           TBD
  TBD                 TBD         TBD TBD           TBD

## 4.8 Edge Cases

Document behavior when:

-   No obstacle is detected.
-   Multiple obstacles are detected.
-   A color is incorrectly detected.
-   The camera image is partially blocked.
-   IMU heading drifts.
-   A turn is overshot.
-   A motor does not respond.
-   Sensor data becomes invalid.
