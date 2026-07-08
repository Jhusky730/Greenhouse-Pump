# Greenhouse-Pump

An extention to my previous project https://github.com/Jhusky730/solar-greenhouse-monitor

This project contains a MOSFET used to control a 5V pump, which can water my greenhouse bed.

# Wiring

This project requires extra wires to be soldered onto my solar greenhouse monitor, so that 5V, GND and a GPI0 pin can be connected to this project via solder pads.

The 5V rail enters the pump through a screw terminal, and leaves through the other wire. There is a shottky diode to prevent flyback from the motor upon shutdown. The wire enters the MOSFET which is controlled by a GPI0 pin with a pull down resistor to keep the gate on GND.

<img width="658" height="759" alt="image" src="https://github.com/user-attachments/assets/e9c54cdd-cb60-4dcb-82a0-63b83887253f" />
<img width="592" height="892" alt="image" src="https://github.com/user-attachments/assets/265163d8-d27e-4cba-8c6d-9cb2c472e060" />
<img width="612" height="866" alt="image" src="https://github.com/user-attachments/assets/10b95d2a-2093-4f3e-a8e5-337aa5a1c630" />

