# Circuit Lab

Circuit Lab is an interactive simulator for series, parallel, and mixed resistive circuits, built to make the distinction between these two wiring topologies concrete rather than purely formulaic.

The simulator is not animation dressed up as physics. Every frame, it solves the actual circuit using Ohm's law (V = IR) and the standard series/parallel resistance combination rules, Req = R1 + R2 + ... for series and 1/Req = 1/R1 + 1/R2 + ... for parallel, then derives current, voltage drop, and dissipated power (P = I squared times R) for every component from that solution. Bulb brightness is rendered proportionally to actual power output, not a fixed animation keyed to a slider position.

The most instructive interaction is deliberately destructive: click any bulb to simulate a burned-out filament, modeled as that component's resistance going to infinity (an open circuit). In series, this drops current to zero everywhere, since there is exactly one conduction path. In parallel, the remaining branches are electrically independent and are unaffected, since each one has its own return path to the source. Seeing that asymmetry play out live is the core teaching moment of the lab.

Features:
- Series, parallel, and mixed topology modes
- Live circuit solving on every parameter change, no precomputed states
- Per component readouts for voltage, current, and power
- Interactive fault injection (burn out any bulb) with physically correct propagation of the failure
- Live equivalent resistance panel showing the formula solved with your actual numbers

Tech: single self-contained HTML file, vanilla JavaScript, no build step, no dependencies beyond Google Fonts. Runs entirely client-side.

Usage: open `CircuitLab.html` in a browser. Choose a topology, adjust battery voltage and resistances, and try burning out a bulb in each mode to compare failure behavior.
