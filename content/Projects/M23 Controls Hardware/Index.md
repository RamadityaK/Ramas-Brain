---
title: M23 Controls Hardware
---

Hi! My name is [Rama](https://www.linkedin.com/in/ramaditya-kotha/), and I was the controls hardware PE for UCLA Baja SAE during the years of 2023-2024.

It's the job of the controls hardware PE to design the electrical framework for the ECVT (*Electronic Continuously Variable Transmission*) and provide the infrastructure so that the car's ECVT can be programmed to always provide the optimal mix of RPM and torque.

I'm building this guide as an open source knowledge transfer document, with the intention of sharing what I've learned over the year in [[M23 PCB Design|PCB design]], [[M23 Harnessing|harnessing]], [[M23 Sensors and ICs|sensor selection and processing]], [[M23 Controls|control theory]], [[M23 Power System|power]], and [[M23 Improvements|potential future improvements]].

## System Overview
M23 ran on a 10HP [Kohler engine](https://www.sae.org/news/press-room/2022/10/kohler-baja-sae) with a peak low-end torque output of around 18 ft-lbs. 
![[Pasted image 20240907100915.png]]
In order to perform well, the car needs to have a highly adaptable mix of torque and RPM. RPM is useful on long, unimpeded straights, while torque is particularly useful in difficult terrain or for obstacles. This necessitates the development of a highly adaptable transmission.

An ECVT's main advantage over a traditional [gauged CVT](https://en.wikipedia.org/wiki/Continuously_variable_transmission) is that it can be finely adjusted and tuned with a simple code push. This adaptability means that we can quickly change tuning based on track conditions or event. The big disadvantage of an ECVT is complexity and weight.

For software questions, contact [Grant Paulker](https://www.linkedin.com/in/grantpauker/). I should also be able to answer high level programming questions that don't go too far into the weeds.

## Objectives and Goals
Baja is ultimately an endurance competition that tests the performance of an off-roading car over multiple different metrics (acceleration, suspension, etc.). Our goal on electronics is not only to control the car, but also to provide data to other subteams to inform future design decisions. Here's a quick summary of our design goals for M23:
- Provide clean, robust data for the controls system to have > 95% uptime.
- Eliminate stalling issues
- Implement proper system compartmentalization to protect critical subsystems in the event of a subsystem failure.
- Facilitate a simple tuning process.
- Anticipate last-minute modifications to the electronic system.

From a high level, these goals seem simple and few in number. Through this guide I hope to pass down the nuances that make designing the Baja electrical system difficult and the rationale for the decisions that we’ve made along the way.

## Hardware Block Diagram
![[Pasted image 20240907104916.png]]
> *The electronics system diagram for M23*

The green [[Teensy 4.1]] on the left is part of the [[M23 Main PCB]]. The lavender [[Teensy 4.1]] is part of the [[M23 DAQ PCB]]. Not pictured in this diagram is the [[M23 Dashboard PCB]].

The [[M23 Main PCB|main PCB]] is the brains of the car, commanding the transmission how fast and which direction to shift.

The [[M23 DAQ PCB|DAQ PCB]] can be thought of as the secretary of the car, logging all the data points on the car for later review.
> In one endurance race last year, we logged **30 million data points**!

The red system at the bottom is our power and actuation system. It consists of an [[Odrive Pro|O-Drive Pro motor controller]], a [[M23 Motor Selection|1500 watt motor]], and an [[M23 Battery Selection|E-bike battery]].

Finally, the [[Can Bus|CAN BUS]] is the information highway that transports information between all three of these systems.
## Contents
- [[M23 PCB Design|PCB Design]]
	- [[PCB Design Guidelines|General Guidelines]]
	- [[M23 DAQ PCB|DAQ PCB]]
	- [[M23 Main PCB|Main PCB]]
	- [[M23 Dashboard PCB|Dashboard PCB]]
- [[M23 Harnessing|Harnessing]]
	- [[M23 Connectors|Connectors]]
	- [[Harnessing Guidelines|Harnessing Guidelines]]
- [[M23 Sensors and ICs|Sensors and ICs]]
	- [[Baja Kill Switches]]
	- [[Brake Lights and Brake Sensor]]
	- [[M23 Gear Tooth Sensors|Gear Tooth Sensors]]
	- [[M23 Throttle and Brake Potentiometers|Throttle and Brake Potentiometers]]
	- [[M23 Thermistors|Thermistors]]
	- [[M23 Strain Gauges|Strain Gauges]]
	- [[M23 Shock Travel|Shock Travel]]
	- [[M23 LoRa Radio|LoRa Radio]]
- [[M23 Power System|Power System]]
	- [[M23 Actuator|Actuator and Actuation]]
		- [[M23 Motor Selection|BLDC Motors]]
		- [[Odrive Pro|O-Drive Pro]]
	- [[M23 Battery Selection|Battery and Power Distribution]]
- [[M23 Controls|Control Theory]]
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

[Google Docs Link to M23 Electronic Hardware Guide](https://docs.google.com/document/d/1RLCjfyGP4bGwF-32CdkQAWU11exEYwgHy4mgGt2Vypk/edit#heading=h.gebd9uls1ju6)
