An RL circuit is a simple circuit with a voltage source, a resistor, and an inductor.
![[Pasted image 20230822102454.png]]
An inductor does not care if the circuit turns on or off. What it does care about it whether or not the current is changing. Changes in current cause an inductor to induce a current in the circuit. Inductors **resist changes in the current of a circuit**. 
	
Let's first consider circuit b. Using Kirchhoff's current law, we can write the following expression:
$$\mathcal{E} - L\frac{dI}{dt} - IR = 0$$
This creates a first order differential equation for $\frac{dI}{dt}$, and its solution is simply:
$$I(t) = \frac{\mathcal{E}}{R}(1-e^{-{t}/{\tau_L}})$$
where
$$\tau_L = L/R$$
$\tau_L$ is the inductive time constant of the circuit. When $t = \tau_L$, the current is 0.63 of its maximum value!
	
When in configuration c, the circuit is discharging from its maximum value. In this configuration, the circuit follows the equation:
$$I(t)=\frac{\mathcal{E}}{R}e^{-t/\tau_L}$$
When there is no electromotive force, it is important to remember that current must be exponentially decreasing. From the equation given above, you can draw conclusions about any given problem.