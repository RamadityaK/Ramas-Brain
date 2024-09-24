Harnessing is a critical component of any electrical system. Many of the electrical failures encountered in Baja are caused by harness failure. Having a robust and easily serviceable harness is critical to ensuring a reliable car.

- [[M23 Harnessing|M23 Harnessing]]
- [[M23 Connectors|M23 Connectors]]
- [Nasa Workmanship Standards](https://archive.org/details/nasa-workmanship-standards/page/n31/mode/2up)

## Harnessing Diagrams
A clear plan should be the first step in creating a harness. A harnessing diagram allows one to thoroughly review their harness design and identify potential issues before manufacturing begins. 

A clear harnessing diagram can also take the guessing out of the purchasing process, by allowing one to buy the right amount of materials.

>[!TIP]
>The more you invest into your harnessing diagram, the less headaches you'll have later.

There are a few key details to include in your harnessing diagram.
1. **Signal Type:** diagrams should indicate the purpose of a wire as well as the signal type (digital, analog, DC, AC).
2. **Length:** diagrams should indicate the length of that wire run.
>[!TIP]
>It's extremely helpful to put your harness into your project's CAD. Not only will it give you the exact length of wire needed, but also insight into potential clearance issues and hazards!

3. **Connectors Used:** diagrams should specify the connector that is being used *on each end* of every wire. It's important to [[M23 Connectors|choose the right connector]] for the job.
4. **Relevant Signal Information:** diagrams should specify miscellaneous but critical information about signals (differential pair, susceptible to noise, etc.)
5. **Perceived Hazards:** diagrams should call out potential hazards a wire will encounter. Things like excessive heat, corrosive substances, and high abrasion are all good callouts.

## Wire Selection
After you have a clear picture of the design requirements for your harness, you can select the wire. There are many considerations in choosing wiring; I'll cover the main ones here.
### Ampacity
The ampacity of a wire is the maximum electrical current (in amps) that a conductor can safely carry.

At the end of the day, all conductors, no matter how good they may be, have some amount of resistance. Resistors dissipate electrical energy in the form of heat.

A conductor that exceeds its ampacity is subject to thermal issues and can cause electrical hazards, fires, and all sorts of nasty damage.

>[!TIP]
>It's best practice to always consider the worst case scenario and give yourself a little margin of error when considering the ampacity of your wires.

>[!theory]-
To understand how the ampacity of a wire is determined, we should first look at how resistance is calculated from resistivity in the following formula:
$$R = \frac{\rho l}{A}$$
where $\rho$ is resistivity, $A$ is cross-sectional area, and $l$ is length. 
>
>The power dissipated as heat from a resistor is given by:
$$P_{heat} = I^2 R$$
>
>All this heat is dissipated by conduction through the wire itself and then convection through the air around the wire.
>
The material and the size of the wire, as well as environmental conditions can greatly affect the ampacity.

The ampacity of a wire is determined by a number of factors:
1. **Conductor Material:** The resistivity of a material determines its resistance. It then follows that the ampacity of a wire is dependent on the material.
2. **Conductor Size:** The larger the cross-sectional area of a wire, the more current it can support.
3. **Insulation Type:** The type of insulation determines how easy it is for heat to dissipate
4. **Environmental Conditions:** The ambient temperature and where the wire is installed can play a key role in the ampacity.

>[!IMPORTANT]
>It's critical to consider where you're installing wires, as installing them near other wires, or in enclosed, non-ventilated spaces can lead to a much lower than anticipated ampacity.

### Environmental Hazards
A wire can encounter many environmental hazards during its lifetime. It's important to consider these hazards when purchasing wire for your harness, as unforeseen hazards can result in poor safety and reliability.
1. **Temperature Extremes:** The insulation of a wire is only rated to handle a range of temperature values. Some wires can handle high heat, while others can handle below freezing temperatures.
2. **Moisture and Water Exposure:** Wires used in outdoors or wet applications should be rated for moisture, or they'll otherwise prematurely degrade.
3. **Chemical Resistance:** Wires must be rated to resist chemicals, oils, acids, and solvents they may contact. 
> [!NOTE]
> Gasoline is a corrosive substance and wires near fuel tanks should be chosen carefully.
4. **UV and Sunlight Exposure:** Insulation exposed to direct sunlight can degrade if not rated for UV exposure.

>[!TIP]
>If you're constrained by budget, it's okay to mix multiple solutions to create a harnessing system that addresses all the environmental hazards you may encounter.
>
>For example, you may need water resistance and UV resistance. You could use UV resistant heat shrink and water resistant wire on the inside.
### Solid Vs. Stranded
Wires come in two main internal constructions: solid and stranded.

Solid core wire is made from a single, solid strand of conductive material. It's stiffer and less flexible and typically has lower resistance for DC applications. Solid core wire is easier to solder and terminate.
>[!WARNING]
>Solid core wire can attenuate higher frequency signals.
>
>Solid core wire becomes more resistive in AC applications, especially as the frequency gets higher. This is due to the [skin effect](https://en.wikipedia.org/wiki/Skin_effect), where current travels on the outside of a conductor, reducing cross-sectional area and increasing resistance.
>

Stranded core wire is much more flexible and has a slightly higher resistance (often negligible). Stranded wire is much more vibration resistant due to its flexibility, but the many strands make it much more difficult to terminate.

## Connector Selection
It's also important to select a suitable connector. Consider environmental hazards and max amperage similarly to how you did for wires. Specific details on connectors, as well as my personal recommendations can be found [[M23 Connectors|here]].
## Mechanical Considerations
Often times, electrical engineers overlook key mechanical considerations when harnessing a system. The mechanical aspects of harnessing can prove to be just as catastrophic if not taken into consideration!

### Wear and Abrasion
Wear and Abrasion are unavoidable aspects of any system. Certain environmental conditions like being outdoors or tight corners can accelerate the rate of wear, but can be counteracted with some consideration.
#### Sheathing
Sheathing is a practice in which wires are wrapped in another protective material. There are many different kinds of sheathing, but there are three main ones we encounter in Baja:
1. **Snake Skin:** Snake skin is a webbed sheathing that is slid over the top of wiring to protect it from abrasion. It's been the standard solution for Baja for a while now. There are many kinds of snake skin sheathing. You can even get them made from metal for some EMI or heat shielding.
2. **Heat Shrink:** Heat shrink offers the most amount of protection for wires. It's slid over the wires and is heated up to shrink down and conform to the wire. Some heat shrink even contains adhesive to waterproof the inside and prevent the wires from sliding around internally. This comes at the cost of heat shrink being a complete pain to remove and service.
3. **Electrical Tape:** Electrical tape is used to tape up the ends of snake skin or other types of sheathing. In a pinch, it can also be used as a temporary sheathing solution. Electrical tape isn't very durable compared to other options and can leave behind a nasty residue.
### Strain Relief
Strain relief is a method of protecting wires from mechanical stress. It helps prevent damage at connection points and helps avoid issues like breakage, disconnection, or insulation damage.

The main premise of strain relief is to take the mechanical stresses on a wire (caused by connectors, vibration, etc.) away from the connection points and spreading it over as much surface area as possible.

You can achieve proper strain relief with:
- **Zip Ties** are tied around the cable and anchored to a fixed surface to prevent movement.
- **Grommets** are rubber or plastic rings inserted into holes where cables pass through. They prevent sharp edges from cutting into the cable and reduce stress at the entry point.
- **Boots and Heat Shrink** are used at connector interfaces to redirect strain on the wire to the body of the connector.
>[!TIP]
>Boots can be very expensive, so a cheap workaround is to 3D print your own boots from a flexible filament. They won't be nearly as flexible, but they'll do the job of protecting your connectors.
- **Concentric Twisting** is a technique of wrapping wires in a spiral shape in order to improve a harness' flexibility and strain relief. Concentric twisting allows no wires within the twist to have any more strain placed on them than another, even when bent. In a straight harness, wires on the outside of the bend will be subject to more strain than those on the inside.
	![[Pasted image 20240908164723.png]]

## EMI
EMI or electromagnetic interference refers to disturbances that can affect an electrical circuit due to electromagnetic radiation from an external source.

EMI can pose significant problems to circuitry, causing it to behave in unexpected ways. Therefore, it's of utmost importance to find ways to mitigate or better yet, eliminate EMI.

### Twisted Pairs
A twisted pair is a set of two wires that are wrapped around each other in a spiral pattern.
![[Pasted image 20240913112445.png]]

Twisted pairs are very useful in mitigating EMI, as their spiral wrapped geometry can cancel out EMI from nearby cables or electronics. 

If you'd like to prove to yourself why, think about how the magnetic fields in the two wires cancel out if one wire has an induced current!

Twisted pairs are also better for cable flexibility, as both wires travel an equal amount when bent!
![[Pasted image 20240913113342.png]]

As you can see, in the picture above, the untwisted wires travel an unequal length around the curve. If both wires are constrained to have the same start and end, the black wire will stretch or deform.

On the other hand, the twisted wires travel an equal amount around the curve, so neither of them will be stretched when we constrain both ends.

Twisted pairs are also good for differential signals because any induced noise in one pair is either cancelled or mirrored by the other pair, preserving signal timing and integrity. This is also called "common mode noise". Twisted pairs also ensure equal path lengths of wire for both ends of a differential signal, which is critical. It also reduces crosstalk from the differential pair to other signal wires nearby.

There are two big cons of twisted pairs. 
1. The twist inherently **increases the length of the wires**, leading to reduced wiring range. If a signal is susceptible to degradation over long distances and you have a particularly long run, twisted pair wiring can reduce signal integrity.
2. Having wires twisted so closely together can cause **issues with heating, reducing the ampacity** of wires. Thus, it's not recommended to twist/bundle a lot of high amperage power wires together.

### Shielding
Shielding is another technique employed to reduce EMI issues in harnesses. Shielded wires consist of a metal mesh or foil wrapped around a wire. This wire is grounded at one end **ONLY** to the ground the wires inside reference.

>[!WARNING]
>Grounding a shielding cable at two ends can create a ground loop and leave your system MORE susceptible to noise!


Shielded wires can be thought of as a Faraday cage, which routes all incident EMI through the outside of the cage without letting it propagate inside.

Be very wary of your ground selection with your shielded ground. Choosing the right ground to prevent EMI is in and of itself a whole field of electrical engineering that I myself am not super familiar with. Think through the return paths of your signals and how induced currents will flow to decide a decent ground!

Usually, it's advisable to separate your shielding ground and your digital ground by grounding all shielding to the chassis!

## Serviceability
Serviceability is a factor that's often overlooked in Baja. In order to make design iterations and repairs as fast as possible, it's critical for the subcomponents to be easily serviceable. Serviceability also serves to minimize mistakes by making relevant information easy to access. Finally, serviceability allows documentation to be clean and simple, allowing future maintainers to repair the car easier.

>[!NOTE]
>What sounds more foolproof? "Snip the green wire labelled *power* to the left of the engine" or "Snip the wire to the left of the engine, underneath the cover, it's the wire that's not twisted"


You can improve serviceability with the following things:
- **Color Coding** your wires can serve as a simple way to denote broad categories of wires. Be sure to establish a club-wide convention early on in order to prevent confusion! It's also worth mentioning that you should be consistent with your wiring color and your heat shrink color!
> [!EXAMPLE]
>- Vcc - Red
>- Ground - Black
>- Data - Purple, Grey, Yellow, etc.

- **Grouping** of similar wires allows people to service chunks of a harness rather than going on a scavenger hunt finding one particular wire. In general, the tidier the wiring, the more easily you'll be able to find and service it.
- **Labelling** wire is critical to allowing **new** people to troubleshoot and even repair the car. Try walking someone not versed in electronics through repairing/troubleshooting a system that's not labelled. It's not fun. Even though you may know where things are, *not everyone else will*! Use a labelling machine to mark critical wires or details about them.
- **Service Loops** are an often overlooked part of making a harness. When repairing/modifying a harness, you often need more wire. A service loop is a loop of extra wire in the harness. Service loops can be lifesavers, and you should leave them near areas prone to modification or damage.