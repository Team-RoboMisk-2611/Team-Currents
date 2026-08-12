# 03 --- Power and Sensor Architecture

## 3.1 System Power Architecture

Create a wiring diagram showing:

``` text
Main Battery
    |
    +---- Motor Power
    |
    +---- Voltage Regulator
              |
              +---- Raspberry Pi
              +---- Sensors
              +---- Camera / other electronics
```

Replace this conceptual diagram with the actual electrical schematic.

## 3.2 Power Budget

  Device             Voltage   Typical Current   Peak Current Supply
  ---------------- --------- ----------------- -------------- --------
  Drive system           TBD               TBD            TBD TBD
  Steering               TBD               TBD            TBD TBD
  Raspberry Pi 5         TBD               TBD            TBD TBD
  Camera                 TBD               TBD            TBD TBD
  MPU6050                TBD               TBD            TBD TBD
  Other                  TBD               TBD            TBD TBD

Explain how the regulator and battery were selected based on the
measured or estimated load.

## 3.3 Raspberry Pi

The development system includes a Raspberry Pi 5 with 4 GB RAM.

Document:

-   OS version
-   Power supply
-   GPIO connections
-   I2C configuration
-   Software environment
-   Boot/run procedure

## 3.4 Camera

The development system includes a Pi Camera Module 3 Wide.

Document:

-   Mounting height
-   Mounting angle
-   Resolution
-   Exposure
-   Gain
-   Region of interest
-   Lighting conditions
-   Calibration

Explain how camera position affects field visibility and detection
reliability.

## 3.5 MPU6050

The MPU6050 is used for orientation/movement work.

Document:

-   VCC
-   GND
-   SDA
-   SCL
-   I2C address
-   Calibration
-   Gyroscope bias
-   Heading reset
-   Turn measurement
-   Drift handling

The final wiring diagram should match the actual robot.

## 3.6 Sensor Placement

For every sensor, explain why its position was selected using field
geometry.

  Sensor         Position   Purpose       Why this position?
  -------------- ---------- ------------- --------------------
  Camera         TBD        Vision        TBD
  MPU6050        TBD        Orientation   TBD
  Other sensor   TBD        TBD           TBD

## 3.7 Failure Considerations

Document possible failures:

-   Camera glare
-   Sensor noise
-   Loose wiring
-   Voltage drop
-   Electrical interference
-   I2C communication failure
-   Mechanical vibration

For each, describe the detection and mitigation method.
