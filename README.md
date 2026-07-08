# Greenhouse-Pump

## Smart Irrigation Extension Node

An extension to my previous project [solar-greenhouse-monitor](https://github.com/Jhusky730/solar-greenhouse-monitor). This project adds an ultra-compact 19mm × 29mm low-side switching daughterboard containing a MOSFET used to control a 5V peristaltic pump, enabling automated watering cycles for my 2ft × 7ft greenhouse bed.

## Project Info

This module acts as the physical execution arm for the greenhouse system. By leveraging the existing environmental telemetry data, it can automatically:

- Drive a high-pressure 5V self-priming pump
- Move water across a fixed 1.5-metre distance and 20cm elevation climb
- Deliver a steady drip-irrigation stream to the soil bed via a split-grid loop

This removes the need for manual watering, stabilizes soil moisture levels in extreme heat (up to 50°C), and works alongside the telemetry data to ensure optimal plant care.

## Implementation, Topology, and Assembly Reference

This project requires extra wires to be soldered onto the main solar greenhouse monitor, routing the raw 5V power, system ground, and a control GPIO channel over to the expansion board via dedicated solder pads.

The custom PCB routes the power rails and control logic using these net configurations:

- **Logic Control Input**: Connected via wire pad **J1** to an available ESP32-C3 GPIO pin (e.g., GPIO2 or GPIO3).
- **Gate Signal In-Line**: Runs from **J1** through a 5.1k Ohm current-limiting resistor (**R1**) to **Pin 1 (Gate)** of the MOSFET to shield the microcontroller.
- **Boot Safety Pull-Down**: **Pin 1 (Gate)** is tied to Ground via a 10k Ohm resistor (**R2**) to strictly clamp the gate on GND during boot-up or resets, preventing accidental pump activation.
- **Power Switching Node**: **Pin 2 (Drain)** of the MOSFET ties directly to the negative lead of the pump output terminal (**J2**). 
- **System Ground Plane**: **Pin 3 (Source)** connects straight to the main common ground.

The 5V rail enters the pump loop through a robust Cixi Kefa KF128-5.08-2P-AA screw terminal block (**J2**), passes through the motor coils, and exits into the MOSFET drain. A surface-mount SS14 Schottky diode (**D1**) bridges the screw terminal connections in parallel to act as a flyback suppressor, safely absorbing high-voltage inductive spikes from the motor upon shutdown.

Verify the expansion board assembly matches this functional checklist before power activation using a manual-ranging digital multimeter:

1. **Short-Circuit Audit**: Measuring continuity across the incoming 5V tap wire and system Ground must read as an Open Loop (`OL`). Any beep indicates a bridge.
2. **Flyback Directional Flow (D1)**: In Diode Test mode, placing the Red probe on **Pin 2 (Drain)** and the Black probe on the **5V wire** must show a forward drop of **`0.200V to 0.400V`**. Reversing the probes must show an open circuit (`OL`). 
3. **Gate Resistor Integrity**: Measuring resistance between **J1** and Ground must read exactly **`10.00 kΩ`**, verifying that the pull-down resistor path is unbroken.


<img width="658" height="759" alt="image" src="https://github.com/user-attachments/assets/e9c54cdd-cb60-4dcb-82a0-63b83887253f" />
<img width="592" height="892" alt="image" src="https://github.com/user-attachments/assets/265163d8-d27e-4cba-8c6d-9cb2c472e060" />
<img width="612" height="866" alt="image" src="https://github.com/user-attachments/assets/10b95d2a-2093-4f3e-a8e5-337aa5a1c630" />

