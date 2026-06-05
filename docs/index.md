# synth-suite

Welcome to the **synth-suite**! This is the central umbrella repository and documentation hub for the Elkins Biophysics ecosystem. This suite of tools provides a comprehensive array of simulation and modeling software for structural biology and biophysics.

## Component Projects

The ecosystem is built using a **meta-repo** architecture. Each component is managed in its own repository to preserve isolation and allow targeted testing, while this central hub documents their integration.

- [**synth-pdb**](https://elkins.github.io/synth-pdb): Core molecular geometry, atomic coordinates, and coordinate manipulations.
- [**synth-nmr**](https://elkins.github.io/synth-nmr): Nuclear Magnetic Resonance (NMR) observable simulations (chemical shifts, NOEs, J-couplings).
- [**synth-cryo-em**](https://elkins.github.io/synth-cryo-em): Cryogenic electron microscopy map generation, CTF application, and FSC resolution analysis.
- [**synth-afm**](https://elkins.github.io/synth-afm): Atomic Force Microscopy (AFM) surface topography simulations.
- [**diff-biophys**](https://elkins.github.io/diff-biophys): Differentiable biophysics modules powered by modern autodiff frameworks for reverse-modeling and refinement.

## Integration & Philosophy

These tools are designed to work together seamlessly. For example, atomic coordinate pipelines initialized in `synth-pdb` can be fed directly into `synth-cryo-em` to simulate instrument outputs, or into `synth-nmr` to estimate ensemble spectra. 

Our ongoing engineering goal is to move overlapping mathematical logic and physical constants from these independent repositories into a shared core, minimizing redundancies while preserving the specialized capabilities of each tool. See the [Roadmap](ROADMAP.md) for current engineering milestones.
