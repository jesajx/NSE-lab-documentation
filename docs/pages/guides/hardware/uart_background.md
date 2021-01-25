---
title: 0xFF - Background: Demystifying Serial, UART, RS-232, and so on
parent: Hardware Hacking
grand_parent: Hacking Guides
has_children: false
nav_order: 1
---

# Background: Demystifying Serial, UART, RS-232, and so on

## UART
[Universal Asynchronous Receiver-Transmitter](https://en.wikipedia.org/wiki/Universal_asynchronous_receiver-transmitter) (UART) is a hardware component used to implement asynchronous serial communication.
Essentially it takes "data" and emits digital pulses (a.k.a. [line code](https://en.wikipedia.org/wiki/Line_code)).
Usually UART takes one byte at a time and emits the bits in
[NZR](https://en.wikipedia.org/wiki/Non-return-to-zero) format,
but there are other formats.

Examples:
* <https://en.wikipedia.org/wiki/8250_UART>

## Serial
[Serial communication](https://en.wikipedia.org/wiki/Serial_communication) is the idea of sending one bit at a time over an interface.
This is usually done over a single wire but there are more complex ways (e.g. USB where there are is a "twisted pair" of wires).
This is a opposed to [parallel communication](https://en.wikipedia.org/wiki/Parallel_communication) where multiple bits are sent at once (which requires multiple wires).

UART is asynchronous in the sense that the device on the sending end and the device on the receiving end are not synchronized using for example a shared clock.

Often the term "UART" and "serial" will be used interchangeably to refer to the full setup (hardware, cable, protocol, communication, etc.).

There are multiple protocols that fall in the category of serial communication and many are typically implemented some form of UART-component.
See for example [here](https://en.wikipedia.org/wiki/Serial_port).


### TTL serial
The term "TTL serial" has to do with [voltage levels](https://en.wikipedia.org/wiki/Logic_level#TTL)
and [Transistor-Transistor Logic](https://en.wikipedia.org/wiki/Transistor%E2%80%93transistor_logic).
The idea is that transistor-level logic gates can be said to communicate by raising and lowering the voltage level of a wire.
Typically there will be a "logic high" voltage level (e.g. 3.3V) and a "logic low" voltage level (e.g. 0V).
Obscure protocols may use more than two voltage levels.

In the same way information can also be sent one bit at a time across a wire between two devices, as
long as both ends agree on the timing and interpretation of the signal.
In a sense all digital communication protocols are "TTL" on some level.


### RS-232
[RS-232](https://en.wikipedia.org/wiki/RS-232) (a.k.a. EIA/TIA-232) is an old TTL-style serial communication
standard that has since been readapted for various purposes.

RS-232 is typically associated with the [DB-25](https://en.wikipedia.org/wiki/DB-25) connector.
This connector is common on older PCs, but have mostly been replaced by USB on modern PCs.

<!-- TODO photo of D-25 -->

The actual standard uses + x V for logic low and -x V for logic high, such that: 3 <= x <= 13.
Many modern IoT devices found "in the wild" will however communicate in ways that do not fully comply with the RS-232 standard.
IoT devices may for example use 3.3V (or 5V) for logic high and 0V for logic low.
These variants are not necessarily clearly standardizes, which is why the naming can be very
confusing ("serial", "TTL", "RS-232", "UART" and various other names are used).

There might be UART-components used in the circuit that implements RS-232, but
additional components and wiring are typically needed to convert the voltage to/from a UART-component.

RS-232 specifies a lot of pins, but most of them are optional. A minimal set of
pins (for communication between devices "A" and "B") is:

  Pin | Function
  -----|--------
  Transmit (TxD) | Transmits data from A to B
  Ground  (GND) | Ground

Or more commonly:

  Pin | Function
  -----|--------
  Transmit (TxD) | Transmits data from A to B
  Receive  (RxD) | Transmits data from B to A
  Ground  (GND) | Ground


Note that TX on device A goes to RX on device B and vice versa.
The GND-pin is necessary as reference when comparing measuring the voltage of
the other two pins (so TxD is x volts relative to GND).

Note that the RS-232 standard or UART specify what to actually

With only the above pins the serial communication is asynchronous.
The remaining pins ([here are only some](https://en.wikipedia.org/wiki/RS-232#Data_and_control_signals)) are mainly used for various types of synchronization and "control flow".
Notably "RTS", "RTR" and "CTS" that have to do with readiness to receive data).

See also:
* <https://en.wikipedia.org/wiki/Serial_port>
* <https://www.sparkfun.com/tutorials/215>
* <https://support.honeywellaidc.com/s/article/What-are-the-differences-between-TTL-and-a-True-RS232-serial-interface>
* <https://en.wikibooks.org/wiki/Serial_Programming/RS-232_Connections>

### USB
[USB](https://en.wikipedia.org/wiki/USB) is perhaps a serial communication you are more familiar with.
We will not go into too much detail here.
However, it might be interesting to note how USB pins and wiring work to contrast it the other types described on this page.
Unlike RS-232 or UART, USB more clearly standardizes everything from hardware, to the connectors, to the protocol.

USB use [differential signalling](https://en.wikipedia.org/wiki/Differential_signaling) on a [twisted pair](https://en.wikipedia.org/wiki/Twisted_pair) of wires.
The pins of USB Type-A and Type-B look like this:

  Pin   | Function
  ------|--------
  V BUS | power from A to B
  D-    | Transmits data
  D+    | Transmits data
  GND   | Ground

The difference between the voltages of D+ and D- is used to calculate the
actual data sent. Think of it as D+ and D- together form "TxD".
The differential signalling helps reduce noise from electromagnetic interference.

The USB protocol differentiates between the "host" (for example a PC) and the
device (for example a mouse or smartphone) and works like a master-slave style
protocol.

The USB protocol is half-duplex. The host and device take turns to transmit
using D+ and D- and this is determined by the control flow in the USB protocol
(in a sort of client-server or master-servant way).

Newer versions of USB add additional twisted pairs to achieve full-duplex for
increased speed.

<!-- TODO photo of USB type A showing the 4 pins -->
<!-- TODO image of twisted pair -->

See also:
* <https://en.wikipedia.org/wiki/USB_hardware>
* <https://en.wikipedia.org/wiki/USB_(Communications)>
* <https://en.wikipedia.org/wiki/USB_3.0#PINOUTS>

### RS-422
[RS-422](https://en.wikipedia.org/wiki/RS-422) (a.k.a. EIA/TIA-422) is like RS-232, but uses
one or two twisted pairs (similarly to USB).

### RS-485
[RS-485](https://en.wikipedia.org/wiki/RS-485) (a.k.a. EIA/TIA-485) is like
RS-422, but uses three voltage levels instead of two. This is used to connect
multiple devices on the same wire --  a "bus network". RS-485 is often used to
implement Modbus.


### Modbus
[Modbus](https://en.wikipedia.org/wiki/Modbus) is a protocol (rather than a
hardware interface) and can be used with many different cables and hardware.
Modbus can for example use RS-232, RS-485 or IP to communicate.

Modbus is a master-slave style of protocol. There is a single "master" device
and one or more "slave" devices. The protocol works by the master sending
commands to the slaves and the slaves respond.

The [Modbus message format](https://en.wikipedia.org/wiki/Modbus#Frame_formats)
varies depending on the underlying technology (RS-232, IP and so on), but
typically contains an address (for the slave), a function code, arguments (for
the function) and an error-detection code.

Modbus is common in industrial systems where a Remote Terminal Interface (RTU)
acts as the master and manages Programmable Logic Controllers (PLCs) and other
industrial appliances. The RTU is "remote" in the sense that it acts like a
"local server" that in turns answers to a centralized Supervisory Control and
Data Acquisition (SCADA) system. Imagine for example that there are multiple
factories and there is a RTU in each factory that can then be controlled
remotely from the headquarters.


See also:
* <https://www.modbus.org/specs.php>
