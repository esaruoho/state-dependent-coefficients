# State-Dependent Coefficients — Interactive Tool

A single-file, dependency-free interactive teaching instrument for the idea that the
"constants" of electrical-engineering pedagogy — inductance *L*, capacitance *C*,
resistance *R*, permeability *μ*, permittivity *ε*, conductivity *σ*, characteristic
impedance *Z₀*, transformer ratio *n*, mutual inductance *M* — are not constants. They
are **operating-point coefficients of state-dependent functions**.

Turn one slider (current, flux, temperature, bias voltage, mechanical stress, frequency,
coupling angle, gap) and every graph, 3-D surface and derived quantity re-solves.

## The point it makes

The full constitutive law of an inductor is

```
V = L·dI/dt  +  I·dL/dt
```

The second term, **I·dL/dt**, is non-zero exactly when *L* depends on its own state
variable (core saturation). Introductory EE texts drop it. The tool shows a live bar
decomposition of both terms: at a small-signal working point the parametric term reads
≈ 0 % and the textbook `V = L·dI/dt` holds; drive the core toward saturation and the
term climbs to a large fraction of the induced voltage. The same is shown for the
capacitor's `I = C·dV/dt + V·dC/dt`.

## Core-material presets

Switch the core material to change the curve **shapes**, not just the operating point:

- **Generic teaching core** — soft small-signal baseline.
- **Silicon-iron** — calibrated to the NASA NAS9-10416 (1971) parametric-transformer
  measurement of 88 % at 500 W.
- **Metglas 2605SA1** — amorphous Fe, higher permeability and lower hysteresis, sharper
  saturation knee; the illustrative efficiency rises toward 91–92 % and the parametric
  channel widens. This is a *falsifiable prediction*, **not** an over-unity claim — the
  parametric (saturable-reactor) channel is bounded by the Manley–Rowe relations.

## Caveats

The functional forms are physically-motivated illustrations (saturation, Curie roll-off,
Class-II ceramic bias roll-off, copper temperature coefficient, Villari stress effect),
not a SPICE-grade device model. Efficiency numbers are calibrated to the silicon-iron
anchor — a fit, not a bench measurement. No over-unity is implied or claimed.

## Background / prior art

Parametric (variable-reactance) energy transfer is established engineering, not fringe:
Steinmetz (1909), Manley–Rowe relations (1956), Wanlass parametric transformer
(IEEE WESCON 1968), NASA NAS9-10416 (1971), Abdel-Kader C-core replication
(First ASAT Conference, Cairo, 1985). The "speed voltage" term appears in graduate
electric-machinery courses; the Manley–Rowe relations appear in graduate microwave
courses. The term is simply absent from introductory texts.

## Usage

Open `index.html` in any modern browser, or visit the GitHub Pages site. No build step,
no dependencies, works offline and on mobile.
