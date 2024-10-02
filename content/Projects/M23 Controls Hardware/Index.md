---
title: M23 Controls Hardware
---
![[Pasted image 20240907163034.png]]
Hi! My name is [Rama](https://www.linkedin.com/in/ramaditya-kotha/), and I was the controls hardware PE for UCLA Baja SAE during the years of 2023-2024.

Baja is a student-led off-roading competition where students design, build, and race an off-roading car throughout the school year. Baja cars are tested on their rock crawl, hill climb, acceleration, endurance, and more!

It's the job of the controls hardware PE to design the electrical framework for the ECVT (*Electronic Continuously Variable Transmission*) and to provide the infrastructure to collect data to inform future design decisions.

I'm building this guide as an open source knowledge transfer document, with the intention of sharing what I've learned over the year in [[Projects/M23 Controls Hardware/PCB Design/Index|PCB design]], [[Projects/M23 Controls Hardware/Harnessing/Index|harnessing]], [[Projects/M23 Controls Hardware/Sensors and ICs/Index|sensor selection and processing]], [[M23 Controls|control theory]], and [[Projects/M23 Controls Hardware/Power and Actuation/Index|power]].

## Overview
M23's powertrain ran on a 10HP [Kohler engine](https://www.sae.org/news/press-room/2022/10/kohler-baja-sae) with a peak low-end torque output of around 18 ft-lbs. 
![[Pasted image 20240907100915.png]]
*CH440 dyno charts from Kohler*

In order to perform well, the car needs to have a highly adaptable mix of torque and RPM. RPM is useful on long, unimpeded straights, while torque is particularly useful in difficult terrain or for obstacles. The exact mix of the two can heavily depend on track conditions, which necessitates the development of a highly adaptable transmission.

To respond to this need, we've created the [[ECVT|ECVT]], an electronically controlled variation on a traditional CVT transmission. An [[ECVT|ECVT's]] main advantage over a traditional [gauged CVT](https://en.wikipedia.org/wiki/Continuously_variable_transmission) is that it can be finely adjusted and tuned with a simple code push. This adaptability means that we can quickly change tuning based on track conditions or event.

*Click [[ECVT|here]] to learn about the mechanical workings of an ECVT*


>[!NOTE]
>
*For software questions, contact [Grant Paulker](https://www.linkedin.com/in/grantpauker/). I should also be able to answer high level programming questions that don't go too far into the weeds.*
>




### Objectives and Goals
Baja is ultimately an endurance competition that tests the performance of an off-roading car over multiple different events (acceleration, suspension, etc.). Our goal on electronics is not only to control the car's transmission, but also to provide data to other subteams to inform future design decisions. 

Here's a quick summary of our design goals and improvements for M23:
1. Provide clean, robust data for the [[M23 Controls|controls system]] to have > 95% uptime.
2. Eliminate stalling issues present in M22
3. Implement proper system compartmentalization to protect critical subsystems in the event of a subsystem failure.
4. Design a simple tuning process.
5. Anticipate future modifications to the electronic system.

### Hardware Overview
![[Pasted image 20240907104916.png]]
*The electronics system diagram for M23*

The green [[Teensy 4.1]] on the left is part of the [[M23 Main PCB]]. The lavender [[Teensy 4.1]] is part of the [[M23 DAQ PCB]]. Not pictured in this diagram is the [[M23 Dashboard PCB]].

At the core of the system is the [[M23 Main PCB|main PCB]] (green). The main PCB is the brains of the car. It takes in the engine RPM, wheel speed, and pedal positions and feeds that into a [[M23 Controls|controls system]] to decide how fast and in which direction to shift the transmission.

The [[M23 DAQ PCB|DAQ PCB]] can be thought of as the secretary of the car, logging all the data points on the car for later review.
> In one endurance race last year, we logged **30 million data points**!

The red system at the bottom is our power and actuation system. A 52V [[Battery Selection|E-bike battery]] feeds power to an [[Odrive Pro|O-Drive Pro motor controller]]. The O-Drive allows us to send simple velocity or position commands to the [[Motor Selection|BLDC motor]] controlling the ECVT and also provides regenerative braking functionality.

The blue [[Can Bus|CAN BUS]] is the information highway that facilitates communication between all three of these systems.
## Contents
- Basic Operation
	- Starting and Operation
	- Maintenance
- [[Projects/M23 Controls Hardware/PCB Design/Index|PCB Design]]
	- [[PCB Design Guidelines|General Guidelines]]
	- [[M23 DAQ PCB|DAQ PCB]]
	- [[M23 Main PCB|Main PCB]]
	- [[M23 Dashboard PCB|Dashboard PCB]]
- [[Projects/M23 Controls Hardware/Harnessing/Index|Harnessing]]
	- [[M23 Harnessing|M23 Harness Design]]
	- [[Connectors|Connectors]]
	- [[Harnessing Guidelines|Harnessing Guidelines]]
- [[Projects/M23 Controls Hardware/Sensors and ICs/Index|Sensors and ICs]]
	- [[Baja Kill Switches]]
	- [[Brake Lights and Brake Sensor]]
	- [[Gear Tooth Sensors|Gear Tooth Sensors]]
	- [[Throttle and Brake Potentiometers|Throttle and Brake Potentiometers]]
	- [[Thermistors|Thermistors]]
	- [[Strain Gauges|Strain Gauges]]
	- [[Shock Travel|Shock Travel]]
	- [[LoRa Radio|LoRa Radio]]
- [[Projects/M23 Controls Hardware/Power and Actuation/Index|Power System]]
	- [[Actuator|Actuator and Actuation]]
		- [[Motor Selection|BLDC Motors]]
		- [[Odrive Pro|O-Drive Pro]]
	- [[Battery Selection|Battery and Power Distribution]]
- [[M23 Controls|Control Theory]]
- [[Projects/M23 Controls Hardware/Instrumentation/Index|Instrumentation]]
	- Oscilloscopes
	- Function Generators
	- AD2
	- Spectrum Analyzers
	- Test Benching
- [[M23 Known Issues and Troubleshooting|Known Issues and Troubleshooting]]
- [[M23 Improvements|Further Improvements]]


## Acknowledgements
I'd like to thank the following people, who were instrumental in providing me guidance and support through the whole process of designing M23's electronics system:
- Arnav Doshi
- Drew Gautier
- Prasanna Srinivas
- Getty George
- Grant Paulker
- Paige Larson
- Beni Korol

I couldn't have made any of this happen without the people above.
***
Contact Rama: 
adi.k394@yahoo.com
