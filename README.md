# Low-Noise Eurorack Busboard (37cm)

An open-source, high-integrity power distribution busboard for Eurorack modular synthesizer systems. It features aggressive passive filtering designed specifically to clean up the switching and regulation ripple from standard industrial switched-mode power supplies (such as the Mean Well LRS-75-12).

## Features

- **37cm Long Layout:** Optimized for physical accessibility across 84hp cases without needing to uninstall central modules to change power cables.
- **Third-Order CLC Pi-Filter:** Achieves ~35dB of noise attenuation at 1kHz, eliminating audible regulation ripple and high-frequency switching hash (65kHz+).
- **Optional +5V Sub-System:** Includes an unpopulated TO-220 footprint compatible with high-efficiency switching buck regulators (e.g., Murata OKI-78SR-5) to drive 5V-enabled IDC headers locally.
- **LED Rail Indicators:** Post-filter diagnostic LEDs immediately confirm active voltage delivery to the distribution rail.

## Filter & Power Specifications

- **Input Terminals:** 3-pin screw terminal block (5.08mm pitch, Phoenix Contact standard).
- **Maximum Current Load:** 2A - 2.5A continuous per board.
- **Input Capacitors ($C_{in}$):** 220µF / 25V+ Low-ESR Electrolytic ($\le$ 0.1Ω impedance at 100kHz).
- **Series Inductors ($L$):** 330µH Toroidal Chokes ($\ge$ 3A rated, low DCR).
- **Output Capacitors ($C_{out}$):** 4700µF / 25V Low-ESR Electrolytic ($\le$ 0.03Ω impedance at 100kHz).

## Critical Assembly & Solder Notes

⚠️ **WARNING: REVERSE POLARITY HAZARD**
Electrolytic capacitors are polarized. On the **-12V rail**, Ground (0V) is the more positive potential. You **MUST** solder the positive lead (+) of the -12V capacitors directly to the Ground plane, and the negative lead (-) to the -12V trace. Installing them backward will cause the capacitors to burst violently upon power-up.

- **Thermal Reliefs:** Ensure your KiCad zone properties retain thermal relief spokes for through-hole pads, otherwise the massive output capacitors and ground planes will sink all the heat from your soldering iron.
- **Mechanical Security:** Because the 4700µF output capacitors carry significant mass, it is recommended to apply a small dab of non-conductive electronics-grade silicone or hot glue between the base of the capacitor capacitor body and the PCB after soldering to relieve trace stress during case transit.

## License

This project is open-source hardware. Feel free to modify, build, or manufacture your own variants.
