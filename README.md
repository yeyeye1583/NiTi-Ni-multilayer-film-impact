-------------------------------------------------------------------------------
Introduction:
-------------------------------------------------------------------------------
Title: Molecular Dynamics Simulation Dataset of Shock-induced Microstructure Evolution in Ni-NiTi Multilayer Thin Films
Institutions: [您的单位名称]
Authors:
 - [作者1姓名]
 - [作者2姓名]
 - [作者3姓名]
 - [作者4姓名]
 
Technical POC: [联系人姓名] ([联系人邮箱])
Data Access POC: [联系人姓名] ([联系人邮箱])

Funding Statement:
[在此处添加资助声明，例如：
This work is supported by the National Natural Science Foundation of China under Grant No. XXXXXX.
或
This research received no specific grant from any funding agency in the public, commercial, or not-for-profit sectors.]

License:
This work is licensed under MIT License. To view a copy of this license, visit https://opensource.org/licenses/MIT

Date:
This dataset was uploaded on [上传日期，例如：January 15, 2025]

Citation:
When using this dataset, please cite the following publication:
[作者姓名], "[论文标题]", [期刊名称], [年份]

-------------------------------------------------------------------------------
Dataset Description:
-------------------------------------------------------------------------------
This dataset provides molecular dynamics simulation input scripts, output data, and analysis results for shock wave propagation in Ni-NiTi multilayer thin films using the Large-scale Atomic/Molecular Massively Parallel Simulator (LAMMPS).

Simulations are performed using LAMMPS with the Modified Embedded-Atom Method (MEAM) potential for Ni-Ti interactions. The dataset includes complete simulation workflows from energy minimization to shock loading phases.

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

2. "Sample_Simulation_Data" directory contains:
   - Thermodynamic output files (run.out, run.${stemperature}K.out)
   - Spatial profile data (density, temperature, pressure, velocity)
   - Atomic trajectory files (dump_*.xyz, dumpschock_*.xyz)

3. "Model_and_Parameters" directory contains:
   - Initial atomic structure file (NiTi_Ni5cengNiTi.lmp)
   - MEAM potential files (library.meam, NiTi.meam)

4. Key simulation parameters (modifiable in in.NiTitongjv):
   - stemperature: Initial system temperature
   - vpiston: Piston velocity controlling shock strength
   - time_eq, time_shock: Duration of equilibration and shock phases
   - alattice: Lattice constant

5. Analysis capabilities included:
   - Common Neighbor Analysis (CNA) for crystal structure identification
   - Per-atom stress and energy calculations
   - Spatial binning for property profiling along shock direction
   - Velocity and temperature distribution analysis

Note: Large output files (>100MB) are recommended to be stored separately and accessed via provided file manifest.
