# 150-MHz-Telemetry-Transmitter
150 MHz Telemetry Transmitter for Wildlife Tracking

This Transmitter is an adaption of http://http://people.ece.cornell.edu/land/PROJECTS/TRANSMIT/.

This circuit allows to build an low-cost, tiny, light weight and very low power VHF-pulse-transmitter from scratch.
It's purpose is to be used in scientific tracking applications for wildlife and livestock.
This is the easiest effective transmitter circuit I know.

This circuit is operating on 150 MHz and as all radio transmitters emitting electromagnetic waves at harmonic frequencies, so be sure that you now your local rules for the used frequency spectrum! This report is only a theoretical abstract so no warranty.

This circuit is based on developments in the early 70s on radio telemetry for wildlife and still base for many transmitters nowadays.
Check also R. Kenwards book "A manual for wildlife radio tagging" for further information in this topic.

The circuit is mainly a single-stage oscillator based on the third harmoinc of a 50MHz crystal.

The pulse-width and -frequency is determined by the RC-member Rp and Cp. This transmitter can also be used for simple data modulation using ASK (Amplitude Shift Keying) with On-Off-Keying (OOK) by removing the Rp and Rc and turning on/off the oscillator by applying/removing voltage (same as Uin respectively GND) directly to resistor R1 (Node "EN").

![alt text](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/circuit.png)

Best results were found with the following values:

C1 = 100 nF<br>
L1 = 100 nH<br>
R1 = 390 kOhm<br>
C2 = 15 pF
L2 = 1 µH
NPN = MMBT3904 (2N3904 as THT equivalent)
XTAL = 50 MHz

It can be build on a small pcb or direectly soldered THT components.
As antenna you can use just copper wire with lambda/4 length wich is for 150MHz: 2m/4 = 50 cm
If this is to long divide it by 2 (25 cm).

The PCB SMD version got an additional matching capacitor Cm with value 2.2pF which was added in series to the antenna.

![alt text](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/smd_ook_circuit.png)
![alt text](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/transmitter_pic.png)

Some characterization results:

The supply voltage can be as low as 0,7V and the circuit consumes only 1,5 mA @ 2.5V.
A simple, small, light coin cell can be used as power supply.

Maximum datarate 250 baud with ASK/OOK modulation.

As receiver a very low cost china handheld device Baofeng UV-5R (30€) was used and a Telonics RA-14 H-antenna which is matched to 150 MHz. With this setup a maximum distance through forest was found at approximately 350m.



