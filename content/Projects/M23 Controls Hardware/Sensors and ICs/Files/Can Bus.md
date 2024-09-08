CAN (Controller Area Network) Bus is a robust communication protocol designed for reliable data exchange between multiple microcontrollers without a host computer.

CAN Bus allows for multiple nodes to communicate on the same data lines without a dedicated master node. Collisions are automatically handled. CAN Bus only uses two wires **CANH** and **CANL** to communicate.

I'll do my best to give a surface level explanation, but you should refer to the [Wikipedia article on CAN bus](https://en.wikipedia.org/wiki/CAN_bus) for further information.

## Typical Implementation
In order to implement a CAN bus node, you need to have:
1. **A microcontroller equipped with a CAN controller**. This controller will handle creating a CAN message, arbitration (collision handling), and error checking. The [[Teensy 4.1]] already comes with two onboard.
2. **A CAN transceiver** that connects to the CAN controller, which converts the single-ended logic-level output signal from the CAN controller to a differential signal. It also can receive a differential signal and convert it back to a single-ended one. We've used the [SN65HVD230DR](https://www.digikey.com/en/products/detail/texas-instruments/SN65HVD230DR/404366) from Texas Instruments in the past with good success.
3. **A physical bus** connecting all the CANH and CANL nodes **in series**. Short stubs are okay.
![[Pasted image 20240907154015.png]]


## The Signal
Unlike other signals, CAN bus uses differential signals defined by recessive and dominant states. A dominant state occurs when a logic low level is applied to the transmit input pin of the CAN transceiver. A recessive state occurs when a logic high level is applied instead.
- In the recessive state, both CANH and CANL are biased to 2.5V.
- In the dominant state, the CANH line is biased to about 3.75V, while the CANL line is biased to about 1.25V. 

The exact state of the bus is determined by finding the difference between CANH and CANL. If the difference is larger than 0.9 V, it's a dominant state. If it's below 0.3 V, its a recessive state. Anything in between is undefined.

>[!CAUTION]
>Voltages and thresholds given are examples based on [this article from TI](https://www.ti.com/document-viewer/lit/html/SSZTCN3). Exact values are determined by manufacturer spec. Read the datasheet of your IC before usage.


![[Pasted image 20240907154309.png]]

An important consideration is how other devices on the bus will affect the bus itself. According to [TI](https://www.ti.com/document-viewer/lit/html/SSZTCN3):
> "The recessive state will only exist on the bus if all transceivers connected to the bus are transmitting a recessive state, because the recessive state is weakly biased, while the dominant state is strongly biased. This is analogous to a wired logical AND connection. All transceivers must be transmitting a logical high signal for the bus output to be logical high. If even one transceiver transmits a logical 0, the entire bus will follow this state and will be in the dominant state."

##

>[!TIP]
>- CANH and CANL should always be a twisted pair to reduce EMI.
>- CANH and CANL should always be differentially routed and have similar length wires.
>- Nodes should be connected in series, with stub lengths kept to a minimum. Refer to the image below for a sample system wiring diagram.

## Example Wiring
![[Pasted image 20240907154425.png]]
##


***
*Images and some content courtesy of:*
- Wikipedia
- By EE JRW - Own work, CC BY-SA 4.0, https://commons.wikimedia.org/w/index.php?curid=38256600