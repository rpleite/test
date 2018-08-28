# Nonequilibrium Free-Energy Calculations of Fluids using LAMMPS code

What is this?
------------
This repository contains a set of source codes and input scripts that allows to perform nonequilibrium free-energy calculations of fluid-phase systems using [LAMMPS](http://lammps.sandia.gov/) code. Details about the code implementation, capabilities and obtained results with these methods will be found in:

["Nonequilibrium Free-Energy Calculations of Fluids using LAMMPS"  
Rodolfo Paula Leite, and Maurice de Koning  
Computational Material Science (submitted)](https://)

What are the repository contents?
--------------
[`examples`](examples): This directory contains input scripts to run MD simulations.

source codes: The main directory contains our LAMMPS source codes.

[`README`](README.md): A brief overview of the distribution.

How to install?
--------------
To install these source codes, please follow the steps below:

1) Go to LAMMPS webpage (https://lammps.sandia.gov/download.html) and download the source code at your local machine.

2) Clone this repository to a subdirectory named `USER-FFE` inside the `src/` directory of your LAMMPS installation:
```
cd <your-local-lammps>/src/
git clone https://github.com/plrodolfo/FluidFreeEnergyforLAMMPS.git USER-FFE
```
WARNING: The next step will overwrite some native source codes in your src folder. However, our source codes have compatibility with old versions. Make a backup of your src folder if you want.

3) Choose some machine file (e.g. Makefile.mpi) and build LAMMPS using the following commands:

i) make yes-rigid

ii) make yes-user-ffe

iii) make mpi

NOTE: Steps i and ii are necessary to install the required packages to reproduce the results presented in our [paper](https://).

4) If LAMMPS was successully built, an executable called "lmp_mpi" will be created in the src directory. Otherwise, an error message is reported. For futher details, please visit the ["Build LAMMPS"](https://lammps.sandia.gov/doc/Build.html) section on user documentation.

How to use these codes?
--------------
Instructions of how to use these codes can be found inside each LAMMPS input script in the [`examples`](examples) directory or in our [paper](https://).

Author and Contact:
--------------
Rodolfo Paula Leite - pl.rodolfo@gmail.com
