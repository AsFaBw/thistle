# Distel
A neighbor for doing fault injection for the GreatFET One
# Name
The plant distel is a bit spikey, and this is what the Neighbor distel shall be able to produce - some spikes
# Purpose
Primary purpose of this neighbor is to provide a possibility to do fault injections on low power targets like smaller micros. For that the neighbor provides
* some fixed volatge regulators
* a voltage follower, following the GreatFET DAC output (variable voltage)
* a 3 channel analog multiplexer for producing spikes
* a programable oscillator, to have the ice40 PLL free for fine granular spike generation (150ps delay elements from PLL macro)
* an ice40 fpga for
  * communication to/from the GF
  * cycle accurate control
  * pattern generation/response recording
  * eventually in future revisions an ADC channel for current oberservations

THE PURPOSE OF THIS NEIGHBOR IS NOT TO BE A TOOL FOR CRIMINALS!
# Status 
A first version was layouted under hurry, production is nearly finished. Wether anything works or just produces smoke is not clear yet. At least the ordered parts seem to fit to the used footprints (based on a photograph from production). Waiting for shipment.
![Alt text](PoC/DistelV0.1.jpg?raw=true "Distel V0.1")
FPGA code under development (reset control, pattern generator and some LED stimulus implemented, plenty of stuff to do).
Bitstream transfer from GreatFET to ICE40 via SPI implemented.
![Alt text](PoC/ICE40Config.jpg?raw=true "Config stimulus")
After receiving the board, soldering of remaing stuff was done and pre-written verilog and host programm tested. Quite happy so far.
Working:
  * ICE40 FPGA configuration
  * SI514 frequency change
  * SPI read/write access to some frist implemented registers on ICE40  
  * pattern generator stream from pre-defined FPGA RAM contents
  
Not working:
  * LEDs :-) 
![Alt text](PoC/DisteFirstActivity.JPG?raw=true "First operation")

   