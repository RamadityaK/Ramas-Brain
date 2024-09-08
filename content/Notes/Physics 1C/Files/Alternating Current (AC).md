Alternating current is current that changes direction and magnitude (usually in a sinusoidal shape). Alternating current is very common in our world, and is usually the method by which power is delivered over long distances. Alternating current occurs naturally from generators and other electromagnetic forces.

	NOTE: Alternating and oscillating current are differnt things! Oscillating current simpliy changes magnitude, but alternating current ALSO SWITCHES DIRECTION!!!

A sinusoidal voltage supply can be represented by the mathematical equation:
$$v_s(t) = V_0 \cos(\omega t)$$
where $V_0$ is the amplitude of the oscillation.

## Power in AC
Power in electrical circuits is defined as 
$$P = VI$$
However, in AC circuits, the values of V and I are constantly fluctuating. For this reason, we often are concerned with the power averaged over one cycle.
$$P_{avg} = \frac{1}{T} \int^T_0 p(t) dt$$
Substituting the sinusoidal equations for $V$ and $I$, we arrive at the following solution:
$$P_{avg} = \frac{1}{2} I_0V_0 \cos \phi$$
In engineering, $\cos{\phi}$ is known as the power factor and accounts for the current and voltage being out of phase (When they are in phase, that is the maximum power). 
	
We can also define a new quantity called the RMS quantity of the voltage and the current. The RMS values are the average of the absolute values of the current and the voltage, given by:
$$I_{rms} = \sqrt{i^2_{avg}}$$ and
$$V_{rms} = \sqrt{v^2_{avg}}$$
Using these definitions, we find that 
$$I_{rms} = \frac{1}{\sqrt{2}} I_0 ,\space \space V_{rms} = \frac{1}{\sqrt{2}} V_0 $$
We can now write the average power dissipated in terms of the RMS value:
$$P_{avg} = V_{rms} (I_{rms})$$
It is useful to use the RMS values because in the real world, AC is often described by its RMS value. 