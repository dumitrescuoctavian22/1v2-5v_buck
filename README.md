# USB-C ADJUSTABLE BUCK CONVERTER

## DESCRIPTION

A compact USB-C powered synchronous buck converter designed to provide a fixed 5 V rail and a selectable regulated output.

The project focuses on practical power electronics design, DC/DC converter selection, feedback network design, USB-C power input, PCB layout, high-current routing, mechanical design, and custom KiCad library development.

## FEATURES

* USB-C 5 V power input
* Up to 3 A continuous output capability
* Synchronous buck converter
* Selectable regulated output:

  * 1.2 V
  * 1.8 V
  * 2.5 V
  * 3.3 V
* Fixed 5 V output
* 3-pin output connector: 5 V / VOUT / GND
* Rotary switch for output voltage selection
* Input and output filtering
* 2-layer PCB
* 4 PCB mounting holes
* Custom rotary-switch footprint
* Custom rotary-switch 3D model
* Wide power traces
* Large ground plane
* USB-C power-only sink
* No USB Power Delivery required

## MAIN SPECIFICATIONS

Input:
USB-C 5 V

Converter:
TI TPS62933P

Topology:
Synchronous buck

Maximum output current:
3 A

Adjustable output:
1.2 V / 1.8 V / 2.5 V / 3.3 V

Fixed output:
5 V

Feedback reference:
0.8 V

Switching frequency:
500 kHz typical with RT floating

Inductor:
TDK VLS6045EX-6R8M
6.8 uH

PCB:
2-layer FR-4
1 oz copper

Output connector:
3-pin, 2.54 mm

Mounting holes:
4x
2.0 mm outer diameter
1.5 mm hole diameter

## OUTPUT CONNECTOR

The board uses a 3-pin output connector.

Pin 1:
5 V

Pin 2:
VOUT - adjustable regulated output

Pin 3:
GND

The 5 V output is connected to the USB-C VBUS rail.

The VOUT pin provides the regulated output selected using the rotary switch.

## USB-C INPUT

The USB-C connector is configured as a 5 V power-only sink.

CC1:
5.1 kOhm pull-down to GND

CC2:
5.1 kOhm pull-down to GND

D+:
Not connected

D-:
Not connected

SBU1:
Not connected

SBU2:
Not connected

USB Power Delivery is not used.

## POWER CONVERTER

The main regulator is the TI TPS62933P.

Key characteristics:

* 3 A continuous output capability
* 3.8 V to 30 V input range
* 0.8 V to 22 V output range
* Integrated MOSFETs
* Internal loop compensation
* Pulse-frequency modulation at light loads
* Spread-spectrum operation
* Overcurrent protection
* Overvoltage protection
* Undervoltage protection
* Undervoltage lockout
* Thermal protection

The RT pin is left floating, giving a typical switching frequency of 500 kHz.

## FEEDBACK NETWORK

The output voltage is selected using a rotary switch connected to the feedback resistor network.

Bottom feedback resistor:

* RFBB = 10.2 kOhm

Rotary switch positions:

Position 1:
RFBT = 5.1 kOhm
VOUT = 1.2 V

Position 2:
RFBT = 12.7 kOhm
VOUT = 1.8 V

Position 3:
RFBT = 21.5 kOhm
VOUT = 2.5 V

Position 4:
RFBT = 31.6 kOhm
VOUT = 3.3 V

The feedback resistors use 1% tolerance.

## INPUT FILTERING

The input filtering consists of:

* 47 uF bulk capacitor
* 10 uF ceramic capacitor
* 100 nF ceramic capacitor

The capacitors are placed close to the converter input to reduce input impedance and minimize the high-frequency switching loop.

## OUTPUT FILTERING

The output filtering consists of:

* 2 x 22 uF ceramic capacitors
* 1 x 100 nF ceramic capacitor
* 6.8 uH power inductor

The output capacitors are positioned close to the power stage.

## INDUCTOR

Part:
TDK VLS6045EX-6R8M

Value:
6.8 uH

Package:
6 x 6 x 4.5 mm

## ROTARY SWITCH

The rotary switch is used to select the feedback resistor and therefore the regulated output voltage.

Component:
Nidec Copal S-2050

The switch only carries the feedback-network current and does not carry the main output current.

## CUSTOM FOOTPRINT AND 3D MODEL

A custom KiCad footprint was created for the rotary switch.

A custom 3D model was also created for the component.

The custom library work included:

* Measuring the physical component
* Creating the through-hole pad layout
* Creating the PCB footprint
* Defining pad and courtyard dimensions
* Creating the 3D model
* Aligning the 3D model with the footprint
* Verifying the component in KiCad's 3D viewer

This allows the actual rotary switch to be accurately represented in both the PCB layout and 3D view.

## PCB DESIGN

The PCB is a 2-layer FR-4 design with 1 oz copper.

Important layout considerations include:

* Input capacitors placed close to VIN
* Short switching-current paths
* Short SW connection
* Inductor positioned close to the converter
* Output capacitors positioned close to the inductor
* Feedback routing kept away from the switching node
* Large ground plane
* Wide VIN and VOUT traces
* Additional copper around the power components for thermal management

## CURRENT ROUTING

The main power paths use wide copper traces.

Important high-current paths include:

* USB-C VBUS to the input capacitors
* Input capacitors to the TPS62933P
* TPS62933P to the inductor
* Inductor to the output capacitors
* Output capacitors to the VOUT connector

Approximately 1.5 mm wide traces are used for the main power paths where appropriate.

## MOUNTING

The PCB includes four mounting holes.

Mounting-hole geometry:

* Outer diameter: 2.0 mm
* Hole diameter: 1.5 mm

The mounting holes provide mechanical mounting points for PCB standoffs or suitable hardware.

## DESIGN GOALS

The main goals of the project were to demonstrate practical experience with:

* DC/DC converter selection
* Synchronous buck converter design
* Feedback network design
* USB-C power input
* Power component selection
* Inductor selection
* Capacitor selection
* Switching power supply layout
* Ground-plane design
* Custom KiCad footprint creation
* Custom 3D model creation
* Mechanical PCB design

## TOOLS

* KiCad
* Schematic capture
* PCB layout
* PCB routing
* Custom footprint creation
* Custom 3D model creation

See the repository license for terms regarding reuse of the hardware design and associated files.
