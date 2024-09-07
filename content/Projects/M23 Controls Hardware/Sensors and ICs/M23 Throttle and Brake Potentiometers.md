Throttle and brake potentiometers are used to estimate the position of the throttle and brake. These data points have proven to be *very* useful in our [[M23 Controls|controls system]] to improve how well we track our reference RPM. 

If you think about it, when applying throttle, there is often a lag between the application of throttle and the engine spinning faster. Throttle information allows us to "feed forward" information into our control cycle and allow the controller to "predict" the increase in RPM, rather than reacting to it late.

A similar argument can be made for the brake potentiometer allowing one to predict sudden decreases in RPM.

The throttle and brake potentiometers were mounted to the brake and gas pedals. They used a $360\degree$ travel potentiometer, which was rigged with 5V to provide good resolution. Future versions of this sensor should use a gear reduction and be mounted directly to the throttle arm like shown below:

![[Pasted image 20240907131200.png]]
> *Image and idea courtesy of Tyler McGown*

One large drawback of mounting the potentiometers to the pedals is that the pushing of the pedals doesn't always correlate well to the end effect (throttle response or braking force). This can be due to small differences in installation and even fatigue over time.

A more reliable way to measure braking and throttle is to tie the throttle potentiometer to the throttle arm on the engine and the brake sensor to a pressure sensor in the brake line. These two things are inherently tied to braking and throttling the car. You cannot move the throttle cable without revving the engine and you cannot put pressure in the brake lines without braking the car.