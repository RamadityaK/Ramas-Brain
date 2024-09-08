Maxwell's Equations are perhaps one of the most robust equations in physics, describing all electromagnetic phenomenon. It holds completely true in anything from classical to quantum physics. 

## Maxwell's Correction to [[Ampere's Law]]
Maxwell corrected an inconsistency in Ampere's Law that prevented the laws of electromagnetism from being tied together.
	
According to [[Ampere's Law]],
$$\oint_C \vec{B} \space \cdot \vec{ds} = \mu_0I_{encl}$$
However, this does not hold true in cases where the current is changing. Maxwell decided to add an additional component to [[Ampere's law]], called the **displacement current**, which is added to the real current:
$$\oint_C \vec{B} \space \cdot \vec{ds} = \mu_0(I_{encl}+I_d)$$
where $I_d$ is defined as:
$$I_d = \mathcal{E}_0 \frac{d\Phi_E}{dt}$$
In this equation, $\mathcal{E}_0$ represents the permittivity of free space, and $\Phi_E$ is the electric flux, defined as:
$$\Phi_E = \iint_{Surface \space S} \vec{E} \space \cdot d\vec{A}$$
The **displacement current** is produced by a changing electric field or current, which produces a magnetic field. The fully modified Ampere's Law is given by:
$$\oint_C \vec{B} \space \cdot d\vec{s} = \mu_0I_{encl} + \mathcal{E}_0\mu_0 \frac{d\Phi_E}{dt}$$

## All 4 Maxwell Equations
Gauss's Law
$$\oint \vec{E} \space \cdot d\vec{A} = \frac{Q_{in}}{\mathcal{E_0}}$$
Gauss's Law for Magnetism
$$\oint \vec{B} \space \cdot d\vec{A} = 0$$
Faraday's Law
$$\oint \vec{E} \space \cdot d\vec{s} = -\frac{d\Phi_m}{dt}$$
Ampere-Maxwell Law
$$\vec{B} \space \cdot d\vec{s} = \mu_0I \space + \space \mathcal{E}_0\mu_0 \frac{d\Phi_E}{dt}$$

## Lorentz Force
Once you have calculated all of these fields, you can use the **Lorentz Force Equation**:
$$\vec{F} = q\vec{E} + q\vec{v} \times \vec{B}$$

## Differential Forms of Maxwell's Equations
Gauss' Law
$$\vec{\nabla} \cdot \vec{E} = \frac{\rho}{\epsilon_0}$$
Faraday's Law
$$\vec{\nabla} \times \vec{E} = -\frac{\partial\vec{B}}{\partial t}$$
Gauss' Law
$$\vec{\nabla}\cdot \vec{B} = 0$$
Ampere-Maxwell Law
$$\vec{\nabla} \times \vec{B} = \mu_0\vec{J} \space + \space \mu_0 \epsilon_0 \frac{\partial\vec{E}}{\partial t}$$




