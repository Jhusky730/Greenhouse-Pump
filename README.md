# Greenhouse-Pump

This project is an extention project to my previous project:https://github.com/Jhusky730/solar-greenhouse-monitor

## Flow of current
### 5V
- The 5V current flows from the USB VBUS pads on the previous project to the new pcb. It is soldered onto a solder pad.
- The current flows into a 1x2 screw terminal attached to a 5V Peristaltic Pump.
- The current flows back from the pump into the screw terminal.
- There is a flyback diode to prevent feedback from turning off the pump.
- The current flows into the drain of an N-channel MOSFET.
- If the MOSFET is open the current returns through a solder pad to the other PCB to complete the circuit.
### Logic (3V3)


<img width="658" height="759" alt="image" src="https://github.com/user-attachments/assets/e9c54cdd-cb60-4dcb-82a0-63b83887253f" />
<img width="592" height="892" alt="image" src="https://github.com/user-attachments/assets/265163d8-d27e-4cba-8c6d-9cb2c472e060" />
<img width="612" height="866" alt="image" src="https://github.com/user-attachments/assets/10b95d2a-2093-4f3e-a8e5-337aa5a1c630" />

