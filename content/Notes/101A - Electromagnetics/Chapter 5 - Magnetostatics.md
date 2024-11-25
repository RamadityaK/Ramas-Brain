Magnetostatics is the study of magnetism in steady state. This means that current isn't changing and all charges are stationary. Recall from Maxwell's Equations that the following relations for magnetism exist:
$$ \nabla \cdot \bf{B} = 0$$
$$\nabla \times \bf{H} = \bf{J}$$
where $\bf{J}$ is the current density. Recall also that the B and H field are related by the following:
$$\bf{B} = \mu_0 \bf{H}$$
>[!NOTE]
>The relationship above is only valid for linear and isotropic materials. Most materials are characterized by constant permeabilities We won't be covering other kinds of materials. Furthermore, we can also write $\mu$ as:$$\mu = \mu_0 (1 + \chi_m)$$
>

## Point Charges
For a given charge q with velocity u, in a magnetic field B, it was experimentally determined that:
$$\vec{F_m} = q\vec{u} \times \vec{B}$$
If we decompose the cross product, we can find the magnitude of the magnetic force through:
$$|F_m| = quB\sin{\theta}$$
where $\theta$ is the angle between u and B. If we put this together with the point charge force for electric fields, we arrive at the **Lorentz Force**:
$$\vec{F} = q(\vec{E} + \vec{u}\times\vec{B})$$

From this equation, we can see a few key differences between electric and magnetic fields:
1. The electric force is in the direction of the electric field, whereas the magnetic force is perpendicular to the magnetic field.
2. The magnetic force only acts on a particle in motion, unlike the electric force.
3. The magnetic force does no work, since it's force is perpendicular to the direction of motion.

### Force on a Current Carrying Wire:
Using our formula, let's figure out the force on a current carrying wire when it's placed in a magnetic field. We can model the wire as a bunch of moving charges:
$$\vec{dF_m} = dQ\vec{u_c} \times \vec{B} = -N_e e A \space dl \space (\vec{u_c} \times \vec{B})$$
Simplifying the terms and recognizing the formula for current, we arrive at the following equation:
$$d\vec{F_m} = Idl \times\vec{B}$$
After taking the integral, we can see that:
$$\vec{F_m} = Il\times \vec{B}$$

### Torque on a Current Carrying Loop
It's worthwhile to study torques that magnetic fields can exert on objects, as it becomes useful in later studies. Recall the formula for torque:
$$\vec{T} = \vec{d} \times \vec{F}$$
>[!NOTE]
>If you point your thumb of your right hand in the direction of the torque, the way your hands curl is the direction the object will try to spin.

If we take a loop of current in the x-y plane and calculate the magnetic force on the loop, you will find that a torque is exerted on the loop equal to:
$$T = NIAB \sin{\theta}$$
The quantity $NIA$ is called the **magnetic moment** $m$ of the loop. If we take the vector $\hat{n}$ to be normal to the surface of the loop, we can rewrite the above formula as:
$$\vec{T} = \vec{m} \times \vec{B}$$
This expression is valid for a loop of any shape and any orientation of B.
>[!IMPORTANT]
>To determine the direction of $\hat{n}$, we curl our right hand in the direction of the current in the loop, and our thumb's direction is the name as $\hat{n}$.

### The Biot-Savart Law

The Biot-Savart Law is analogous to Coulomb's Law for electrostatics. It gives us a way to analyze the magnetic field's effects on point charges:
$$d\vec{H} = \frac{I}{4 \pi} \frac{dl \times \hat{R}}{R^2}$$
The vector $\vec{R}$ in this formula represents the distance between $dl$ and an observation point P. $dl$ is along the direction of the current, and $\hat{R}$ points from $dl$ towards P. We can use the Biot-Savart law to derive the magnetic field resulting from a wire:
$$\vec{B} = \hat{\phi} \frac{\mu_0 I }{2 \pi r}$$
We can use this expression to derive the magnetic force between two parallel conductors:
$$\vec{F} = -\hat{y} \frac{\mu_0 I_1 I_2}{2 \pi d}$$
Each conductor exerts the same force on the other. If the currents are flowing in the same direction, they attract. If they are flowing in opposite directions, they repel.

## Maxwell's Magnetostatic Equations:
While the Biot-Savart law is certainly useful in solving for magnetic fields, Maxwell's equations are much more general and powerful. First, let's take a look at **Gauss's Law for Magnetism:**
$$\oint _C \vec{B} \cdot ds = 0$$
This equation, which we get from using the divergence rule on one of Maxwell's equations, asserts that **magnetic monopoles do not exist**. This also means that contours of magnetic fields form closed loops.

### Ampere's Law
If we examine the second equation ($\nabla \times H  = J$), and apply Stoke's theorem, we find **Ampere's Law**:
$$ \oint_C \vec{H} \cdot dl = I$$
The line integral around a closed contour is equal to the current enclosed by the Amperian surface! Ampere's Law is hugely useful for problems that exhibit symmetry, where the line integral is simply to evaluate.

