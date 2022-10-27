# VEX 2022-2023 Spin Up Programming API References for 10/27/2022 Newer Driver Base

## Overview

This document will record all the methods as name and params for us to code the program faster and easier. This reference will only record the name and the data we need with this function.

## References

> ⚠️ All the functions and variables are classified by the hardward and its functions

### Intake

```cpp
void IntakeStartForward()
```

This function is used to control the intake. This function will let the intake to rotate forward.

```cpp
void IntakeStartReverse()
```

This function is used to control the intake, This function will let the intake to rotate reverse

By using these two methods, driver could collect the frisbees and roll the roller.

```cpp
void IntakeStop()
```

```cpp
void stopRoller()
```

⚠️**These two functions are the same. But for now the `IntakeStop()` method is the recommend method.**

This method could stop the intake motor group. Drivers could use this to stop rotating the intake.

```cpp
void autoRollerStart(int roller_color = 0)
```

⚠️**THIS METHOD IS ONLY FOR AUTONOMOUS**

Let the robot to rotate the roller till the target color we want in the autonomous. The chart below indicates the meaning stands by the different numbers.

| The number of `roller_color` | Meanings                                                         |
|:---------------------------- | ---------------------------------------------------------------- |
| `0`                          | Target color is **red**                                          |
| `1`                          | Target color is **blue**                                         |
| `2`                          | Auto pass the color compare (For testing the autonomous methods) |

### Flywheel

⚠️All the methods in this sectino is still in **Beta**.

```cpp
void HighGoalShooterStart()
```

Start spinning the Flywheel.

```cpp
void HighGoalShooterStop()
```

Stop spinning the Flywheel.

### Autonomous

```cpp
void init_auto()
```

This method will help to initializaed the optical and inertial sensors before and after running. The function will initial the following variables and properties:

`Drivetrain.setHeading(0, degrees);`

This method is also referenced by the other methods for autonomous. 

```cpp
void autoTurn(float degree = 0)
```

**⚠️THIS METHOD IS ONLY FOR AUTONOMOUS**

This method will help the robot to turn itself to a particular angel in autonomous.

If the `degree < 0`, the robot will turn `left`.

If the `degree > 0`, the robot will turn `right`.

**PLEASE REMBER** that everytime this method finished, the robot will automatically run the `init_auto` method to reset the headings. So everytime when you're setting up the angles, please use the relative angels instead of global angles.

### Autonomous Solutions

```cpp
void autonomous_solution_1(int roller_color)
```

This is the first solution for the autonomous. Use it by typing it inside the autonomus function.

For the `roller_color`, please refer: the `autoRollerStart` function and its color form.
