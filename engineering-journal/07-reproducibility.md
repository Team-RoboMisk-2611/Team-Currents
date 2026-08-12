# 07 --- Reproducibility and GitHub Quality

## 7.1 Goal

Another team should be able to understand the robot and reproduce its
construction, electronics, software setup, and autonomous behavior using
the repository.

## 7.2 Required Repository Content

-   [ ] README.md
-   [ ] Engineering journal
-   [ ] Complete source code
-   [ ] Wiring diagram
-   [ ] CAD/STL files where applicable
-   [ ] Robot photographs
-   [ ] Team photograph
-   [ ] Video link
-   [ ] Hardware list
-   [ ] Software installation instructions
-   [ ] Sensor calibration instructions
-   [ ] Testing procedure
-   [ ] Version history

## 7.3 Build Procedure

Document:

1.  Chassis assembly.
2.  Motor installation.
3.  Steering installation.
4.  Electronics mounting.
5.  Wiring.
6.  Sensor mounting.
7.  Camera mounting.
8.  Software installation.
9.  Sensor calibration.
10. Autonomous test.

## 7.4 Software Setup

**OS:** TBD

**Python:** TBD

**Libraries:**

``` text
TBD
```

**Run command:**

``` text
TBD
```

## 7.5 Wiring

Place the final wiring diagram in:

``` text
schemes/
```

The diagram should show every electrical component and the connections
between them.

## 7.6 CAD

Place CAD/STL/STEP files in:

``` text
models/
```

Use meaningful filenames and version numbers.

## 7.7 Versioning

Use releases for important milestones.

Example:

``` text
v0.1 — First autonomous prototype
v0.5 — Stable obstacle detection
v1.0 — Regional competition configuration
v2.0 — Final competition configuration
```

## 7.8 Commit History

Use meaningful commit messages.

Examples:

-   `Added initial mechanical CAD`
-   `Added complete wiring diagram`
-   `Implemented MPU6050 heading reset`
-   `Improved obstacle detection`
-   `Added autonomous state machine`
-   `Documented final testing`

Avoid messages such as `update`, `changes`, or `final final`.
