# Design and Simulation of a Self-Balancing Bot

A two-wheeled self-balancing robot, modelled in **SolidWorks** and simulated in **MATLAB Simulink (Simscape Multibody)**, stabilised with **PID** and **LQR** control.

> **Guide:** Prof. D. Ezhilarasi, Dept. of Instrumentation and Control Engineering, NIT Tiruchirappalli

![LQR Controller in action](images/lqr_action.gif) 

## Aim
Model a complete self-balancing bot and balance it within a given time using a suitable control algorithm.

## CAD Model

Isometric view
<img width="1287" height="795" alt="image" src="https://github.com/user-attachments/assets/7eaf8b2b-296a-4761-82fc-e092b459b9a6" /> 

- Chassis, middle frame, head, supports and rubber-gripped wheels designed in SolidWorks.
- Electronics and motors imported from GrabCAD and assembled using mates.
- **Planned hardware:** Arduino UNO, IMU (I2C), L298N motor driver, Bluetooth module, N-20 (BO) DC motors, battery.

### Physical Parameters (from SolidWorks)
| Parameter | Value |
|---|---|
| Mass | 2725.75 g |
| Centre of mass (mm) | X = -288.55, Y = -88.65, Z = 1.78 |
| Ixx (about wheel axis) | 79225670.88 |

## Simulation
- CAD exported as STL and imported into Simscape Multibody using File Solid blocks.
- Equations of motion derived with Euler-Lagrange and linearised about the upright position (θ = 0).

![Simscape block diagram](images/simscape_block_diagram.png)

## Control

### PID
A 10° → 1° step acts as the initial disturbance. The tilt angle settles at the 1° setpoint in **about 3 s**.

![Scope output](images/scope_output.png)

### LQR
Gains obtained from the Riccati equation with u = -Kx:

```
K = [-1.000, -1.385, -100.435, -7.596]
```

## Tools
SolidWorks · MATLAB · Simulink · Simscape Multibody

## Status
Ongoing. LQR is being explored for easier tuning and smoother control, with hardware implementation to follow.


<img width="1287" height="795" alt="image" src="https://github.com/user-attachments/assets/7eaf8b2b-296a-4761-82fc-e092b459b9a6" />
