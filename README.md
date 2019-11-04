# 150-MHz-Telemetry-Transmitter
150 MHz Telemetry Transmitter for Wildlife Tracking

This Transmitter is an adaption of http://http://people.ece.cornell.edu/land/PROJECTS/TRANSMIT/.
It has some minor changes and is only discrete components as building all coils etc. by hand needs a lot of experienece, luck and effort to get the circuit running well, which I hardly had to experience...

This circuit allows to build an low-cost, tiny, light weight and very low power VHF-pulse-transmitter from scratch.
It's purpose is to be used in scientific tracking applications for wildlife and livestock.
This is the easiest effective transmitter circuit I know.

This circuit is operating on 150 MHz and as all radio transmitters emitting electromagnetic waves at harmonic frequencies, so be sure that you now your local rules for the used frequency spectrum! This report is only a theoretical abstract so no warranty.

This circuit is based on developments in the early 70s on radio telemetry for wildlife and still base for many transmitters nowadays.
Check also R. Kenwards book "A manual for wildlife radio tagging" for further information in this topic.

The circuit is mainly a single-stage oscillator based on the third harmoinc of a 50MHz crystal.

The pulse-width and -frequency is determined by the RC-member Rp and Cp. This transmitter can also be used for simple data modulation using ASK (Amplitude Shift Keying) with On-Off-Keying (OOK) by removing the Rp and Rc and turning on/off the oscillator by applying/removing voltage (same as Uin respectively GND) directly to resistor R1 (Node "EN").

![Circuit of Low-Power VHF-Transmitter](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/circuit.png)

Best results were found with the following values:

C1 = 100 nF<br>
L1 = 100 nH (In THT wind copper coil: 4x0.4mm, diameter 3mm)<br>
R1 = 390 kOhm<br>
C2 = 15 pF<br>
L2 = 1 µH (In THT wind copper coil: 12x0.4mm, diameter 3mm)<br>
NPN = MMBT3904 (In THT: 2N3904)<br>
XTAL = 50 MHz, 3rd harmonic determines transmitter frequency<br>

Rp = 0-1 MOhm<br>
Cp = 0-5 µF<br>
Combination of Rp and Cp determine the pulse width and Pulsing frequency.

It can be build on a small pcb or direectly soldered THT components.
As antenna you can use just copper wire with lambda/4 length wich is for 150MHz: 2m/4 = 50 cm
If this is to long divide it by 2 (25 cm).

The PCB SMD version got an additional matching capacitor Cm with value 2.2pF which was added in series to the antenna.

![Circuit used for ASK/OOK](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/smd_ook_circuit.PNG)
![Assembled Transmitter SMD version](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/smd_pic.PNG)

Some characterization results:

The supply voltage can be as low as 0,7V and the circuit consumes only 1,5 mA @ 2.5V.
A simple, small, light coin cell can be used as power supply.

Maximum datarate 250 baud with ASK/OOK modulation.

This graph shows the relative emitted power at harmonic frequencies.
![Frequency Spectrum](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/spectrum.PNG)
![Radiated Power at Harmonics](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/harmonics.PNG)

As receiver a very low cost china handheld device Baofeng UV-5R (30€) was used and a Telonics RA-14 H-antenna which is matched to 150 MHz. 

![Receiver UV-5R and RA-14](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/receiver.PNG)

With this setup a maximum distance through forest was found at even 350m!



