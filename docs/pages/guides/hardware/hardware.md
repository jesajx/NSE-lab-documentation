---
title: Hardware Hacking
parent: Hacking Guides
has_children: true
nav_order: 1
---

# Hardware Hacking


## Initial unpowered voltmeter tests.
* TODO put this on another page?
* If the circuit board you are analyzing lacks useful labels you may need to
  use a voltmeter (and possibly a logic analyzer or ocilloscope) to identify pins.
* Start with the target device unpowered.
* Use the coninuity setting on the multimeter/voltmeter. The continuity
  setting usually looks like the WiFi symbol.
* The black cable should go to "COM" (usually black) on the multimeter and the red cable to
  the ohm/V port. There are usually two red jacks where one is for measuring e.g. voltage and the other for current. For continuity use the one for voltage.
* If you touch the two probes together, the voltmeter should audibly beep.
* I you touch the probes to each end of a wire, the voltmeter should beep.
* If you pinch one probe in each hand, the voltmeter should NOT beep.
* I you touch the probes to two unconnected wires, the voltmeter should NOT beep.
* I you touch the probes to two ends of a components (like a resistor), the voltmeter should NOT beep.
* Intuitively, the continuity checks if there is resistance between the two probes. If the voltmeter beeps the wires are "the same".
* TODO include photo of multimeter.
* The continuity setting is useful for:
    * tracing e.g. ground and VCC across a different parts of the board. If there are two ground pins, the voltmeter should beep if you prod each end.
    * identifying wires at both ends of a cable (a cable is a bundle of wires).
    * check for mistakes in soldering.
    * identifying where the wire to your headset is broken.
* If you have trouble finding ground, look for antenna jacks and chassis.


* TODO about what to do with circuits where there is a mixed DC and AC.
    * TODO for example only power DC-part using power supply.
    * TODO or just be very, very careful.

## About Soldering
* TODO put this on another page?
