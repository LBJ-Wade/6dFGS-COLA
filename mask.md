mask
=======

winx_6dfgs.dat



- line 1: dummy header line

```
# temporary line
```

- line 2: header

```
 120 240 240  600.  1200.  1200.  0.  600.  600.
 nx  ny  nz   Lx    Ly     Lz     x0  y0    z0
```

nx, ny, nz: number of grids in x,y,z direction, respectively.
Lx, Ly, Lz: size of the cuboid [1/h Mpc]
x0, y0, z0: position of the observer, where 0 is the cornor of the cuboid

- Line 3 to `nx*ny*nz + 2` mask (incompleteness)

One number per line, f[ix, iy, iz], in Fortran order

```C
for(int iz=0; iz<nz; ++iz)
 for(int iy=0; iy<ny; ++iy)
  for(int ix=0; ix<nx; ++ix
    printf("%e\n", f[ix, iy, iz])
```

The normalization of the mask is arbitrary.
Mock galaxies are subsample by the ratio f[ix, iy, iz]/max(f).