### Vector Magnetic Potential
Analogous to V for electric fields, we define a similar quantity for magnetic fields, **the vector magnetic potential**:
$$B = \nabla \times \vec{A}$$
With this definition, we can define the **vector Poisson's equation**:
$$\nabla^2 \vec{A}=-\mu \vec{J} $$
This can be decomposed further into the following form:
$$\vec{A} = \frac{\mu }{4 \pi} \int_{V'} \frac{\vec{J}}{R'} dV$$
This is a third way that we can solve for the magnetic field due to a current-carrying conductor!

### The Magnetic Flux
The magnetic flux $\Phi$ is defined as follows:
$$\Phi = \int_S \vec{B} \cdot ds$$
This can be interpreted as the amount of magnetic field passing through a given area. Of course, we can use the vector magnetic potential to get a similar expression:
$$\Phi = \oint_C \vec{A} \cdot dl$$
This concept will be used further later, especially in the study of electrodynamics!

## Magnetic Boundary Conditions
Boundary conditions determine how the magnetic field behaves the edge of two media with different magnetic permeabilities ($\mu_1 \not= \mu_2$). Using *Gauss's Law for Magnetism*, we can determine that:
$$B_{1n} = B_{2n}$$
This means that the normal component of magnetic fields is continuous across two media. The tangential component is a different story. If we apply Ampere's law to the boundary, we can see that:
$$\hat{n}_2 \times (\vec{H_1} = \vec{H_2}) = \vec{J_s}$$
Typically, surface currents only exist at the surfaces of perfect conductors and superconductors. Thus, we can make the assumption that $\vec{J_s} = 0$, and consequently:
$$H_{1t} = H_{2t}$$

>[!TIP]
>If you'd like to compute the normal vector to a plane, you can simply use the standard form of a plane:
>$$Ax + By + Cz + D = 0$$
>In this form, the normal vector is simply $<A,B,C>$, which still needs to be normalized to get $\hat{n}$.


## Inductance
An inductor is the analog of a capacitor. Just how a capacitor stores energy in electric fields, an inductor stores energy in a magnetic field! If we consider a solenoid (a type of inductor where wires are wound tightly in a coil shape), we can use the Biot-Savart law to find that the magnetic field inside an inductor is:
$$\vec{B} = \hat{z} \frac{\mu n I}{2} (\sin{\theta_2} - \sin{\theta_1})$$
If we take the length of the solenoid to be much larger than the radius, we arrive at the commonly used expression:
$$\vec{B} = \frac{\hat{z}\mu N I}{l}$$
which can also be found simply through Ampere's Law. 

>[!IMPORTANT]
>One should be careful with what is meant by inductance. There are two forms of inductance that are relevant in magnetism: mutual inductance and self-inductance. Typically, if one is just asked for the inductance, the problem is referring to the self-inductance.

### Self Inductance
The self inductance ($L$) formula is defined as:
$$L = \frac{N\Phi}{I}$$
Notice that the self inductance doesn't depend on the current, or any parameter other than the geometry of the inductor!

>[!NOTE]
>Some books may define a separate intermediate quantity, called the **magnetic flux linkage** ($\Lambda$), which is defined as:
>$$\Lambda = N\Phi$$


For the solenoid above, we can calculate the self inductance as:
$$L = \mu \frac{N^2}{l}S$$

For geometries without wire windings (N), we can take $N=1$ and solve as normal!

### Mutual Inductance
Current flowing in one loop can induce a magnetic field, which can induce a current in another loop. This phenomenon is quantified and related through a new quantity, **mutual inductance**. 

The magnetic field $B_1$ generated by a current $I_1$ results in a flux $\Phi_{12}$ through loop 2 given by:
$$\Phi_{12} = \int_{S_2} \vec{B_1} \cdot ds$$
We can then calculate the mutual inductance as:
$$L_{12} = \frac{N_2}{I_1} \Phi_{12}$$
This quantity is symmetric, meaning that the mutual inductance of loop 1 on loop 2  is equal to the mutual inductance of loop 2 on loop 1 ($\Phi_{12} = \Phi_{21}$).


## Magnetic Energy
The magnetic energy in joules, building up a current $I$ in an inductor is given by:
$$W_m = \frac{1}{2} LI^2$$
Using this, we can quantify the **magnetic energy density** ($w_m$), defined as:
$$w_m = \frac{W_m}{V} = \frac{\mu H^2}{2}$$
We can easily go from the magnetic energy density to the total magnetic energy by integrating over the entire volume:
$$W_m = \frac{1}{2} \int_V \mu H^2 \space dV$$

## Chapter Summary
![[Pasted image 20241124165211.png]]
