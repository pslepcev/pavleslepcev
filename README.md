[README_1.md](https://github.com/user-attachments/files/32269709/README_1.md)
# Pavle Slepcev

**Mechanical and Space Engineering student at the University of Pittsburgh (Class of 2028).**

Drivetrain sub-lead on Pitt's Formula SAE electric team and co-founder of WASP, a computer-vision navigation project for drones. I like problems where the analysis has to survive contact with hardware — a truss that actually gets loaded to failure, a homography that has to hold up at 50 m in real wind.

Currently looking for a **Summer 2027 engineering internship or co-op**. Open to relocation.

[Portfolio](https://sites.google.com/view/pavleslepcev/home) · [LinkedIn](http://www.linkedin.com/in/pavle-slepcev-bb39b5384) · pslepcev@gmail.com

---

## Projects

| Project | What it is | Stack |
|---|---|---|
| [WASP — GPS-denied drone navigation](https://sites.google.com/view/pavleslepcev/projects/drone-navigation) | Absolute position fixes with no GNSS and no radio link, by registering downward camera frames against satellite imagery | ROS 2, OpenCV, Jetson Orin Nano, SOLIDWORKS |
| [Idí-Run](https://sites.google.com/view/pavleslepcev/projects/id%C3%AD-run-app) | iOS run tracker where your GPS trail captures territory on a shared live map | SwiftUI, Supabase/PostGIS, Apple Intelligence |
| [6-DOF robot arm](https://sites.google.com/view/pavleslepcev/projects/6-dof-robot-arm) | My own variation on the open-source BCN3D Moveo — six steppers, belt-driven joints, fully 3D printed | Arduino Mega + RAMPS, SOLIDWORKS, FDM |
| [Bridge truss optimizer](https://sites.google.com/view/pavleslepcev/projects/bridge-design-matlab) | Gradient-descent joint-position optimizer for a poplar truss bridge, verified in FEA | MATLAB, SOLIDWORKS |
| [Custom keyboard PCB](https://sites.google.com/view/pavleslepcev/projects/custom-keyboard-pcb) | 87-key TKL mechanical keyboard designed end to end, schematic through board layout | KiCad 10, STM32F072, QMK |

### WASP — absolute position without GPS

Each fix ties to a satellite map tile rather than to the previous estimate, so error never compounds the way it does in visual odometry or inertial dead reckoning. ORB keypoints, Lowe ratio test at 0.75, RANSAC-verified homography against a 3×3 mosaic of zoom-20 tiles, running onboard in ROS 2.

Flight-tested on a DJI Phantom 3 carrying a Jetson Orin Nano and IMX477 camera, 560 g payload on a carbon-fiber-reinforced nylon mount with a six-damper isolator (18 Hz natural frequency, 0.065 transmissibility at motor frequency).

**Results:** 13 successful match events across 7 flights; the last two produced absolute fixes within 10 m of origin, mean horizontal error 8 m against the aircraft's own ±3 m GNSS. Prototype 2 adds a rangefinder, an IMU, and a two-axis gimbal to collapse the 8-DOF estimate to a 2D transform.

### Bridge truss optimizer

Four-person project, December 2025 — I was project manager and wrote the optimizer. Instead of sizing members by hand, `OptimizeBridge.m` runs gradient descent on joint positions against an objective that penalizes the worst-stressed member while favoring tension over compression via a softmax. Symmetry is enforced as a constraint. Half the optimized truss was rebuilt in SOLIDWORKS under identical loading; member forces matched the solver.

**Results:** 994 lb held at 244 g of poplar and $10.17 of material — performance index 187.9, top three in the class. Failure came in a mid-span cross-member rather than the one flagged as critical, which was the real lesson: load paths move as the structure deforms.

### Custom keyboard PCB

87-key ANSI TKL, 373.7 × 188.8 mm, two-layer FR-4, 234 components. STM32F072CBT6 with crystal-less USB, 6×17 ROW2COL matrix with per-key diodes, Kailh hot-swap sockets, 16 WS2812B underglow LEDs behind a 74AHCT1G125 level shifter, USB-C in through an XC6206 LDO with a USBLC6-2SC6 ESD array and a resettable fuse. QMK firmware. 152/152 nets connected, 0 DRC errors — boards ordered from JLCPCB.

---

## Skills

**CAD** — SOLIDWORKS (pursuing CSWP), AutoCAD, Fusion 360
**Drivetrain & gearing** — KISSsoft; ISO 6336, DIN 3990, AGMA
**Electronics** — KiCad schematic capture and PCB layout
**Programming & analysis** — MATLAB, Python, Swift/SwiftUI, Supabase, ROS 2, OpenCV
**Coursework** — Space Engineering, Measurements + Lab, Mechanical Design I, Dynamic Systems, Simulation and Design

---

## Elsewhere

Native Serbian speaker. I also run a weekly cooking channel on international recipes, recently past 10,000 views.

Reach me at **pslepcev@gmail.com** or **pas346@pitt.edu**.
