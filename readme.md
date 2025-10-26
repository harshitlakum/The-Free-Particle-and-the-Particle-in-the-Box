# The Free Particle and the Particle in a Box

Interactive notebook exploring two quantum staples: **free particle** dispersion and **particle-in-a-box** eigenstates. Includes analytic formulas, normalized wavefunctions, probability currents, and widgets to poke the physics.

![Python](https://img.shields.io/badge/Python-3.9%2B-blue) ![Notebook](https://img.shields.io/badge/Jupyter-Notebook%2FLab-yellow) ![License](https://img.shields.io/badge/License-MIT-green)

---

## What’s Inside (and why it matters)

* **Free particle**: Gaussian wavepacket ( \psi(x,0)\propto e^{-\frac{(x-x_0)^2}{4\sigma^2}}e^{ik_0 x} ) with dispersion
  ( \omega=\frac{\hbar k^2}{2m},\quad v_g=\frac{\partial\omega}{\partial k}=\frac{\hbar k}{m} ).
  Shows spreading, group vs phase velocity, and probability **current** ( j=\frac{\hbar}{m},\Im(\psi^*\partial_x\psi) ).

* **Infinite square well** on ( x\in[0,L] ):
  ( \psi_n(x)=\sqrt{\tfrac{2}{L}}\sin!\big(\tfrac{n\pi x}{L}\big),\quad E_n=\frac{n^2\pi^2\hbar^2}{2mL^2} ).
  Superpositions, revival hints, nodes/antinodes, and proper boundary conditions ( \psi(0)=\psi(L)=0 ).

* **Sanity checks** you’re expected to pass: normalization (\int|\psi|^2dx=1),
  uncertainty lower bound ( \Delta x,\Delta p\ge \hbar/2 ), and conserved (\int |\psi|^2 dx) under unitary evolution.

---

## Installation

```bash
pip install numpy matplotlib ipywidgets
# Classic Notebook widgets (if needed):
jupyter nbextension enable --py widgetsnbextension
```

> JupyterLab 3+ usually needs no extra widget install. If sliders don’t show, you didn’t enable widgets—fix that first.

---

## Usage

1. **Clone** the repo and **open** the notebook:

   ```bash
   jupyter notebook
   ```
2. Open `UE02.ipynb` and run cells **top to bottom**.
3. Use sliders to tweak:

   * **Free particle**: (m,,k_0,,\sigma,,x_0,,t)
   * **Box**: (L,,n) or superposition coefficients, time (t)

> Pro tip: set units ((\hbar=1, m=1, L=1)) while prototyping. If you reintroduce SI, be consistent or your scales will be nonsense.

---

## Repository Structure

```
.
├─ UE02.ipynb                 # Main interactive notebook (free particle + box)
├─ README.md                  # You’re reading it
└─ LICENSE
```

No external data needed—this is **theory + visualization**.

---

## Plots & Widgets (what you actually see)

* (|\psi(x,t)|^2) vs (x), **phase**, and **current** (j(x,t)) for the free particle
* (|\psi_n(x)|^2), energy ladders (E_n), and time evolution for superpositions in the box
* Optional FFT to visualize momentum-space (|\phi(p,t)|^2) (windowing to avoid ringing)

---

## Common Failure Modes (don’t be that person)

* **Wrong normalization** of Gaussians or eigenstates → fake probabilities.
* **Forgetting boundary conditions** in the well → garbage at (x=0,L).
* **Mixing units** (SI vs natural) → velocities/energies off by orders of magnitude.
* **Reading phase as probability** → plot (|\psi|^2) when making physical claims.

---

## Contributing

PRs welcome—clean code, clear math, and tests for normalization/orthogonality. If you add a potential, include analytic limits or regression plots.

---

## License

MIT.


