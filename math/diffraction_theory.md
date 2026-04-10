# Diffraction Theory of Quasicrystals

Diffraction reveals the structure of matter at atomic scales. The discovery of sharp
diffraction peaks with 5-fold symmetry in 1984 (Shechtman et al.) was the experimental
proof that quasicrystals exist. Understanding why sharp peaks arise despite aperiodicity
is central to quasicrystal physics.

## 1. Why Sharp Peaks Despite No Periodicity

In a crystal, Bragg's law explains sharp peaks: constructive interference occurs when
the path length difference between waves reflected from parallel planes equals a whole
number of wavelengths: 2d*sin(theta) = n*lambda.

For a quasicrystal, there are no periodic planes — so why sharp peaks?

The answer: sharp peaks arise from LONG-RANGE ORDER, not from periodicity per se.
A crystal is a special case of long-range order (perfectly periodic). A quasicrystal
has a different kind of long-range order — quasiperiodic — that still produces coherent
constructive interference at specific wavevectors.

Mathematically: the diffraction intensity I(k) is the squared modulus of the Fourier
transform of the atomic density rho(x):
    I(k) = |FT[rho](k)|^2

For a point set {x_n}:
    FT[rho](k) = sum_n exp(i*k*x_n)

This sum is delta-function-peaked at k if the phases k*x_n add coherently.
For a quasiperiodic set, coherent addition occurs at a dense but countable set of k
values — exactly the quasicrystal diffraction spots.

## 2. Poisson Summation Formula

For a lattice L with reciprocal lattice L*:
    sum_{x in L} f(x) = (1/vol(unit cell)) * sum_{k in L*} FT[f](k)

Applied to cut-and-project sets: the diffraction measure of the quasicrystal is
obtained from the diffraction measure of the parent lattice (delta peaks at all L*)
modulated by the Fourier transform of the acceptance window W.

Intensity at reciprocal lattice vector k*:
    I(k*_par) = |FT[W](k*_perp)|^2

where k*_par is the physical-space component and k*_perp is the internal-space component.

Since W is a bounded region with non-zero area, FT[W] is non-zero generically →
most reciprocal lattice vectors give non-zero intensity → dense set of sharp peaks.

## 3. Pure Point Diffraction Spectrum

The diffraction spectrum of a perfect quasicrystal (cut-and-project with Pisot
inflation factor) is **pure point**: it consists entirely of sharp Bragg-like peaks
with no diffuse (continuous) background.

This is in stark contrast to:
- **Amorphous materials**: purely continuous (diffuse) spectrum
- **Liquids**: broad diffuse humps, no sharp peaks
- **Disordered crystals**: sharp peaks + diffuse background
- **Perfect crystals**: pure point (periodic subset of L*)
- **Perfect quasicrystals**: pure point (dense subset of R^d but countable)

The mathematical condition for pure-point diffraction: the inflation eigenvalue must
be a Pisot-Vijayaraghavan (PV) number — all algebraic conjugates have absolute
value less than 1.
- phi = (1+sqrt(5))/2: conjugate is (1-sqrt(5))/2 ≈ -0.618. |conjugate| < 1. PV number. Pure point.
- delta_S = 1+sqrt(2): conjugate is 1-sqrt(2) ≈ -0.414. |conjugate| < 1. PV number. Pure point.

## 4. Irrational Peak Ratios — The Diagnostic Signature

In a crystal, peak positions along any axis are at rational multiples of the
fundamental wavevector — that is, peak spacings are rational ratios.

In a quasicrystal, peak positions involve IRRATIONAL ratios:
- Icosahedral QC: peak spacing ratios include tau = phi ≈ 1.618 (5-fold)
- Decagonal QC: peak ratios involve phi (in-plane) and integer ratios (along axis)
- Octagonal QC: peak ratios involve sqrt(2) (silver ratio related)
- Dodecagonal QC: peak ratios involve sqrt(3)

This is the experimentalist's diagnostic: if you see sharp peaks whose positions
require IRRATIONAL ratios to index, you have a quasicrystal.

## 5. Comparison Table

