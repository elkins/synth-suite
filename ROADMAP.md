# Roadmap: Biophysics Suite Refactoring & Centralization

As `synth-suite` grows into a mature meta-repo, we are undertaking a series of structural refactors to remove duplicated logic, consolidate physical constants, and streamline the underlying math across all constituent projects.

## Goal 1: Consolidate Mathematical Operations
Several projects (`synth-cryo-em`, `diff-biophys`, `synth-nmr`) independently implement standard biophysics algorithms such as:
- Fourier Shell Correlation (FSC)
- 3D Grid operations and interpolation
- Euler angle and quaternion manipulations

**Action Items:**
- [ ] Create a shared `synth-core` (or `biophysics-core`) Python package.
- [ ] Migrate robust `compute_fsc` (with NumPy 2.x and complex arithmetic fixes) to the shared core.
- [ ] Migrate `diff-biophys` and `synth-cryo-em` to import standard signal processing functions from the shared core.

## Goal 2: Unified Physical Constants
Currently, fundamental values such as Planck's constant, Boltzmann's constant, or standard gyromagnetic ratios for NMR are defined individually within project scopes.

**Action Items:**
- [ ] Centralize `constants.py` inside the core library.
- [ ] Establish standard physical unit types (e.g., forcing Angstroms vs Nanometers).

## Goal 3: Meta-Package Deployment
To make installing the ecosystem frictionless, we will deploy a top-level `synth-suite` PyPI package.

**Action Items:**
- [ ] Publish independent versions of all current projects.
- [ ] Establish a `pyproject.toml` in `synth-suite` that declares the specific compatible versions of `synth-pdb`, `synth-cryo-em`, etc., as dependencies.
- [ ] Test the monolithic `pip install synth-suite` on clean environments.
