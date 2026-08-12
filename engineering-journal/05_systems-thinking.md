# 05 --- Systems Thinking and Engineering Decisions

## 5.1 System Block Diagram

``` text
                  +----------------+
                  |   Camera       |
                  +-------+--------+
                          |
                          v
+-----------+      +-------------+      +----------------+
| MPU6050   |----->| Raspberry Pi|----->| Motor/Steering |
+-----------+      | Processing  |      | Controller     |
                   +-------------+      +----------------+
                          |
                          v
                   Autonomous
                   Decision Logic

        Battery ---> Power Distribution ---> Electronics
                          |
                          +-----------------> Motors
```

Replace this conceptual diagram with the final system architecture.

## 5.2 Subsystem Interaction

Explain how:

-   Mechanical design supports sensing.
-   Sensors provide information to software.
-   Software generates control commands.
-   Power electronics supply each subsystem.
-   Mechanical response affects sensor measurements.
-   Testing feeds information back into design.

## 5.3 Engineering Constraints

Document actual constraints involving:

-   Weight
-   Dimensions
-   Power
-   Processing
-   Component availability
-   Mechanical space
-   Sensor field of view
-   Time
-   Reliability

## 5.4 Design Trade-offs

For every important trade-off, use:

**We considered X and Y.**

**X advantage:** ...

**Y advantage:** ...

**We selected X because:** ...

**Test evidence:** ...

**Result:** ...

## 5.5 Risk Analysis

  Risk                  Probability   Impact   Mitigation   Evidence
  --------------------- ------------- -------- ------------ ----------
  Camera misdetection   TBD           TBD      TBD          TBD
  Power instability     TBD           TBD      TBD          TBD
  Heading drift         TBD           TBD      TBD          TBD
  Wheel slip            TBD           TBD      TBD          TBD
  Loose wiring          TBD           TBD      TBD          TBD

## 5.6 Iteration Story

The documentation should show how the robot evolved.

### Version 1

Problem:

Change:

Result:

### Version 2

Problem:

Change:

Result:

### Version 3

Problem:

Change:

Result:

The strongest evidence is numerical testing showing why the next version
was built.
