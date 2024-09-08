Shock travel sensors are a critical data collection system for the suspension team. Unsurprisingly, they measure how much the suspension travels.

There are many ways to implement a shock travel sensor. We've done it with TOF (time-of-flight) sensors, and with potentiometers.

Data from shock travel sensors can be used to optimize suspension geometry and to tune the suspension setup.

## TOF Methods
The easiest way to hack together a TOF-based shock travel sensor is to gather the following materials:
1. An Arduino
2. An ultrasonic sensor
3. A 3D printer or some cardboard

Armed with these materials, you can mount the ultrasonic sensor on one end of the shock and a reading plate at the other end. The ultrasonic sensor can then measure the distance to the reading plate, giving shock travel.

I've written a [4BL paper on a comparison between ultrasonic and laser methods](https://docs.google.com/document/d/1OIjiiK7AUqGqBI6UchtZ_aWR6hoKhZI70DKhfLM6vW0/edit?usp=sharing) for shock travel data collection.

## Linear Potentiometers

I highly recommend switching to linear potentiometers for the next year. Potentiometers yield data that can be sampled much faster, and is ultimately much more accurate.

Linear potentiometers are the industry standard, but are expensive. You should be able to easily rig up a mounting solution to connect them to the top and bottom of the shock or any other suspension component. 

>[!NOTE]
If you connect to another point on the suspension geometry, you'll have to do some math or experimentation to correlate it to shock travel

