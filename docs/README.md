# Autonomous Line Following Robot

A small two-wheel robot that follows a black line on the floor using
five infrared sensors and an Arduino Nano. I'm designing the body
myself in Fusion 360 so it can be 3D printed.

## Status
The CAD, the circuit plan and the code are done. I haven't built or
tested the robot yet, so the code has not run on real hardware.

## What's in this repo
- cad/ the chassis in Fusion 360 (.f3d) and as an STL
- code/ the Arduino sketch
- docs/ circuit diagram, pin map and parts list

## How it works
The sensors read the line, and the code works out how far the line is
from the center. The motors speed up or slow down to steer back on
track. It uses the P and D parts of PID control.

## Parts
| Component | Qty | Purpose |
|---|---|---|
| Arduino Uno or Nano | 1 | Main controller: reads the sensors, runs the line following and PID code, and drives the motors |
| 5-channel IR sensor array (TCRT5000 type) | 1 | Looks down at the floor to tell the black line from the white surface |
| TB6612FNG motor driver module | 1 | Drives the left and right motors with speed and direction control, and wastes much less power than an L298N |
| TT gear motors with wheels | 2 | Two-wheel differential drive: the robot steers by running one wheel faster than the other |
| Ball caster | 1 | Third support point at the rear so the robot balances |
| 18650 Li-ion cell | 2 | Battery pack in series (2S) |
| 2-slot 18650 holder | 1 | Holds the two cells |
| 2-bay 18650 charger | 1 | Charges the cells outside the robot |
| Adjustable buck converter module | 1 | Gives the Arduino and sensors a steady 5V, separate from the motor power |
| Latching power switch | 1 | On/off switch on the robot |
| Capacitor assortment | 1 | Smooths the power rails |
| Resistor assortment | 1 | Current limiting and pull-ups |
| Breadboard | 1 | Prototype the wiring before soldering |
| Jumper wire set | 1 | Prototype wiring |
| Silicone wire 22AWG | 1 | Power and motor wiring |
| M3 screw and standoff assortment | 1 | Mounts the Arduino, motors and sensor bar on the chassis |
| 3D-printed chassis (own design) | 1 | Base plate, motor mounts, sensor bracket and battery holder designed in Fusion 360 |

## Known gaps
- The caster is not modelled yet.
- The sizes of the motor, battery and sensor board come from typical
  listings and need to be checked against the real parts.
- Sensor threshold and steering values (Kp and Kd) are starting
  guesses that need tuning on a real track.
