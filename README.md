# Event Horizon Lab

Event Horizon Lab is a real-time simulator of multi-black-hole dynamics, layering Newtonian gravity, gravitational-wave-driven orbital decay, and a raymarched renderer for gravitational lensing into a single interactive sandbox.

The base layer is an N-body gravitational integrator: every body exerts a Newtonian gravitational force on every other body, and their trajectories are updated each timestep accordingly. This is the same underlying physics that governs planetary motion, just applied to compact, extremely massive objects at much smaller separations. As two black holes spiral toward each other, the simulation adds a gravitational-wave inspiral term, modeling the energy loss that causes orbiting compact objects to lose orbital energy and spiral inward over time. This is the actual physical mechanism behind the binary black hole mergers detected by observatories like LIGO.

When two bodies merge, the simulation does not simply combine their masses. It applies fitting formulas derived from numerical relativity simulations to estimate the final black hole's mass, spin, and recoil ("kick") velocity from asymmetric gravitational wave emission during merger. These fits are a standard technique in computational astrophysics, since directly solving the Einstein field equations for every merger event is computationally intractable in a real-time context.

Gravitational lensing is rendered using raymarching: rays are traced through curved space around each black hole so that background distortion and light bending are computed geometrically rather than faked with a shader trick.

Features:
- N-body Newtonian gravity integrator supporting multiple simultaneous black holes
- Gravitational-wave-driven orbital decay (inspiral)
- Numerical-relativity-fitted merger remnants (final mass, spin, and kick velocity)
- Raymarched real-time rendering of gravitational lensing

Tech: single self-contained HTML file, vanilla JavaScript and WebGL for the raymarched renderer, no dependencies beyond Google Fonts. A discrete or reasonably capable integrated GPU is recommended, since raymarching is the most compute-intensive part.

Usage: open `EventHorizon.html` in a modern browser or my personal website, sid2010abc.github.io. Place black holes, set masses, and run the simulation to watch inspiral and merger unfold.
