A controls system is the brains of the car, controlling the transmission to provide the optimal mix of torque and RPM at any given time. Internal combustion engines are limited to producing torque and power as per their torque-power curves. The torque power curve of the Kohler engine used on our Baja car is shown below:
![[Pasted image 20240907100915.png]]

>[!NOTE]
>Notice how the power peaks at around 3000 RPM. In a naturally aspirated engine, the power usually increases consistently (more engine speed = more combustion cycles = more power!). The Baja Kohler engine uses a restrictor plate to choke the intake airflow. After the 3000 RPM point, the fuel-air ratio becomes too rich, reducing the amount of power output by the engine.


A transmission (in our case an ECVT) greatly improves the mix of torque and RPM that we can produce. With a transmission, we are theoretically only limited by the power output at any given RPM.

>[!NOTE]
> Remember that $\tau = Force * Distance$ and $P = \tau * \omega$, where $\tau$ is torque and $P$ is power.



## What's Controls?
Controls gets its name from the field of [control theory](https://en.wikipedia.org/wiki/Control_theory), which is the study of controlling the outputs of dynamic systems and machines. We use control theory to, you guessed it, control our car's transmission ratio. 

## Why Controls?
Sure, we can control the transmission ratio...but what's the ultimate goal? What are we trying to control in our system and what do we want that to look like?

The answer is a complicated question, and is still currently under investigation. The naïve answer is to just target the maximal power output by adjusting the transmission so that the engine is constantly outputting peak power.

However, nonidealities like wheel and belt slip, along with inconsistent running conditions mean that the fastest car is often one that targets a lower power in favor of more torque! The exact ratio is something we experiment with throughout the year and car vary from car to car.

## How Does Controls Help?
Okay, so we can control exactly how much torque and RPM goes to the wheels and we want to provide the most *used* power possible. How does controls help with this? Let's take a deeper dive.

### No Transmission
If we simply coupled the engine straight to the wheels and ran the car, you would get the following simplified graph:
![[Pasted image 20240926200815.png]]

There are a couple of problems with this. The engine is not running at optimal RPM except for a little bit. It's really hard to start the car when you can't control how much torque you have at the low end.

In a manual transmission, we can control the transmission ratio to get a different looking graph.
![[Pasted image 20240926202704.png]]

When the transmission surpasses our target RPM, we can switch to a higher gear to put more load on the engine, slowing it down and maintaining our target RPM.

This graph looks a little discreet, as you usually only have around 6 defined gear ratios.

The graph of an [[ECVT|ECVT]] on the other hand, looks a little something like this:
![[Pasted image 20240926203031.png]]
We no longer have a single line for our output. Our transmission can take any number of paths to reach out target RPM and can be controlled to stay at our target RPM consistently.

By maximizing the time we spend at the target RPM, we can ensure that the car acts optimally and predictably! This is why we undertake the extra complication of building an [[ECVT|ECVT]].

The red curve is the idealized operation, but in practice, we see a lot more jitter and non-idealities.

## Control Inputs
Before we can control the ECVT, we must implement a few sensor inputs.
### Engine Speed
The engine speed sensor returns the rotary speed of the engine in RPM. Read [[Gear Tooth Sensors|the article on gear tooth sensors]] to learn more details. 

The engine speed sensor determines the short term reactions of the primary sheave. I highly recommend reading the [[ECVT]] description if the mechanical aspects are confusing.
### Wheel Speed
### Throttle and Brake Inputs

## Controller Details
### Feedback Control (PID)
### Feed Forward Inputs
### Results

## Improvements
### Tracking on Braking
### Response time
- Mushy Pedal
### Tuning Process
