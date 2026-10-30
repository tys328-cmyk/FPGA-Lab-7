ECE 128 Lab 7 – 4095 Up Counter with Multi-Digit Seven-Segment Display

Project Description

This project implements a decimal up counter that counts from 0 to 4095 and displays its value on the four-digit seven-segment display of the Basys 3 board. The design combines a clock divider that produces a 1 Hz clock, a 12-bit up counter, a 12-bit binary to 16-bit BCD converter, and a driver for the multi-digit seven-segment display. The display driver uses a refresh counter and a 2:4 decoder to generate the anode signals that enable one digit at a time, a 4:1 multiplexer that selects the BCD digit for the enabled position, and a seven-segment decoder that converts the 4-bit BCD digit into the cathode signals. A top module connects all of the components together.

Simulation

1. Open the project in Vivado.
2. Add the clock divider, 12-bit counter, binary-to-BCD converter, refresh counter, 2:4 decoder, 4:1 multiplexer, seven-segment decoder, and top module as design sources.
3. Add the top module testbench as a simulation source.
4. Set the testbench as the simulation top module.
5. Run Behavioral Simulation.
6. Verify from the waveform that the counter increments by one on each count clock and wraps from 4095 back to 0, that the BCD output shows the correct decimal digits for each count, and that the anode signals rotate through the four digit positions with one digit enabled at a time.

FPGA Implementation

1. Select the Basys 3 as the target FPGA board.
2. Select the top module as the top module for implementation.
3. Add the Basys 3 constraints file and assign the 100 MHz board clock, the four anode signals, and the seven cathode signals to their pins.
4. Run Synthesis.
5. Run Implementation.
6. Generate the Bitstream.
7. Connect and power the Basys 3.
8. Open Hardware Manager and program the FPGA with the generated bitstream.
9. Verify that the four-digit display counts up in decimal once per second, with all four digits appearing lit, and wraps from 4095 back to 0.
