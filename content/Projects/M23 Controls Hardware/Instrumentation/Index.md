---
title: Instrumentation
---
Instrumentation is a critical part of Baja electronics. Only a small portion of your time in Baja, and as an engineer in industry will be spent designing. The large majority of your time will be spent testing and iterating. 

In order to diagnose and solve problems with your designs, and make successive iterations, it's imperative that you become very familiar with testing equipment and their uses. The right tool can mean the difference between a 12 hour diagnostic session and a 12 minute one.

## Oscilloscopes
Oscilloscopes (or scope for short) are devices that can measure differential voltages over time. This means that scopes can provide critical information about how a voltage waveform evolves over time.
![[Tektronix_Oscilloscope_475A.jpg]]

Oscilloscopes have 3 main controls: the voltage scaling, the time scaling, and the trigger. To understand how all of these controls work, as well as how to use a scope, refer to [this guide by Sparkfun](https://learn.sparkfun.com/tutorials/how-to-use-an-oscilloscope/all).
## Function Generators 
![[58Y4498-40.jpg]]
Function generators allow you to generate voltage signals. In a way, they're the opposite of oscilloscopes, which read voltages.

Function generators are very good at simulating input signals from sensors, or other sources in your system. You should use the to monitor your system's behavior in a variety of simulated conditions.

Modern-day function generators are fairly straightforward to use. Here's [a quick blurb](https://www.keysight.com/used/us/en/knowledge/guides/signal-generator-buying-guide/how-to-use-a-signal-generator) about how they work.
## AD2
![[analog_discovery_2_obl_600.png]]
The [Analog Discovery 2](https://digilent.com/reference/test-and-measurement/analog-discovery-2/start), or AD2, is a key part of the Baja toolkit. It combines a oscilloscope, function generator, and logic analyzer into a small, easy to use device. While it does need to be plugged into a computer to function, and can only generate/analyze 5V signals, it's versatility and portability makes it invaluable in the remote test areas that Baja often goes to.

Due to it having many tools in one package, the AD2 is often used to simulate an input signal to a system, along with reading and validating its response.

## Test Benching
Test benching is the process of simulating real-life running conditions on a miniaturized version of your electrical system. 

A test bench gives you the comfort of having all of your electronics easily accessible, which can be invaluable in Baja. Often times it's very inconvenient or difficult to access electronics once they're on the car. 

A test bench makes it easy to diagnose issues or test new changes!

