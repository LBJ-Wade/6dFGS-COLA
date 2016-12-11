nbar_parent
===========

mocks/v0.3/analysis/nbar_parent

Number density of the parent catalogues (i.e. without mask).

## summary

Summary for all mocks

nbar_parent_summary_mock.txt
nbar_parent_summary_rand.txt

Column 1: redshift
Column 2: n.realisation
Column 3: mean nbar(z)
Column 4: standard deviation nbar(z)

## for each realisation

mock/
rand/

Neglect line 1: `Serial mode`

Column 1: z
Column 2: nbar(z)

## nbar data

Target nbar(z) is:

```
nbar(z) = 1.415179*2.94123282e-02*exp(-2.34906602e+01*z  -3.52187066e+02*z^2
          + 1.00558482e+03*z**3)
```

which means, the HOD paramter M_min(z) is adusted to give this number
density. The result, however, is not exactly not this function due to
lack of low mass halo for z < 0.05, and imperfect mass calibration for
high mass (z > 0.15).
