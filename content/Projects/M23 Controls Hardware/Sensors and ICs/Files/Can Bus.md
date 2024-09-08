CAN (Controller Area Network) Bus is a robust communication protocol designed for reliable data exchange between multiple microcontrollers without a host computer.

CAN Bus allows for multiple nodes to communicate on the same data lines without a dedicated master node. Collisions are automatically handled. Furthermore, CAN Bus only uses two wires **CANH** and **CANL** to communicate.

I'll do my best to give a surface level explanation, but you should refer to the [Wikipedia article on CAN bus](https://en.wikipedia.org/wiki/CAN_bus) for further information.

## Implementation
In order to implement a CAN bus node, you need to have:
1. A microcontroller equipped with a CAN controller. This controller will handle creating a CAN message, arbitration (collision handling), and error checking. The [[Teensy 4.1]] already comes with two onboard.
2. A CAN transceiver that connects to the CAN controller, which converts the data stream from the CAN controller to CAN bus levels (more on this later). We've used the [SN65HVD230DR](https://www.digikey.com/en/products/detail/texas-instruments/SN65HVD230DR/404366) from Texas Instruments in the past with good success.
3. A physical bus connecting all the CANH and CANL nodes **in series**.
![[Pasted image 20240907154015.png]]


## The Signal
CAN bus communication is special because it splits two signals to communicate 1s and 0s. Take a look at the picture below for a better understanding:
![[Pasted image 20240907154309.png]]

##

>[!TIP]
>- CANH and CANL should always be a twisted pair to reduce EMI.
>- CANH and CANL should always be differentially routed and have similar length wires.
>- Nodes should be connected in series, with stub lengths kept to a minimum. Refer to the image below for a sample system wiring diagram.

![[Pasted image 20240907154425.png]]



***
*Images and some content courtesy of:*
- Wikipedia
- By EE JRW - Own work, CC BY-SA 4.0, https://commons.wikimedia.org/w/index.php?curid=38256600