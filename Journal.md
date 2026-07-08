#8th July 2026

I have designed my pump manager PCB today

This project requires extra wires to be soldered onto my solar greenhouse monitor, so that 5V, GND and a GPI0 pin can be connected to this project via solder pads.

The 5V rail enters the pump through a screw terminal, and leaves through the other wire. There is a shottky diode to prevent flyback from the motor upon shutdown. The wire enters the MOSFET which is controlled by a GPI0 pin with a pull down resistor to keep the gate on GND.

![Uploading image.png…]()
