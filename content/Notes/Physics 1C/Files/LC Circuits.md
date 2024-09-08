The LC Circuit is a common circuit that consists of a capacitor and an inductor. This circuit exhibits an interesting oscillatory behavior and exhibits [[Alternating Current (AC)]]. 
![[Pasted image 20230822104531.png]]
In the above image, the circuit shown has a charged capacitor. When this capacitor discharges, it goes through the inductor, which resists the change. 
	
Eventually the charge travels to the other plate of the capacitor, and the inductor tries to oppose the reducing current, generating a current in the other direction, repeating the cycle again.
	
To find an equation to describe this system, we use an energy approach:
$$U = \frac{1}{2}Li^2 + \frac{1}{2} \frac{q^2}{C}$$
This bears uncanny resemblance to the mass-spring system, so we simply replace the constants with those in the mass-spring system.
$$q(t) = q_0 \cos(\omega t + \phi)$$
Where the angular frequency is $$\omega = \sqrt{\frac{1}{LC}}$$
By taking the time derivative of charge, we can find the current in the circuit:
	$$i(t)= -\omega q_0 \sin({\omega t + \phi})$$
These two sinusoidal functions work in tandem to create the graphs in the figure above.
