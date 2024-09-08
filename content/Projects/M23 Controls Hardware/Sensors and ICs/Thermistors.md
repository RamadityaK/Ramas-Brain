Thermistors are incredibly important to monitoring the health and heat dissipation of the ECVT. 3 years ago, at a comp, the ECVT overheated, causing the gearbox input shaft to fail. Since then, monitoring the heat going through the ECVT has been a prime concern.

A thermistor is just a resistor that changes its value with heat. They make thermistors that increase resistance with heat and decrease resistance with heat. 

We ended up using these something like these [Vishay thermistors](https://www.vishay.com/docs/29078/ntcle413.pdf), which are nominally $10 k\ohm$ at $25\degree C$. They decrease resistance with temperature.
![[Pasted image 20240907143704.png]]
There is a long formula to compute the temperature from the resistance of a thermistor called the [Steinhart-Hart equation](https://en.wikipedia.org/wiki/Steinhart%E2%80%93Hart_equation). You can find a [calculator](https://rusefi.com/Steinhart-Hart.html) for these equations online that will give you the coefficients given the table of temperature-resistance values from the manufacturer. 

>[!TIP]
>You'll want to pick reference values that closely bound the expected temperature range of what you want to measure, as that will improve your accuracy.

