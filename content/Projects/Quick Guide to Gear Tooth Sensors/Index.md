---
title: How to Use a Gear Tooth Sensor
---
# Using Gear tooth Sensors in an Off-Road Racecar
Measuring systems that spin very fast is a common challenge in vehicle systems. To accurately measure how quickly something is spinning without touching it like an encoder, the UCLA Baja racing team makes use of the Littelfuse 55075 series of gear-tooth sensors. In this article, we'll be exploring how gear tooth sensors use the Hall effect to function, as well a practical example of how we use them on our race car. After giving this a read, you should hopefully be able to implement your own gear tooth sensor solutions!

## Theory
Gear tooth sensors like the Littelfuse 55075 use the Hall effect to detect ferrous materials. That's a dense statement, so let's take a second to unpack it. Ferrous materials (or any material with high magnetic permeability) have a very special property: they can guide and concentrate magnetic fields. In the figure below, you can clearly see that introducing a ferrous material into the magnetic field of a typical bar magnet concentrates the field directly in front of it. This means that as ferrous materials pass by the face of the sensor, the strength of the magnetic field will become stronger and weaker. Gear tooth sensors like the 55075 series typically embed this magnet into the sensor body, but you should check your sensor's datasheet to be sure!
![[3-s2.0-B9780750679343500090-f09-06-9780750679343.jpg]]
*Source: [Edward Ramsen](https://www.sciencedirect.com/book/9780750679343/hall-effect-sensors)*

But how is this useful, and how do we detect this phenomenon? The answer lies in the Hall effect. The Hall effect takes advantage of the fact that magnetic fields push moving electric charges. Charges of different signs move in opposite directions, allowing us to detect magnetic fields as a voltage! By reading this voltage, we can quantify the strength of the magnetic field through the sensor. The finer details of how a hall effect sensor works can get hairy, so here's [a video by the organic chemistry tutor](https://www.youtube.com/watch?v=pnbRXo1q-nE) explaining how it works!
![[Pasted image 20241119220916.png]]
*Picture of the Hall Effect in Action. Charges moving due to the magnetic field create a voltage Vh that we can measure!*

## Implementation
By measuring the Hall Effect, gear tooth sensors can read when ferrous materials pass by them. Like I said, we can use this to read the speed of a spinning object (provided it is ferrous). Thankfully, because of some additional circuit magic inside the 55075 series, we don't have to worry about reading and interpreting the Hall Effect voltage. Instead, the sensor outputs a digital high signal when it detects the presence of a ferrous material, and a digital low signal otherwise.

We can easily interpret these digital signals using a microcontroller like an Arduino Uno. We'll be using the same sensors we use on the car: the [55075 by Littelfuse](https://www.digikey.com/en/products/detail/littelfuse-inc/55075-00-02-A/565509). Wire up the sensor as shown below.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfAriIgCkyi_Ac7XP6-w6Qqp-Kbw898KZroXJRee7zNA0_diPc6zsE2WmXEM1A8XxOPlnnZo6gtlZQll9bfJuZvgwxxSDmsZ6RI5syvCmEgrPgP5nYld4M13LV8Mk0WHvFuMrQ6BHm_MrD1l-F-xr_sEiaL?key=h9hB8NoE_klradCjQ-Iuew)


In this example, we'll be using the gear tooth sensor to measure the speed of the front wheels of our vehicle.
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcfTMyXv_YAHqW3ikWeXno2ZGPt6-EGI_THOO1_Xc3h_5RRaz9643O7TjwseDM8EkQq1B6__FxZNE8JzdACkYZaREcETb2HwyM9JkoobR-4DAgw9GZGv4prPkVs6CXkv7J5Txonjr80ZhZOZFtGzAMrOeuj?key=h9hB8NoE_klradCjQ-Iuew)
*Picture of how the gear tooth sensor is implemented in the demo.*

Circled in red is the gear tooth sensor. It's set up to read the slots in the steel brake disc. As the wheels (and the brake disc) spin, the sensor outputs a logic low when the slots in the disc pass by. If you don't have access to a Baja car, don't worry! You can also wave any ferrous item across the face of the sensor to test if its working! We like to use steel bolts in a pinch. If your sensor is powered with 5V, and you probe the output, you should see the following:

![](https://youtu.be/3afke70dV1o)

## Code
In the Arduino IDE, we used the following code to record the RPM (rotations per minute) values as the wheel spins:
```cpp
#define GEARTOOTH_INPUT 3 
int ticks = 0;
double teeth_per_rot = 8.0;
double gear_rpm;
uint32_t last_gear_time_us = 0;
unsigned long time;
double milPerMin = 60000;
double lastTime = 0;

void on_gear_tick() {
  ticks++;
}  

void setup() {
  Serial.begin(9600);
  pinMode(GEARTOOTH_INPUT, INPUT);
  attachInterrupt(digitalPinToInterrupt(GEARTOOTH_INPUT), on_gear_tick, CHANGE);
}

void loop() {

  if (millis() - lastTime == 500) {
    //Count number of rotations and divide by number of minutes passes (20 micros)
    double rpm = ((ticks / teeth_per_rot)/ (500)) * milPerMin;
    ticks = 0;
    Serial.print(rpm);
    Serial.print(", ");
    Serial.println(millis());
    lastTime = millis();
  }
}

```

The code isn't too complicated if you've used interrupts before. An interrupt is just a function that triggers when a digital pin changes, or is driven high/low. In our case, we detect when the gear tooth sensor's output changes (High-Low or Low-High). When that happens, we increment our variable, *ticks*. 

Each tick corresponds to the sensor passing by a slot in the brake rotor. In the main loop, we evaluate the RPM every 0.5 seconds by dividing the number of ticks by the number of slots in the brake rotor (8). This gives us rotations. We then divide that by how many minutes have elapsed to get the rotations per minute (RPM)!

We print both the calculated RPM and the time in milliseconds so that we can plot our data later!

## Results
In order to test our sensor, we drove our car around in a parking lot for a few minutes at a time. We then took the values we printed to the serial monitor and graphed it using Python. The results are shown below:
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfftuMnX8dXrbCEhuSp5IdI_zR54bN2_jirJ11-EIetVKJLg2fLGuVeRBYA7MQILRhmL0Fy1yxNpChUQ0h_kk_5bqCk_HwmUNnkXUi0JdoHBoG-xWYtKhDS_u8H0Pef8aEKiVBv8g?key=h9hB8NoE_klradCjQ-Iuew)
You can see that the output contains quite a bit of noise and a couple peaks that need to be filtered out. By passing the sensor data through a simple low pass filter, we can achieve the output below!
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc6wpRDRhosjR_xA4ighQIk8rXEiToUjgkniQVsNnsMl_PZPj5CYQZ3QUoB-wksjpTKEflJZTGVJUmjuQy3PdmtPYEl8QrOBMk4lh4U_RJ2uYB8g-j0cOsjPAZw2Ynk3SUz0Y_5rA?key=h9hB8NoE_klradCjQ-Iuew)
Using this method, the Baja team measures the speed of all 4 wheels and the engine. We then use those sensor inputs to control our automatic transmission! We'll save explaining how we do that for a different article.

By now, if you've read through the article, you should be able to understand not only how a gear tooth sensor works, but also how to implement it in practice! Happy making!