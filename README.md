Smoke Detector Interlock
========================

The following schematics are provided as a reference for designing a
circuit interlock which opens in the event of fire.

Please read the LICENSE file before consuming any data here.

**It is strongly recommended that any design be tested before every use**

Schematic files were drawn in the Eagle Layout Editor from cadsoft.de

Example output stage
--------------------

This schematic contains the output stage reverse-engineered from a commodity ionizing
smoke detector purchased from a local home center.  It is provided solely as a reference
to give the reader an idea of how the link circuit on consumer smoke detectors operate.

As the output capacity of these devices is unknown, it is recommended that they only be used
to drive low current loads, such as transistor gates or opto-isolators.

Example Latching Interlock
--------------------------

This schematic diagrams a simple latching interlock circuit for 12V loads.
Q1, a P-channel FET is the current carrying device for the load.
When energized resistor R1 holds Q1 in an off state.
The circuit must be enabled by pressing S1, at which point resistor R5 turns Q1 on energizing the output.
S1 should obviously be a momentary pushbutton, not an on/off switch.
Current flows through Q1 and R4 enabling T1.
When T1 is on, R2 and T1 will hold Q1 in an on state.

In the event of fire the smoke detector will apply +9V between its LOAD and NEUTRAL terminals.
Current, limited by R6, will flow from the smoke detector and energize the LED in OK1.
When OK1 is energized it will allow current to flow from +12, through R3, turning off Q1.
This will de-energize the output, turning off T1.
When the smoke alarm output de-energizes the circuit returns to its initial state, with Q1 held off by R1.

OK1 is a opto-coupler rated for 5KV.  This is important as smoke detectors are not double-insulated.
Also note that the sizing of R6 takes into account the resistor internal to the example smoke detector for a load of 14mA.

A similar circuit could be built for AC interlocks using triacs and opto-triacs, and example circuit has
not been prototyped at this time.