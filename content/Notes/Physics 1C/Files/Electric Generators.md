Electric generators take advantage of [[Inductance]] and [[Faraday's Law]] by rotating a coil in a magnetic field, inducing an emf.

## Basic Idea:

![[Pasted image 20230818112507.png]]
First we use [[Faraday's Law]]:
$$\mathcal{E} = -N\frac{d\Phi_m}{dt}$$
We can define the magnetic flux simply as:
$$\Phi_m = NBAcos\theta$$
And after differentiating, we arrive at the following result:
$$\mathcal{E} = NBAsin\theta \frac{d\theta}{dt}$$

## General Formula:
![[Pasted image 20230818113307.png]]
If we consider this rectangular loop, we can derive a formula for all loops in this kind of generator. From [[Faraday's Law]], specifically our derivations on Motional EMF, we know that
$$\mathcal{E} = Blv$$
The velocity in this case is not all perpendicular to the magnetic field. Thus, we find the perpendicular component. We also multiple by 2 for both sides of the loop. Thus:
$$\mathcal{E} = 2Blvsin\theta$$
To find the EMF as a function of time, we use $\theta =\omega t$:
$$\mathcal{E}=NBA\omega \sin(\omega t)$$
We can see that the max EMF generated is $NBA\omega$ and follows a sinusoidal shape.
	