| Material type  | Diffraction          | Peak positions    | Peak width   |
|----------------|----------------------|-------------------|--------------|
| Perfect crystal | Sharp Bragg peaks   | Rational ratios   | Resolution-limited |
| Quasicrystal   | Sharp Bragg-like    | Irrational ratios | Resolution-limited |
| Glass/amorphous | Broad humps         | No preferred pos  | Very broad   |
| Liquid         | 1-2 broad rings     | Near-neighbor dist| Very broad   |
| Quasi+phason   | Sharp + diffuse     | Irrational ratios | Sharp + halos |

## 6. Indexing Quasicrystal Diffraction

### Crystal Indexing (3D)
In a crystal, each Bragg peak is indexed by 3 integers (h,k,l):
    Q_hkl = h*b1 + k*b2 + l*b3
where b1,b2,b3 are reciprocal lattice vectors.

### Icosahedral QC Indexing (requires 6 integers)
For an icosahedral quasicrystal, every diffraction peak requires 6 integers:
    Q = n1*d1 + n2*d2 + n3*d3 + n4*d4 + n5*d5 + n6*d6

where the 6 basis vectors d_i are related to the icosahedral symmetry:
    d1 = (2*pi/a_qc) * (1, tau, 0) / (1+tau^2)^0.5  (and its icosahedral partners)

The factor tau = phi appears explicitly in the basis vectors.

This 6-integer indexing is NECESSARY and SUFFICIENT — you cannot index the pattern
with fewer integers (unlike a periodic crystal where 3 suffice).

The 6D parent space index (h1,h2,h3,h4,h5,h6) maps to physical space vector via:
    Q_physical = sum_i h_i * pi_par(e_i)

where e_i are the 6D basis vectors and pi_par is the projection to physical 3D.

### Decagonal QC Indexing (5 integers)
For decagonal quasicrystals (periodic along c-axis):
    Q = h1*a1 + h2*a2 + h3*a3 + h4*a4 + l*c
where a1-a4 are the 4 in-plane quasicrystal basis vectors and c is the periodic axis.
4+1 = 5 integers needed.

## 7. D-Spacings and Peak Intensities

### D-Spacings
The "d-spacing" of a peak in a quasicrystal: d = 2*pi/|Q|.
Unlike crystals, quasicrystal d-spacings do NOT repeat periodically — they form
a quasi-discrete set with irrational ratio relationships.

For icosahedral QC, d-spacings satisfy:
    d_{n1,n2,n3,n4,n5,n6} = 2*pi / |sum n_i * d_i|

The most prominent d-spacings are determined by the dominant peaks (small |n_i|).

### Peak Intensities
Peak intensity I ~ |FT[W](Q_perp)|^2 * |atomic form factor|^2

For a single atomic species, the atomic form factor is constant, and intensities
are governed by |FT[W]|^2. This is maximized when Q_perp = 0 (strongest peaks)
and falls off as Q_perp increases (higher-indexed peaks are weaker).

The strongest peaks in a Penrose/icosahedral pattern are those with small internal-space
components — these correspond to small (n1,...,n6) index sets, analogous to low-index
planes in a crystal.

## 8. Phason Disorder and Diffuse Scattering

### Phasons
In a crystal, atomic displacements break translational symmetry locally — these are
phonons. In a quasicrystal, there is an additional degree of freedom: the **phason**.

A phason corresponds to shifting the acceptance window W in internal space. This
flips some boundary tiles (tiles near the window boundary jump from inside to outside
or vice versa), creating local rearrangements.

Physical effect: phason fluctuations cause:
- Anisotropic broadening of diffraction peaks (phason Debye-Waller factor)
- Diffuse streaks or halos around the sharp peaks
- The broadening is LINEAR in peak index (unlike thermal broadening which is quadratic)

### Phason Strain
A uniform phason strain corresponds to a linear shift of the window with position:
    x_perp -> x_perp + M * x_par
where M is the phason strain matrix. This produces systematic peak shifts and
intensity changes characteristic of icosahedral quasicrystals.

### Experimental Signature
Real quasicrystals always have some phason disorder (frozen in during quenching).
The diffraction pattern shows:
- Sharp main peaks (from long-range quasiperiodic order)
- Diffuse background (from phason fluctuations)
- Anisotropic peak broadening along specific directions in reciprocal space
- Some peaks more broadened than others depending on their internal-space component
