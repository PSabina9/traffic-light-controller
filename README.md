# traffic-light-controller
This project implements a sequential traffic light controller for an intersection with pedestrian crossings, specifically designed for the Basys3 FPGA development board. The system manages traffic adaptively based on vehicle presence on two streets (Street A – main street, Street B – secondary street) and ensures safe pedestrian crossings.

**Features**

Vehicle Detection: Sa for Street A, Sb for Street B. Street A is green by default until a vehicle is detected on B.

Traffic Light Logic: Street A green ≥ 60s. Street B green 50s, extendable by 10s if vehicles keep arriving and A is empty.

Pedestrian Crossings: Integrated pedestrian signals; buttons can request crossing safely.

FPGA Implementation: Finite State Machine (FSM). Inputs: Sa, Sb, pedestrian buttons. Outputs: traffic lights and pedestrian signals. Works with Basys3 using Verilog or VHDL.

**How It Works**

FSM manages green, yellow, and red states for both streets.

Minimum green times and adaptive extensions reduce traffic jams.

Pedestrian requests are handled safely without violating traffic rules.

**Hardware Connections**

Sensors: Connect Sa and Sb to Basys3 GPIO inputs.

LEDs: Connect traffic lights and pedestrian signals to Basys3 LEDs.

Clock: Use 100 MHz Basys3 clock for timing.
