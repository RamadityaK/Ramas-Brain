Finding the resonance of an [[RLC Circuits]] is often a critical part of circuit analysis. Because voltages and currents in AC circuits are often time dependent, there will be a particular frequency for which these values are maximized. 
	
For a simple RLC Circuit, the resonance frequency can be found by finding the frequency at which the **reactance** of the capacitor is equal to the **reactance** of the inductor (See [[Complex Analysis]]).
$$\omega L = \frac{1}{\omega C}$$
Solving for $\omega$, we find that $\omega$ must be equal to
$$\omega_0 = \sqrt{\frac{1}{LC}}$$
This frequency yields the highest value of voltage and current in an RLC circuit.

## Quality Factor
The quality factor is a unitless quantity that describes the quality of the peak resonance. The sharper the peak (and lower the bandwidth), the higher the quality factor.
	
The **bandwidth** of the resonance peak is defined as the range of angular frequencies $\omega$ over which $P_{avg}$ is greater than one-half the maximum value of $P_{avg}$. 
	
Mathematically, the quality factor is defined as:
$$Q = \frac{\omega_0}{\Delta \omega}$$
where $\omega_0$ is the resonance frequency. We can rewrite Q in terms of circuit parameters as:
$$Q = \frac{\omega_0 L}{R}$$
which can be further rewritten as:
$$Q= \frac{1}{R}\sqrt{\frac{L}{C}}$$

