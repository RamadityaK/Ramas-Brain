The brains of our PCB is a [Teensy 4.1](https://www.pjrc.com/store/teensy41.html). The Teensy runs on an NXP ARM-Cortex M7 chip at 600Mhz. This is much faster than the measly Arduino’s 16 Mhz ATMega chip. It has a lot of peripherals and I/O, and is super fast at floating point computations. The 4.1 also has 32 general purpose DMA channels. I will not cover DMA, but it is hugely useful in applications where you want to sample a data line very fast.

- We program the Teensy with [Platform I/O](https://platformio.org/). Nobody should be using Arduino IDE 😭. 

- The Teensy is a 3.3V Device. DO NOT GIVE AN INPUT 5V, IT WILL DIE. You must use [[M23 Sensors and ICs#Level Shifting|level shifters]] or voltage dividers for 5V signals.

- **NEVER** plug in a laptop and a power supply to a Teensy, you will fry your USB port. It's highly advisable to isolate USB power from the 5V input port by cutting the pad on the bottom of the teensy to separate VUSB and Vin. 

- The 3.3V pin can only supply a maximum of 250mA. Don’t exceed 200mA to be safe!

The full feature list and datasheet for the Teensy can be found [here](https://www.pjrc.com/store/teensy41.html).

