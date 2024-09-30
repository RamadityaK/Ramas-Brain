There are many connectors that we use on the car. Each connector has it's strengths and weaknesses and it's critical to evaluate any connector choice for the environmental conditions it'll have to handle.

It's critical for serviceability and inventory size considerations to standardize a small number of connectors. Having many different connectors on the car makes it difficult to learn to repair all of them well.

> [!TIP]
> The integrity of the connectors has historically been one of the most common failure points in the electronics system. Choose your connectors wisely, with longevity in mind!

Much like wires, connectors will have current and environmental ratings that are critical to pay attention to. Too much current can overheat a connector beyond what it can dissipate, leading to premature failure. 
## DT Connectors
![[Pasted image 20240923212008.png]]

DT connectors have been a favorite of UCLA Baja for around 3 years at the time of writing this guide. They boast the following features:
- Waterproof
- Locking
- Keyed

They also come in a large variety of different configurations from 2 positions to 12 or more! We commonly use the DT line of connectors.

Be mindful of the difference between DT and DTP connectors! DT connectors are designed for smaller gauge data wires. DTP connectors are designed for larger power wires, and can carry 25 amps of current continuously.

>[! CAUTION]
>When purchasing DT connectors, pay special attention to compatibility and part numbers! The large number of DT connectors available means that it's easy to accidentally order the wrong pair of connectors.

Wires interface through DT connectors with crimps, which, when done properly, are almost as reliable a connection as a solder joint. It's imperative that you pick the right size crimp for your wire, as the wrong size of crimps can lead to premature connector failures.

## XT60 and Similar
![[Pasted image 20240923212129.png]]

XT60 Connectors are 2 pin power connectors where wires are soldered to the connector. They are NOT WATERPROOF and they are friction fit together. They are however, keyed

For this reason, I highly discourage the usage of XT60 connectors in Baja. Their main advantage is their large current carrying capability and their ease of use. These benefits are largely outweighed by them not having a locking connector and not being waterproof. 

XT60 connectors are useful for "quick and dirty" implementations like test benching, where their ease of use can streamline the testing experience and where the robustness of other connector types isn't required.

## Bullet Connectors
![[Pasted image 20240923212346.png]]

Bullet connectors are friction fit and usually crimped. They are commonly used in motors and high power applications due to their ability to support high currents. 

These connectors are often shipped with the motors we purchase, I highly recommend cutting them off and replacing them with something more robust, as their lack of waterproofing is a no go for Baja.
## Screw Terminals

Screw terminals are one of the quickest connectors to implement. They use a screw to clamp down on a wire, forming an electrical connection.

Screw terminals are often used in environments where a connection will remain stationary. Higher end screw terminals may be rated for vibration resistance, but they will never be more vibration resistant than a well done solder or crimp connector.

Because they are so quick to attach and disconnect, screw terminals are often used in prototyping to quickly attach and disconnect wires.

Screw terminals in Baja should be relegated to test benching ONLY!

### Ferrules
Ferrules can be used to improve the performance of a screw terminal. Ferrules are crimp connectors that are crimped onto the end of an exposed stranded wire that would normally go into a screw terminal. They provide the gate of the screw terminal with a more substantial thing to bite down on. They also prevent stranded wires from falling apart and shorting to adjacent screw terminals.

It's highly advised to use a ferrule on stranded wires when putting them inside screw terminals.
## Wago/Lever Connectors
Wago and lever connectors are a spin on screw terminals that are even easier to connect. Instead of using a screw, they use a lever to push down on a wire and form an electrical connection.

## Molex Nano Fit Connectors
![[Pasted image 20240923214013.png]]

Molex Nano Fit connectors are connectors that are used in the [[Odrive Pro|Odrive]]. They are a non waterproof, but keyed and locking connector that are crimped.

>[!WARNING]
>Amperage is highly dependent on crimp material and size. Please refer to this [datasheet](https://www.molex.com/content/dam/molex/molex-dot-com/products/automated/en-us/productspecificationpdf/201/201447/2014471000-PS-000.pdf?inline) to determine allowable amperage.
## Off-Brand Connectors
Off-brand connectors are ill advised. They just don't have the same reliability and stringent testing factors as branded ones.
