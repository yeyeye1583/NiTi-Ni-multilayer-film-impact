-------------------------------------------------------------------------------
Introduction:
-------------------------------------------------------------------------------
Title: Molecular Dynamics Simulation Dataset of Shock-induced Microstructure Evolution in NiTi-Ni Multilayer Thin Films
Institutions: Chongqing University of Posts and Telecommunications

License:
This work is licensed under MIT License. To view a copy of this license, visit https://opensource.org/licenses/MIT

Date:
This dataset was uploaded on 2025.11.21



-------------------------------------------------------------------------------
Dataset Description:
-------------------------------------------------------------------------------
This dataset provides molecular dynamics simulation input scripts, output data, and analysis results for shock wave propagation in Ni-NiTi multilayer thin films using the Large-scale Atomic/Molecular Massively Parallel Simulator (LAMMPS).

Simulations are performed using LAMMPS with the second-nearest-neighbor modified embedded atom method (2NN-MEAM) potential for NiTi-Ti interactions. The dataset includes complete simulation workflows from energy minimization to shock loading phases.

The simulation parameters include:
- Initial temperature: 500 K
- Piston velocity: 2.1 km/s (converted to 6 Å/ps)
- Time step: 0.001 ps
- Equilibration phase: 40 ps (40,000 steps)
- Shock phase: 50 ps (50,000 steps)

-------------------------------------------------------------------------------
Organization:
-------------------------------------------------------------------------------
This dataset is organized as follows:

1. "in.NiTitongjv" - Main LAMMPS input script containing:
   - Model initialization and energy minimization
   - Thermal equilibration (NPT ensemble)
   - Shock loading via piston method (NVE ensemble)
   - Real-time calculation of stress, temperature, and velocity profiles

2. "Partial Data" directory contains:
   - Thermodynamic output files (run.out, run.${stemperature}K.out)
   - Spatial profile data (density, temperature, pressure, velocity)

3. "Model_and_Parameters" directory contains:
   - Initial atomic structure file (NiTi_Ni5cengNiTi.lmp)
   - MEAM potential files (library.meam, NiTi.meam)

4. Key simulation parameters (modifiable in in.NiTitongjv):
   - stemperature: Initial system temperature
   - vpiston: Piston velocity controlling shock strength
   - time_eq, time_shock: Duration of equilibration and shock phases
   - alattice: Lattice constant

5. Analysis capabilities included:
   - Per-atom stress and energy calculations
   - Spatial binning for property profiling along shock direction
   - Velocity and temperature distribution analysis
