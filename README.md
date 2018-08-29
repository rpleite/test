# Nonequilibrium Free-Energy Calculations of Fluids using LAMMPS code

What is this?
------------
This repository contains a set of source codes and input scripts that allows to perform nonequilibrium free-energy calculations of fluid-phase systems using [LAMMPS](http://lammps.sandia.gov/) code. Details about the code implementation, capabilities and obtained results with these methods will be found in:

["Nonequilibrium Free-Energy Calculations of Fluids using LAMMPS"  
Rodolfo Paula Leite, and Maurice de Koning  
Computational Material Science (submitted)](https://)

What are the repository contents?
--------------
[`doc`](doc): This directory contains an updated user manual.

[`examples`](examples): This directory contains input scripts to run MD simulations.

source codes: The main directory contains our LAMMPS source codes.

[`README`](README.md): A brief overview of the distribution.

What is new in these source codes?
--------------
| Code Name                       | Already exists? |  Modification |
| :---                            |     :---:      |     :---      |
|fix_adapt.cpp / .h               | yes            | Added a fscale keyword for kspace pppm and pppm/tip4p styles to adapt only the forces during MD simulations. |
|kspace.cpp / .h                  | yes            | Added a fscale variable in extract() method.                           |
|meam_force.cpp                   | yes            | Added a fscale variable into meam_force function.                         |
|meam.h                           | yes            | Added a fscale variable into meam_force function.                           |
|pair_lj_cut_coul_long.cpp / .h   | yes            | Added a fscale variable (which multiplies only the forces) in the extract() method.                           |
|pair_lj_cut_tip4p_long.cpp / .h  | yes            | Added a fscale variable (which multiplies only the forces) in the extract() method.                         |
|pair_meam.cpp / .h               | yes            | Added a fscale variable (which multiplies only the forces) and the extract() method to adapt parameter over the time.                         |
|pair_sw.cpp / .h                 | yes            | Added a fscale variable (which multiplies only the forces) and the extract() method to adapt parameter over the time.                         |
|pair_ufm.cpp / .h                | yes            | Added citation information inside the code.                          |
|pair_ufm_rw.cpp / .h             | no             | A new pair style which is based on LAMMPS implementation of TIP4P water model.                          |
|pppm_tip4p.cpp / .h              | yes            | Added a fscale variable (which multiplies only the forces).                          |
|pppm.cpp / .h                    | yes            | Added a fscale variable (which multiplies only the forces).                          |

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

i) make yes-kspace

ii) make yes-rigid

iii) make yes-user-meamc

iv) make yes-user-ffe

v) make mpi

NOTE: Steps i, ii, iii and iv are necessary to install the required packages to reproduce the results presented in our [paper](https://).

4) If LAMMPS was successully built, an executable called "lmp_mpi" will be created in the src directory. Otherwise, an error message is reported. For futher details, please visit the ["Build LAMMPS"](https://lammps.sandia.gov/doc/Build.html) section on user documentation.

How to use these codes?
--------------
Instructions of how to use these codes can be found inside each LAMMPS input script in the [`examples`](examples) directory and in our [paper](https://).

Contact:
--------------
Rodolfo Paula Leite - pl.rodolfo@gmail.com
