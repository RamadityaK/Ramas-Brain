A strain gauge is a device that's used to measure strain (deformation) in an object. We can then use the strain and the properties of the material to calculate the forces that an object experiences.

Strain gauges have always been a pain point in Baja, but are insanely useful for validating FEA load cases. Properly implementing strain gauges is one of the best avenues to mechanically improve the car.

## Construction
A strain gauge is made from a thin metal foil arranged in a grid. This is attached to a flexible backing, which is then glued securely to the object in question.

## Working Principle
When the object is deformed, the strain gauge will stretch with the object, changing the resistance. 


### Deformation
In tension, the strain gauge becomes longer and thinner. In compression, it becomes shorter and thicker. Thus, the resistance of the strain gauge changes according to the following formula:
$$R = \frac{\rho L}{A}$$
*where R is resistance in ohms, $\rho$ is resistivity, and A is cross sectional area of the conductor*

### Signal Measurement
As you can imagine, the change in resistance is often very small. Thus, we'll need to use circuitry that can amplify small changes in resistance. 

For this reason, we often use strain gauges in tandem with [Wheatstone bridges](https://en.wikipedia.org/wiki/Wheatstone_bridge).
![[Pasted image 20240907144340.png]]\
We then (*optionally*) pass the Wheatstone bridge's output through a LNA (low noise amplifier) in order to get voltages that a microcontroller can read.

We can relate the change in resistance to strain with the gauge factor:
$$G_F = \frac{\Delta R / R}{\epsilon}$$
*where $R$ is the resistance, $G_F$ is the gauge factor, and $\epsilon$ is the strain*.

##

>[!TIP]
>I recommend going with an off-the-shelf solution for strain gauges. You could make your own, but it's not worth the time when there are many other pressing improvements to take care of first.
