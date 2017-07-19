# AIDFT+U

# Goal
Evaluate ab initio the Coulomb and exchange parameters for DFT+U calculations. DFT+U theory is based on DFT, but the intra-atomic Coulomb and exchange interactions of localized valence electrons are effectively treated at the Hartree-Fock level of theory. DFT+U theory can correct the self-interaction errors in DFT, given the average Coulomb (U) and exchange (J) interactions of these localized valence electrons as input. To obtain these two parameters, previously researchers either empirically fitted them or performed constrained DFT calculations. We recently proposed instead to evaluate the U and J using unrestricted Hartree-Fock calculations on electrostatically embedded clusters.

# Implementation in GAMESS
The method used to evaluate these parameters is based on unrestricted Hartree-Fock calculations. A few subroutines were modified to get GAMESS to calculate U and J.

The modifications to each subroutine are: gamess.src : check input files and variables; prppop.src :get Mulliken populations for calculating U and J;

int2a.src: calculate the onsite two-electron integrals in the basis of the atomic orbitals;

rhfuhf.src: extensive modifications to calculate U and J;

scflib.src: calculate the Coulomb and exchange integrals through building the Fock matrix with direct SCF methods.
