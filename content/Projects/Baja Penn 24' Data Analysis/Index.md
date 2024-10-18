---
title: Baja Data Analysis
---
Data analysis is a critical component to the engineering design cycle. Without data, one cannot make informed design decisions. Thanks to the infrastructure set up on the Baja electronics team, we were able to collect around **30 million** data points over the course of a 4 hour race in Pennsylvania.

## Background

The data analysis will focus on M23's endurance race run at the Pennsylvania College of Technology in Williamsport, Pennsylvania. The data spans over the course of 5.2 hours, with the race itself being 4 hours.

The weather was sunny, with mild humidity.

During the course of the race, we pitted 4-5 times, with the last pitting being after multiple failures of the drivetrain, limiting the car to 1WD :).

## Breakdown of Variables

- cycle_start_us
> The microsecond counter of the [[Teensy 4.1|Teensy microcontroller]]. This variable is used as the main time base for all data analysis. 


> [!NOTE] 
> The microsecond counter is stored in a long long, and will overflow at certain points in the log. This just means that the counter will wrap around to 0.



- **engine_rpm**
> The RPM (rotations per minute) of the engine, before being filtered. This value should only range from around 1800 - 3800 (idle to max legal engine RPM).

- **filtered_engine_rpm**
>The RPM of the engine, but passed through an IIR low pass filter. This value is used in the [[M23 Controls|controls]] cycle.

- **secondary_rpm**
>The RPM of the secondary sheave, the output of the ECVT.

- **filtered_secondary_rpm**
>The RPM of the secondary sheave, filtered through a low pass IIR filter. This value is also used on the car, but exactly how it's used shall not be disclosed.

- **target_rpm**
> The current engine RPM value that the transmission's PID controller is trying to target. In controls, this is know as a setpoint or reference!

- **velocity_command**
> The speed that the [[Odrive Pro|Odrive]] is commanded to move at. Measured in rotations per second.

- **velocity_estimate**
>The Odrive's estimate of it's current speed based on the motor's encoder. Velocity estimate and velocity command values can diverge based on the tuning scheme of the Odrive and based on our velocity ramping coefficient.

- **position_estimate**
> The position estimate is the current position of the Odrive, as measured by the encoder. Measurement unit is unknown...

- **bus_voltage**
> The voltage the Odrive measures at the battery input terminals. For M23, nominal battery voltage was 48V. 

- **bus_current**
> The current flow the Odrive measures at the battery input terminals. Positive currents indicate battery consumption, while negative current indicate regenerative braking.

- **iq_measured**
> The current flow in the phases of the BLDC motor. This value directly corresponds to the torque of the motor through a constant defined by the motor itself. This value is also the basis upon which the Odrive achieves torque control.

- **iq_setpoint**
> The target value of the Odrive's internal motor PID controller.

- **inbound_limit_switch**
> A 0/1 value corresponding to whether or not the inbound limit switch has been pressed. The variable is 1 if the switch has been pressed. The inbound switch is the switch closest to the engine and indicates to the system that the maximum transmission ratio has been reached.

- **outbound_limit_switch**
> A 0/1 value corresponding to whether or not the outbound limit switch has been pressed. The variable is 1 if the switch has been pressed. The outbound switch sits the farthest away from the engine, and tell the engine that the clutch position has been achieved. The clutch position means that the engine and transmission are decoupled.

- **engage_limit_switch**
> A 0/1 value corresponding to whether or not the engage limit switch has been pressed. 1 if switch is pressed. The engage switch sits in between outbound and inbound and sits right at the edge of belt engagement.

- **throttle**
> A value ranging from 0 to 1, indicating the percentage of throttle travel achieved. 1 indicates the throttle has been pressed all the way through its travel and 0 corresponds to the throttle not being pressed at all.

- **brake**
> A value ranging from 0 to 1, indicating the percentage of brake travel achieved. 1 indicates the brakes are pressed all the way and 0 corresponds to the brakes not being pressed at all.

- **d_throttle**
> Derivative of the throttle measurement

## Data Cleaning

- **cycle_start_us** must be processed to provide continuation when it overflows and wraps around. A short Python script is provided to accomplish that. Please adjust for your use case:
```python
# Detect and fix the cycle_start_us values
adjustment = 0
max_seen = 0
new_values = []

for i in range(len(df)):
    if i > 0 and df['cycle_start_us'][i] < df['cycle_start_us'][i-1]:
        # Loop detected, add the last max_seen value to adjustment
        adjustment += max_seen
        max_seen = 0  # Reset max_seen for the new cycle
    max_seen = max(max_seen, df['cycle_start_us'][i])
    new_values.append(df['cycle_start_us'][i] + adjustment)

# Create a new dataframe with the fixed cycle_start_us
df_fixed = df.copy()
df_fixed['cycle_start_us'] = new_values
```

## Analysis

### Electrical Power Analysis
In this section, we explore the current data (**bus_current**) as well as the voltage data (**bus_voltage**) to gain insight into the power usage of the actuator. This section will provide statistics about power consumption (helping us justify the power of the motor), voltage sag (shows the health and capacity of the battery), and current draw (provides information about torque and allows us to spec the right size battery).

#### Bus Current Consumption Over Time


#### Current Consumption Distribution
- What distribution does the current consumption roughly follow, and what current do we need to support to capture 95% of current consumption cases?

#### Bus Voltage Consumption Over Time


#### Total Current Consumption Over Endurance 
- integral

#### Total Voltage Sag Over Endurance 
- (difference
#### Electrical Power Consumption Over Time

#### Total Electrical Power Consumption 
- Watt Hours

### Controls Performance Analysis
In this section, we want to gain insight into the software side of the car's performance. This section will provide insight into the efficiency of the code, potential bottlenecks for controls, and hopefully give us direction for future controls improvements. 

#### Velocity Command vs Time

#### Engine RPM vs Time

#### Filtered Engine RPM vs Engine RPM
- Correlation, data loss

#### Target RPM vs Engine RPM and Difference
- Perspective on tracking performance

#### Cycle Tick Consistency
- Consistency of controls system evaluation.

### Actuator Mechanical Analysis
In this section, we explore the main mechanical characteristics of the actuator. 
#### Velocity Command Over Time

#### Velocity Estimate Over Time

#### Velocity Command Vs. Velocity Estimate. 
- Difference between the two.
- Provides insight into how well the inner motor control loop is tracking our commands. (filtered and unfiltered)

#### Position Estimate Over Time

#### Actuator Utilization 
- (histogram of actuator position when outbound limit switch is not activated)

#### Limit Switch Repeatability
- Histogram of actuator position when inbound limit switch activated. Provides insight into accuracy of actuator position estimate and our motor's stopping ability.
- Histogram of actuator position when outbound limit switch activated

#### Actuator Torque
- Torque applied over time. Can use electrical power from previous section as "total power". Be careful of units, velocity estimate is in rotations/sec.


### Vehicle Dynamic Analysis
In this section we explore data analysis that's not necessarily linked to one part of the car, but to the performance of the car as a whole.

#### Wheel Speed Analysis
#### Car Speed Analysis

#### Engine RPM Analysis
- Engine RPM over time
- Histogram of Engine RPM

### Miscellaneous Analysis[](http://localhost:8888/lab#Miscellaneous-Analysis)
#### Throttle Position
- Vs time 
- Histogram
#### Brake Position
- Brake vs Time
- Histogram of Brake
#### Derivative of throttle
- d_throttle vs Time
- Histogram of d_throttle

