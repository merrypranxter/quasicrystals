# Cut-and-Project Method

The cut-and-project (or strip projection) method is the most powerful and general
framework for constructing quasicrystal structures. It explains both WHY quasicrystals
have long-range order and WHY they produce sharp diffraction peaks despite lacking
periodicity.

## 1. Intuition: Shadows of Higher-Dimensional Lattices

Imagine a 2D square lattice (grid of dots). Shine a light from directly above at
a slight irrational angle, and look at the shadows of the dots projected onto a 1D
line. If the angle is rational (e.g., 45°), the projected dots form a periodic 1D
lattice. If the angle is irrational (e.g., arctan(1/phi)), the projected dots form
a QUASIPERIODIC sequence — aperiodic, but with long-range order.

This is the essence of cut-and-project: a higher-dimensional periodic lattice,
sliced at an irrational angle, yields a quasiperiodic structure of lower dimension.

## 2. Formal Construction

### Setup
- Start with a lattice L in n-dimensional space R^n (typically a hypercubic lattice Z^n)
- Choose a d-dimensional "physical" subspace E_parallel (the space we want to tile)
- The complementary (n-d)-dimensional subspace is E_perp (internal/perpendicular space)
- Choose an "acceptance window" (or "window") W in E_perp — a bounded region

### Projection
For each lattice point x in Z^n:
1. Project x onto E_parallel: x_par = pi_par(x)
2. Project x onto E_perp: x_perp = pi_perp(x)
3. Include x_par in the quasicrystal point set IF x_perp lies in the window W

The resulting set of points Lambda = { pi_par(x) : x in Z^n, pi_perp(x) in W }
is the quasicrystal.

## 3. Penrose Tiling from 5D Lattice

The Penrose tiling arises from projecting the 5D hypercubic lattice Z^5 onto 2D:

### The Five Basis Vectors
In R^5, the 5 standard basis vectors e_1,...,e_5 project to 2D as:
    f_k = (cos(2*pi*k/5), sin(2*pi*k/5))  for k = 0,1,2,3,4

These are the 5 unit vectors at 72° angles to each other in the 2D plane.
The projection pi_par: R^5 -> R^2 sends e_k to f_k.

### The Window
The window W is the projection of the unit hypercube [0,1]^5 onto E_perp (3D).
The resulting window is a regular triacontahedron (in a suitable 3D representation)
or equivalently a Euclidean pentagoid in the 3D internal space.

### Result
The projected points form the vertices of a Penrose tiling! The tiles (rhombi or
kite-darts) arise naturally from the geometry of the hypercubic lattice.

Alternatively: embed 2D in R^4 (not R^5) using the subgroup of Z^5 with sum=0.

## 4. Icosahedral QC from 6D Lattice

For 3D icosahedral quasicrystals:
- Start with the 6D hypercubic lattice Z^6
- Physical space: E_parallel = R^3 (3D physical space)
- Internal space: E_perp = R^3 (3D perpendicular space)
- The 6 basis vectors project to the 6 five-fold axes of the icosahedron in E_parallel

The acceptance window W is an icosahedron (or rhombic triacontahedron) in E_perp.
The resulting 3D point set is the icosahedral quasicrystal — the 3D analogue of Penrose.

## 5. Why Irrational Angle Produces Aperiodic Order

If the projection angle between E_parallel and the lattice directions is RATIONAL,
the lattice points whose E_perp projection lands in W form a PERIODIC subset of L.
The projected point set is then periodic — a crystal.

If the angle is IRRATIONAL (as for all quasicrystal projections), no lattice vector
lies exactly in E_parallel. Therefore the projected point set has no translational
period — it is aperiodic.

But because the source is a LATTICE (fully ordered), the projected set retains
long-range correlations. Every finite patch appears infinitely often (uniform
recurrence) — hence long-range order.

The specific irrational that matters is determined by the symmetry:
- 5-fold: cos(72°) = (sqrt(5)-1)/4 involves sqrt(5) → phi
- 8-fold: cos(45°) = 1/sqrt(2) involves sqrt(2) → silver ratio
- 12-fold: cos(30°) = sqrt(3)/2 involves sqrt(3)

## 6. Why Sharp Diffraction Peaks Appear

### Poisson Summation Formula
The diffraction intensity is the squared absolute value of the Fourier transform
of the point set Lambda. For a cut-and-project set:

    I(k) = |FT[Lambda](k)|^2

Using the Poisson summation formula for the parent lattice L:
    FT[L] is also a lattice (the reciprocal lattice L*)

The cut-and-project selection (via window W) modulates the intensities by the
Fourier transform of the window function FT[W].

Result: Delta-function (sharp) peaks appear at every reciprocal lattice vector k*
that projects into E_parallel AND whose E_perp component k*_perp satisfies
FT[W](k*_perp) != 0.

Since W has non-zero measure, FT[W] is non-zero on a dense set — and the peaks
in the physical diffraction pattern are DENSE but individually sharp (delta functions).
This is exactly what is observed in quasicrystal diffraction!

## 7. De Bruijn's Pentagrid

Nicolaas de Bruijn showed that the Penrose tiling can be constructed by the "dual"
of a pentagrid: five families of parallel lines at angles 72° apart. Where lines
from different families intersect, tiles are born. This is a special case of
cut-and-project where the acceptance window is the unit interval.

Pentagrid construction:
1. Define 5 families of parallel lines with spacing 1, oriented at angles k*36° 
2. Lines in family j: x*cos(j*pi/5) + y*sin(j*pi/5) = m + gamma_j for integer m
3. Each intersection of lines from families j and k defines a tile vertex
4. The tile type (thick/thin) depends on the angle between the intersecting families
5. Parameter gamma_j shifts within the window — different values give different tilings

## 8. Pseudocode for Cut-and-Project

```
function cut_and_project_penrose(N_range, gamma=[0,0,0,0,0]):
    // Generate 2D Penrose tiling vertices via 5D projection
    
    // Basis vectors in 2D (physical space)
    f = [(cos(2*pi*k/5), sin(2*pi*k/5)) for k in 0..4]
    
    // For each 5-tuple of integers in range [-N, N]^5
    vertices = empty set
    for (n0,n1,n2,n3,n4) in [-N..N]^5:
        // Physical space projection
        x = sum(n_k * f[k][0] for k in 0..4)
        y = sum(n_k * f[k][1] for k in 0..4)
        
        // Perpendicular space projection (3D)
        x_perp = sum(n_k * g[k][0] for k in 0..4)  // g = perp basis
        y_perp = sum(n_k * g[k][1] for k in 0..4)
        z_perp = (n0+n1+n2+n3+n4) / sqrt(5)       // 5th component
        
        // Acceptance: is perp projection in window W?
        if point(x_perp, y_perp, z_perp) in W:     // W = projected hypercube
            vertices.add((x, y))
    
    return vertices
```

The window W is typically the projection of [0,1]^5 onto E_perp — a 3D polytope
that can be tested with 10 half-space inequalities (faces of the pentatope).
