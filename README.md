# Centroid data set

Data set to learn the force on the centroid and the dipole moment.

## Data set generation

1. Ring polymer beads are initialised at the equilibrium geometry and with momenta drawn from the Maxwell-Boltzmann distribution. The average total momentum is subtracted, so the center of mass remains stationary.

2. The ring polymer is equilibriated at the set temperature for 200 time steps.

3. Ring polymer configurations are saved with 200 decorrelating PIMD steps between them, resampling the momentum from the Maxwell-Boltzmann distribution after each storage.

4. For each configuration, the force on the centroid and the dipole moment of the centroid are averaged over fluctuations of the ring polymer internal modes. The internal modes are all shifted to the same frequency $\Omega$, which is close to the system's physical frequencies. The fluctuations are integrated with time step $\delta t = \frac{\pi}{i_\mathrm{cyc}\Omega}$, $i_\mathrm{cyc}$ = 20 (ie. 40 steps per oscillation).

5. The data is written to disk. The first row of the data file contains the number of carbons $n_\mathrm{C}$, the number of hydrogens $n_\mathrm{H}$ and the number of sample points. Each following row contains (in this order) the centroid configuration in Angstrom, the difference of the averaged force on the centroid to the classical force $f_c - f_\mathrm{cl}$, the averaged dipole moment and the difference of the averaged dipole moment to the classical dipole moment $\mu_c - \mu_\mathrm{cl}$


## Current data sets:

| File name | Temperature [K] | Bead number | Time step size [fs] |
|-|-|-|-|
| | 200 | 64 | 1
