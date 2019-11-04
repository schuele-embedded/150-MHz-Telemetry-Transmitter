# 150-MHz-Telemetry-Transmitter
Ultra Low Power VHF-Transmitter for Wildlife Tracking

This Transmitter is an adaption of http://http://people.ece.cornell.edu/land/PROJECTS/TRANSMIT/.<br>
It has some minor changes and uses only discrete components as winding all coils etc. manually needs a lot of experienece, luck and effort to get the circuit running well and robust, which I hardly had to experience...
I got two versions running stable, one manufactured in THT and one in SMD.

This circuit allows to build a low-cost, tiny, light weight and very low power VHF-pulse-transmitter from scratch.
It's purpose is to be used in scientific tracking applications for wildlife and livestock.
This is the easiest but most effective transmitter circuit which is known to me.

This circuit is operating on 150 MHz and as all radio transmitters also emitting electromagnetic waves at harmonic frequencies, so be sure that you now your local rules for the emitted frequency spectrum! This report is only a theoretical abstract so there is no legal  warranty.

This circuit is based on developments in the early 70s on radio telemetry for wildlife and still base for many transmitters nowadays.
Check also R. Kenwards book "A manual for wildlife radio tagging" if you're interested in further information and advanced knowledge in radio tagging.

The circuit is in principle a very simple single-stage oscillator based on the third harmonic of a 50MHz crystal (you can also use a different frequency crystal). Its emitting short pulses of a continuous wave signal.
The pulse width and pulsing frequency is determined by a simple RC-network. 
This transmitter can also be used for simple data modulation using ASK (Amplitude Shift Keying) with On-Off-Keying (OOK) by removing the components Rp and Rc and turning on/off the oscillator by applying/removing voltage (with levels Uin/GND) directly to resistor R1 (Node "EN").

![Circuit of Low-Power VHF-Transmitter](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/circuit.png)

Best results were found with the following values:

C1 = 100 nF<br>
L1 = 100 nH <br>
(In THT wind copper coil: 4x0.4mm, diameter 3mm)<br>
R1 = 390 kOhm<br>
C2 = 15 pF<br>
L2 = 1 µH<br>
(In THT wind copper coil: 12x0.4mm, diameter 3mm)<br>
NPN = MMBT3904 (In THT: 2N3904)<br>
XTAL = 50 MHz<br>
3rd harmonic determines transmitter frequency<br>

Rp = 0-1 MOhm<br>
Cp = 0-5 µF<br>
Combination of Rp and Cp determine the pulse width and Pulsing frequency.

This circuit can be build on a small pcb (see also eagle schematic and layout in ".../eagle/") or directly solder the THT components to each other as a "flying assembly".
As antenna you can use just a piece of copper wire with length lambda/4 which is for 150MHz: 2m/4 = 50 cm

The PCB SMD version got an additional matching capacitor Cm with value 2.2pF which was added in series to the antenna.

![Circuit used for ASK/OOK](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/smd_ook_circuit.PNG)
![Assembled Transmitter SMD version](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/smd_pic.PNG)

Some characterization results:

The supply voltage can be as low as 0.7V and the circuit consumes only 1.5 mA @ 2.5V.
A simple, small, light coin cell with 1.5V for example can be used as power supply.

Maximum datarate is 250 baud with ASK/OOK modulation.

This graph shows the relative emitted power at harmonic frequencies and the narrow signal at 150 MHz.
![Frequency Spectrum](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/spectrum.PNG)
![Radiated Power at Harmonics](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/harmonics.PNG)

As receiver a very low cost china handheld device Baofeng UV-5R (30€) was used and a Telonics RA-14 H-antenna which is matched to 150 MHz. 

![Receiver UV-5R and RA-14](https://github.com/fistlabsdev/150-MHz-Telemetry-Transmitter/blob/master/receiver.PNG)

With this setup a maximum distance through forest was found at even 350m.



