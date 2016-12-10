6dFGS-COLA
==========

COLA mocks for 6dF Galaxy Survey

The data is available at g2 supercomputer

http://supercomputing.swin.edu.au

g2.hpc.swin.edu.au:/lustre/projects/p018_swin/jkoda/6dFGS-COLA/


## Mocks

mocks/v0.3/mocks    mock catalogue   (mask applied)
mocks/v0.3/rands    random catalogue (with applied)

There are 1180 mocks, index  00001 - 01180.


## File format (ascii text file)

Lins starting with # is a comment

Column 1-3: x y z [1/h Mpc] comoving coordinate in redshift space
Column 4:   vr    [km/s]    line-of-sight velocity
Column 5:   redshift
Column 6:   redshift_cosmo  redshift without RSD
Column 7:   M_200m [1/h M solar]  host halo mass
Column 8:   r_sat [1/h Mpc] satelite galaxy displacement from halo center
Column 9    vr_sat [km/s]   line-of-sight virial virial


## HOD

The probabilty that a halo of mass M has a central galaxy:

<ncen(M)> = 1/2 { 1 + erf[ (log10 M - log10 M_min)/sigma] }

The mean number of satellite galaxies if the halo has a central galaxy:

<nsat(M)> = [(M - M_min)/M1]^alpha

The halo mass is M_200m; the mean density within the halo is 200 times
the mean matter density.


M_min(z) = 12.044819376747501 + 22.819438315305984*x +  110.43647374068253*x^2
           - 1435.652917667794*x^3 + 3679.37702426386^4

where x = z - 0.05

sigma = 0.5
log10(M1/M_min) = 1.4
alpha = 1.5


## Cosmology and simulation parameters

Omega_m = 0.30
h       = 0.68

Simulation boxsize: 1200 [1/h Mpc] on a side
N-body particle mass: m = 2.788529e+10
Snapshot redshift:    z = 0.1


## Halo catalogues

/lustre/projects/p018_swin/jkoda/work/6df_fit/halo_lightcone rand_lightcone

Halo catalogue is created from FoF halo catalogue:
    fof/
and subsampled particles,
    particles/

COLA halo mass: M >= 3.0e12

The mass of COLA FoF haloes are remapped to Tinker (2010) mass
function by matching the abundance n(>M).

Particle halo:  6.0e11 <= M < 3.0e12

`Fake` haloes are added to the halo catalogue from subsampled N-body
particles, given a mass according to the same Tinker (2010) mass
function. The lower limit of this type of halo is given by the number
of the particle data.

Lightone n (1 <= n <= 590) and n + 590 are created from the simulation
box;
1   -  590 are created from 0 <= x < 600
591 - 1180 are created from 600 <= x < 1200.

See
/lustre/projects/p018_swin/jkoda/work/6df_fit/data/fof
or
/lustre/projects/p018_swin/jkoda/work/6df_fit/data/indices.txt
to see which fof/part index is used for the lightcone.


## Parent catalogues

/lustre/projects/p018_swin/jkoda/work/6df_fit/mock/v0.3/sigma0.5
parent_mocks
parent_rands

*Parent catalogue* is a halo catalogue before applying the mask
 (incompleteness); the catalogue covers exactly 2pi steradian of the
 sky.

Parent catalogues are in real space and does not have redshift with RSD
(column 5 in the masked catalgoue).

