# quadrotor-control

Development of a complete quadrotor modeling and control architecture in MATLAB/Simulink, from motor-propeller dynamics to embedded implementation on STM32.

## Drone Specifications

| Parameter | Value |
| Configuration | Quadrotor |
| Total mass | 1.5 kg |
| Propeller | 10 × 4.7 in |
| Propeller radius | 0.127 m |
| Battery | LiPo 3S – 11.1 V |
| ESC | 20 A |
| Flight controller | STM32 |
| Thrust coefficient (CT) | 0.0165 |
| Torque coefficient (CQ) | 0.00214 |
| Air density | 1.225 kg/m³ |

## Current Development

The project currently includes a nonlinear quadrotor simulation with:

- Brushless motor electrical and mechanical dynamics
- Propeller aerodynamic model
- PI motor speed control
- Four-motor integration
- Quadrotor mixer
- Nonlinear attitude dynamics
- Nonlinear translational dynamics
- Roll, pitch and yaw control
- Altitude control
- Horizontal position control
- Cascaded control architecture

The motor-propeller subsystem uses the **Rotor** block from the MATLAB/Simulink **Aerospace Blockset**.

The current propeller model is based on a **10 × 4.7 in propeller** and, in this first version, assumes constant thrust and torque coefficients.

## Motor-Propeller Model

The motor-propeller subsystem includes:

- Thrust-to-angular-speed conversion
- PI motor speed controller
- Electrical motor dynamics
- Mechanical motor dynamics
- Propeller thrust calculation
- Propeller aerodynamic torque calculation

The PI controller gains were tuned to obtain a fast response suitable for the cascaded control architecture.

Tests performed at **400, 600 and 800 rad/s** resulted in settling times of approximately **0.2 to 0.3 s**.

## Current Status

The main simulation architecture is already implemented and functional.

The current development stage is focused on:

- Translating and standardizing the model in English
- Reviewing and validating the implemented dynamic equations
- Robustness analysis
- Parameter sensitivity analysis
- Validation under different operating conditions
- Controller performance evaluation

## Future Work

After the simulation model is validated, the next stages will include:

- Experimental validation of the motor-propeller model
- Integration with real ESCs and motors
- Embedded implementation on STM32
- Comparison between simulation and experimental results
- Flight testing
