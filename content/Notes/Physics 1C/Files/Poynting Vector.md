To understand the Poynting Vector, it's important that we first take a look at some preface knowledge:
## Continuity Equation for Electric Charge
The continuity equation is equivalent to the property of the **conservation of charge** the main difference is that the continuity equation is a derivative form for describing the continuity equation.
$$\frac{\partial \rho}{\partial t} = -\vec{\nabla} \cdot \vec{J}$$
We can see that in this equation, the only way for charge in a region to change is by $\vec{J}$, the current density also changing. We can interpret this as follows:

	The only way to get a change in charge, is to have charge flowing into or out of the region you are analyzing.

## Energy Density
So far, we have encountered two forms of energy density:
1. Electric Field Density
$$\mu_E = \frac{1}{2}\epsilon_0E^2$$
1. Magnetic Field Density
 $$\mu_B = \frac{1}{2\mu_0}B^2$$
These two energy densities add upon our knowledge from mechanics to paint a new picture of energy. There are now two sources of energy: 
1. The energy from motion
2. The energy from electromagnetic forces.

The change in this energy can be described by something called the **Poynting Vector**!

## Poynting Vector
The Poynting Vector is defined by:
$$\frac{\partial}{\partial t}(\mu_{mechanical} + \mu_{EM}) = -\vec{\nabla} \cdot \vec{S}$$
Where S is given by:
$$\vec{S} = \frac{1}{\mu_0}(\vec{E} \times \vec{B})$$
We can interpret this equation in a similar fashion to the **Charge Continuity** equation above! Before we do that however, we first must note that the Poynting Vector has units of $\frac{energy}{time \cdot area}$ or $\frac{power}{area}$.
	
The Poynting Vector tells us that for the ammount of energy to change in a region, there must be energy flow into or out of the region!
	
You can use the Poynting Vector to find power with the following equation:
$$P = \iint_S \vec{S} \cdot d\vec{A}$$
### Example 1:
The expression for electrical power in a circuit: $P = VI$ is one that is extensively used in circuit analysis. While we have used other methods to find this expressions before, we can now use the Poynting Vector to derive this expression.
	
Let's suppose the resistor is a cylinder with radius $a$ and length $L$. The Poynting Vector is defined as:
$$\vec{S} = \frac{1}{\mu_0}(\vec{E} \times \vec{B})$$
First we analyze the electric field $\vec{E}$ inside of the resistor. The electric field is forcing electrons across the resistor, so we find the expression:
$$E = \frac{V}{L}$$
We now analyze the magnetic field inside the resistor. We know that there is a current flowing through the resistor, which would create a magnetic field. We find the following expression for the magnetic field due to a current in a wire (derivation found in [[Ampere's Law]]):
$$B = \frac{\mu_0 I}{2\pi a}$$
Now that we have our two pieces, we can take the cross product, giving us:
$$|\vec{S}| = \frac{1}{\mu_0}EBsin\theta$$
We can plug in and simplify this to (Note that $\vec{B}$ and $\vec{E}$ are at $90\deg$):
$$S = \frac{VI}{2\pi aL}$$
We can now use the power equation above to find the power:
$$P = \iint_S \vec{S} \cdot d\vec{A}$$
The resistor is a cylinder with area $2\pi a L$, so we get:
$$P = \frac{VI}{2\pi aL} (2\pi a L)$$
The terms cancel and we get:
$$P = VI$$
Here's a picture to illustrate the situation further:
![[Pasted image 20230829124236.png]]

## Field Momentum Density:
$$\rho_{EM} = \mu_0 \epsilon_0 \vec{S} = \frac{\vec{S}}{c^2}$$
Where $c$ is the speed of light.