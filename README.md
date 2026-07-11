# Greenhouse-Pump

This project is an extention project to my previous project:https://github.com/Jhusky730/solar-greenhouse-monitor

I was inspired to make this as i wanted to have my sensor automatically water my greenhouse for me.

## Flow of current
### 5V
- The 5V current flows from the USB VBUS pads on the previous project to the new pcb. It is soldered onto a solder pad.
- The current flows into a 1x2 screw terminal attached to a 5V Peristaltic Pump.
- The current flows back from the pump into the screw terminal.
- There is a flyback diode to prevent feedback from turning off the pump.
- The current flows into the drain of an N-channel MOSFET.
- If the MOSFET is open the current returns through a solder pad to the other PCB to complete the circuit.
### Logic (3V3)


<img width="832" height="1069" alt="image" src="https://github.com/user-attachments/assets/e2c03782-fb55-4ea9-aacb-d84434894b81" />
<img width="773" height="1112" alt="image" src="https://github.com/user-attachments/assets/0c76eb15-540b-4c39-a14f-d10ae81621ea" />
<img width="892" height="963" alt="image" src="https://github.com/user-attachments/assets/0e73c95d-34bf-4089-ba2d-784ecd854b51" />


