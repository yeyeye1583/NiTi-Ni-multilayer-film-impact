# NiTi-Ni-multilayer-film-impact
Ni-NiTi Multilayer Thin Film Shock Simulation - LAMMPS MD. Investigates shock-induced behavior and phase transformations at atomic scale. Includes complete simulation scripts and analysis tools for impact dynamics research.


## Overview

The core simulation is performed using LAMMPS, a widely-used open-source molecular dynamics package. The main input script configures the model, interatomic potential, integration parameters, and analysis routines.

## Files and Directories

- **`in.NiTitongjv`**: The primary LAMMPS input script. This file defines the entire simulation workflow, including:
  - Model initialization and energy minimization.
  - Thermal equilibration (NPT ensemble).
  - Shock loading via a piston method (NVE ensemble).
  - On-the-fly calculation of properties like stress, temperature, and velocity profiles.

- **`/Sample Simulation Data`**: This directory contains a subset of the computational results obtained by running the main script. It is intended for validation and preliminary analysis. Contents may include:
  - `run.out`: Thermodynamic output.
  - `temp.profile`, `pressure.profile`: Spatial profiles of temperature and pressure.
  - `dumpschock_*.xyz`: Atomic trajectory files for visualization.

- **`/Model and Parameters`**: This directory holds the essential input files that define the simulated system.
  - `NiTi_Ni5cengNiTi.lmp`: The initial atomic coordinates data file.
  - `library.meam` & `NiTi.meam`: Files defining the Modified Embedded-Atom Method (MEAM) potential for Ni-Ti interactions.

## Getting Started

### Prerequisites
*   LAMMPS must be installed on your system. Pre-built binaries or source code can be found on the [LAMMPS website](https://www.lammps.org/).

### Running the Simulation
1.  Clone this repository.
2.  Navigate to the root directory in your terminal.
3.  Execute the simulation with the command:
    ```bash
    lmp -in in.NiTitongjv
    ```

### Customizing the Simulation
You can easily modify the simulation parameters by editing the `in.NiTitongjv` file. Key variables are defined at the top of the script:
- `stemperature`: Initial system temperature (K).
- `vpiston`: Piston velocity (km/s), which controls the shock strength.
- `time_eq` & `time_shock`: Duration of the equilibration and shock phases.

## License
MIT License

## Contact
For questions regarding the simulation setup, please contact [Your Email or ORCID].


