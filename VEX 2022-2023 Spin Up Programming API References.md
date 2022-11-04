# VEX 2022-2023 Spin Up Programming API References for 10/27/2022 Newer Driver Base

## Overview

This document will record all the methods as name and params for us to code the program faster and easier. This reference will only record the name and the data we need with this function.

## References

> ⚠️ All the functions and variables are classified by the hardward and its functions

### Global Variables
```cpp
bool drivetrainSlowSpeed = false;
float intake_velocity = 600; //rpm
float high_goal_speed = 100; //pct
float moving_velocity = 600; //rpm
float turning_velocity = 600; //rpm
```

`drivetrsinSlowSpeed` used to control the driving mode for the robot. **This method has already abandonded**
`intake_velocity` set up the speed for the intake
`high_goal_speed` set up the speed for the fly wheel
`moving_velocity` set up the driving speed
`turning_velocity` set up the turning speed in all situation

### Driverbase Driving Speed

```cpp
void setSpeedToHigh()
```

This function will set the driving speed to full (normal)

```cpp
void setSpeedToLow()
```

This function will set the driving speed to slow speed (1/2 normal)

### Intake

```cpp
void IntakeStartForward()
```

This function is used to control the intake. This function will let the intake to rotate forward.

------

```cpp
void IntakeStartReverse()
```

This function is used to control the intake, This function will let the intake to rotate reverse

By using these two methods, driver could collect the frisbees and roll the roller.

------

```cpp
void IntakeStop()
```

> ⚠️**Method `StopRoller()` has been abandoned since Nov. 1 2022**

This method could stop the intake motor group. Drivers could use this to stop rotating the intake.

------

```cpp
void autoRollerStart(int roller_color = 0)
```

> ⚠️**THIS METHOD IS ONLY FOR AUTONOMOUS**

Let the robot to rotate the roller till the target color we want in the autonomous. The chart below indicates the meaning stands by the different numbers.

| The number of `roller_color` | Meanings                                                         |
|:---------------------------- | ---------------------------------------------------------------- |
| `0`                          | Target color is **red**                                          |
| `1`                          | Target color is **blue**                                         |
| `2`                          | Auto pass the color compare (For testing the autonomous methods) |

------

### Flywheel

> ⚠️All the methods in this sectino is still in **Beta**.

```cpp
void FlyWheelStart()
```

Start spinning the Flywheel.

------

```cpp
void FlyWheelSlowStart()
```

Start spinning the Flywheel in 25% speed

------

```cpp
void FlyWheelStop()
```

Stop spinning the Flywheel.

------

### Autonomous

```cpp
void init_auto()
```

This method will help to initializaed the optical and inertial sensors before and after running. The function will initial the following variables and properties:

`Drivetrain.setHeading(0, degrees);`

This method is also referenced by the other methods for autonomous. 

------

```cpp
void autoTurn(float degree = 0)
```

> **⚠️THIS METHOD IS ONLY FOR AUTONOMOUS**

This method will help the robot to turn itself to a particular angel in autonomous.

If the `degree < 0`, the robot will turn `left`.

If the `degree > 0`, the robot will turn `right`.

**PLEASE REMBER** that everytime this method finished, the robot will automatically run the `init_auto` method to reset the headings. So everytime when you're setting up the angles, please use the relative angels instead of global angles.

------

### Autonomous Solutions

> **⚠️ AUTONOMOUS SOLUTIONS are redesigning because of the change of new driver base since Nov 1 2022. These methods below are not reliable.**

```cpp
void autonomous_solution_1(int roller_color)
```

This is the first solution for the autonomous. Use it by typing it inside the autonomus function.

For the `roller_color`, please refer: the `autoRollerStart` function and its color form.

------
