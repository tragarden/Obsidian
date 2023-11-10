# Computer Power 3.5

### WARNING

***ALWAYS DISCONNECT FROM A POWER SOUCE WHEN WORKING ON ELECTRONICS.  EVERY TIME. NO EXCEPTIONS. GOD DAMMIT JUST UNPLUG THE FUCKIN THING***. 

Some capacitors can retain a charge for a long time, so keep in mind that you **may need to discharge the capacitors before you can work on the device**.  

**DO NOT CONNECT YOURSELF TO THE GROUND WIRE IDK WHY YOU WOULD EVER DO THAT BUT DO NOT**

### Power Supply

Your computer uses a DC voltage to #power the system, but the voltage coming from your house is AC.  The role of **the Power Supply is as a #converter, converting 120V AC or 240V AC to 3.3V DC, 5V DC, and 12V DC**.  If there are problems with your power supply, you will not be able to turn on your computer. 

1. #Ampere (amp or A) **represents the electron flow at any given point for the duration of one second**.  The ***diameter of the vessel has major influence*** over amps.

2. #Voltage (volt or V) is the amount of **metaphorical pressure created by the electrical power source**. More voltage ‘pushes’ electrons with more force in a certain direction. 

3. #Watt (W) is a measurement that **denotes the combined powers of Volts and Amps**.  You simply **multiply the volts by the amps**, and you will get the wattage. 

#### Voltages

*Power Supplies* can **distribute multiple voltages at once**, 3.3V, 5V, and 12V.  Positive and negative voltages are determined by using the electrical ground as a neutral reference point which we measure from.

**+12V is used by your #PCIe slots, hard drives, fans**, and many modern components.

**+5V** may power some components on older motherboards, but most of these have been **replaced by more modern 3.3V** components.

**+5VSB is a reference to standby voltage**, which is an electrical signal used to **determine when you have pressed your power button**. 

**+3.3V** is used by your **M.2 slots, #RAM, and logical circuits** on the motherboard.

**-12V** is used by your **integrated #LAN technology, legacy serial ports, and legacy #PCI** slots.

**-5V** is used by #ISA adapter cards, which are an ***outdated technology*** that most modern motherboards do not accommodate.

If you look at the input and output information for your power supply, you will find that they accommodate a wide range of amps, input voltage, and output voltage. 

#### Motherboard Pins

**24-pin motherboard power supplies +3.3V, +/-5V, and +/-12V**.  The older standard used a 20-pin standard, but surprisingly the 24-pin variant works with 20-pin jacks.

#### Redundancy

When you have **two or more power supplies** in a device, this is known as **power supply #redundancy**.  Each power supply is adequate on its own, and the additional units are there to balance the load or serve as backups in case the main supply fails.  These devices are **often hot-swappable** and can be easily removed via clips without powering down the server.

#### Modular Power

**Power supply connectors typically have a fixed set of associated wiring**, which may have more or less connectors than you need.

#Modular Power Supply Connectors allow you to add and **remove cables as needed, yielding better airflow** and a device that is a perfect fit for your system. 

#### Determining Power Requirements

**Determining the size of the power supply** you need is accomplished by ***adding up all the required watts needed for the various components*** of your system.  #CPU, #storage drives, and #video cards are the **most power intensive components**.  Most graphics cards will recommend a minimum wattage for your power supply.  A rule of thumb is to get a power supply that is twice the anticipated wattage of your system.

### AC

*Alternating Current* ( #AC) is a way to **transfer electricity over great distances**.  The directional flow of electrons is reversed, and then forwarded again, many times a second.  The #frequency of these changes is indicated by Hertz ( #Hz).  

> US and Canada use 120VAC @ 60Hz.
>
> Europe uses 240VAC @ 50Hz.

### DC

*Direct Current* ( #DC) is an electrical source that only **moves in one direction**.

#Dual-voltage Input allows you to **switch manually or automatically between 120V and 230V** power sources.  The automatic units will switch for you, but the **manual units must be checked with a multimeter** to ensure that you are set to the correct voltage.  If you run the incorrect voltage through a power supply, it will create sparks and smoke, ruining the unit and causing a serious fire hazard.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/computer-power-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [334 Motherboard Connectors](334%20Motherboard%20Connectors.md)
- [431 Peripheral Cables](431%20Peripheral%20Cables.md)
- [734 CPU Features](734%20CPU%20Features.md)
- [931 Adapters and Converters](931%20Adapters%20and%20Converters.md)
- [934 Cooling](934%20Cooling.md)

#study #professormesser #comptia #Aplus #hardware #powersupply