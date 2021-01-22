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


## Voltmeter tests on powered device.
* TODO about what to do with circuits where there is a mixed DC and AC.
    * TODO for example only power DC-part using power supply.
    * TODO or just be very, very careful.
* If your device is DC-only (e.g. if it is USB-powered):
    * Make sure the probes are in the correct jacks on the voltmeter (black to
      com and red to voltage/resistance/ohm).
    * Set your voltmeter to the highest voltage (V) setting.
    * Secure the device so that it does not move around.
    * Power on the device.
    * Carefully put each probe to two different spots on the board.
        * If you know where ground is it useful to put the COM (black) probe there.
    * Gradually reduce the voltage setting until you get output that makes sense.
    * If you know the voltage rating you can go there right away.
    * If you swap the location of the black and red probes on the circuit the
      voltage will switch sign (plus to minus and vice versa).
* If your device has a high voltage part or AC:
    * Be very, very careful.
    * Have a easy way to unplug the device (like a switch, but don't rely too
      much on it).
    * Consider if you can detach the DC-part of the board and analyze only
      that. You may need a (DC) powersupply to power it and for that you need
      to identify how the circuit receives power.

* TODO link to resources

## About Soldering
* TODO put this on another page?

* TODO link to videos (embed videos here?)
* TODO link to resources
