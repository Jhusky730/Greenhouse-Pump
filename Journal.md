## 8th July 2026

I have designed my pump manager PCB today

This project requires extra wires to be soldered onto my solar greenhouse monitor, so that 5V, GND and a GPI0 pin can be connected to this project via solder pads.

The 5V rail enters the pump through a screw terminal, and leaves through the other wire. There is a shottky diode to prevent flyback from the motor upon shutdown. The wire enters the MOSFET which is controlled by a GPI0 pin with a pull down resistor to keep the gate on GND.

<img width="722" height="1079" alt="image" src="https://github.com/user-attachments/assets/28e8a3e7-b90b-46e0-9976-aa6c924440cf" />

## 11th July 2026

I have edited my PCB to use a different MOSFET which can use the 3V3 input from the GPI0 pin

<img width="938" height="1174" alt="image" src="https://github.com/user-attachments/assets/669a7c86-c68c-4426-b706-59c7387c2b1a" />
