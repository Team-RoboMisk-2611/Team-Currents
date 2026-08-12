# 06 --- Testing and Iterations

## 6.1 Testing Philosophy

Current uses testing to convert observations into engineering decisions.

A test should identify:

-   What was changed.
-   What was measured.
-   How many trials were performed.
-   What failed.
-   What improved.
-   What remains to be improved.

## 6.2 Mechanical Tests

  Test                      Runs   Success   Failure Metric
  ----------------------- ------ --------- --------- --------
  Straight-line driving      TBD       TBD       TBD TBD
  90° turn                   TBD       TBD       TBD TBD
  Full lap                   TBD       TBD       TBD TBD

## 6.3 Vision Tests

  Test   Lighting   Object             Detection accuracy Main failure
  ------ ---------- ---------------- -------------------- --------------
  V01    TBD        Red                               TBD TBD
  V02    TBD        Green                             TBD TBD
  V03    TBD        Reference line                    TBD TBD

## 6.4 Heading Tests

Record repeated turns.

    Trial   Target   Final heading   Error
  ------- -------- --------------- -------
        1      90°             TBD     TBD
        2      90°             TBD     TBD
        3      90°             TBD     TBD
        4      90°             TBD     TBD
        5      90°             TBD     TBD

## 6.5 Full Robot Tests

  Test   Configuration     Runs   Successful runs   Success rate
  ------ --------------- ------ ----------------- --------------
  T01    TBD                TBD               TBD            TBD
  T02    TBD                TBD               TBD            TBD

## 6.6 Failure → Change → Result

Use this format for major problems.

### Problem

Describe exactly what happened.

### Investigation

Explain what the team measured or observed.

### Change

Explain the engineering change.

### Retest

Repeat the same test where possible.

### Result

Record numerical improvement.

### Decision

Explain whether the change was kept or reverted.
