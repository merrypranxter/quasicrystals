# Theory of Aperiodic Order

Aperiodic order is a mathematical framework that captures the structure of quasicrystals:
systems that are ordered (have long-range correlations) but not periodic (have no
translational symmetry). This field, developed largely after the 1984 discovery of
quasicrystals, bridges crystallography, dynamical systems, and harmonic analysis.

## 1. Definition of Aperiodic

A tiling or point set Lambda in R^d is **aperiodic** if it has no non-trivial translation
symmetry: there is no non-zero vector v such that Lambda + v = Lambda.

Note: "Aperiodic" is sometimes used loosely to mean "non-periodic," but in tiling theory
it specifically means a set of tile shapes that can ONLY tile aperiodically — any tiling
by those shapes is aperiodic. The Penrose tiles are aperiodic in this sense.

## 2. Delone Sets

A point set Lambda in R^d is a **Delone set** (named for Boris Delaunay/Delone) if:
- **Uniformly discrete**: there exists r > 0 such that every ball of radius r contains
  at most one point of Lambda. (No two points are too close.)
- **Relatively dense**: there exists R > 0 such that every ball of radius R contains
  at least one point of Lambda. (No large empty regions.)

Quasicrystal point sets are Delone sets. This captures the physical reality that atoms
have finite size (uniform discreteness) and fill space (relative density).

Parameters:
- r = packing radius (half the minimum inter-point distance)
- R = covering radius (maximum distance from any point to the nearest lattice point)
- Ratio R/r is a measure of "how crystal-like" the set is

## 3. Repetitivity

A Delone set Lambda is **repetitive** if for every finite patch P in Lambda (a finite
subset within a ball), there exists R_P such that every ball of radius R_P contains a
translated copy of P as a sub-pattern of Lambda.

In other words: every finite pattern appears throughout the tiling, with bounded gaps
between occurrences. Penrose tilings are repetitive.

Physical meaning: any local neighborhood you observe in a quasicrystal appears
infinitely often elsewhere in the structure. This is a form of long-range order.

## 4. Local Isomorphism Classes

Two tilings T1 and T2 are **locally isomorphic** (LI) if every finite patch of T1
appears (up to translation) in T2, and vice versa. This is an equivalence relation.

Key theorem: All Penrose tilings (of each type P2 or P3) form a single local
isomorphism class. This means:
- Any two Penrose P2 tilings contain exactly the same set of local patterns
- They cannot be distinguished by any local measurement
- They differ only "globally" — in the arrangement at the very largest scales

This is analogous to the ergodic theory fact that all typical realizations of an
ergodic process are indistinguishable locally. The LI class is the quasicrystal analogue
of the "phase" in statistical mechanics.

## 5. Complexity Function

For a 1D quasicrystal (or word) w, the **complexity function** p(n) counts the number
of distinct subwords of length n.

- For a periodic word with period k: p(n) = k for all n >= some n_0 (bounded)
- For a Sturmian word (e.g., Fibonacci word): p(n) = n + 1 for all n >= 1 (linear)
- For a "random" word: p(n) = 2^n (exponential)

The Fibonacci word achieves the MINIMUM complexity for an aperiodic word: p(n) = n+1.
This is the hallmark of "minimal complexity aperiodic order" — Sturmian sequences.

For 2D tilings, the analogous complexity counts distinct "patches" of radius n.
Penrose tilings have polynomial complexity growth, far below the exponential
complexity of random patterns.

## 6. Pure Point vs Absolutely Continuous Spectrum

The diffraction spectrum (Fourier transform of the autocorrelation) of a point set
decomposes as:
    mu = mu_pp + mu_ac + mu_sc

- **Pure point (pp)**: delta-function peaks at specific frequencies → long-range order
- **Absolutely continuous (ac)**: diffuse background → disordered/liquid-like contribution
- **Singular continuous (sc)**: fractal-type spectrum → very rare, intermediate case

Crystals: mu = mu_pp only (sharp Bragg peaks, no diffuse scattering)
Quasicrystals: mu = mu_pp (dominant) + possibly some mu_ac (phason disorder)
Amorphous/glass: mu = mu_ac (broad humps, no sharp peaks)
Fibonacci-like with special parameters: can have mu_sc (fractal spectrum)

Quasicrystals with Pisot inflation factors (like Penrose phi, Ammann delta_S)
have **pure point diffraction spectrum** — all their "disorder" is pure-point order.

## 7. Meyer Sets

A Delone set Lambda is a **Meyer set** if Lambda - Lambda = {x - y : x,y in Lambda}
is also a Delone set (in particular, is uniformly discrete).

Equivalently: Lambda is a Meyer set iff it is a subset of a mathematical quasicrystal
(cut-and-project set with suitable window).

Meyer sets are the "most ordered" Delone sets short of lattices. All quasicrystal
structures observed in nature correspond to Meyer sets (or close approximations).

Properties of Meyer sets:
- They have "almost periods": for any epsilon > 0, there are many vectors t such that
  Lambda and Lambda + t agree up to epsilon-small displacements on most points
- Their diffraction is pure-point (for appropriate definitions)
- They are exactly the Delone sets for which the almost-lattice structure is preserved

## 8. Diffraction Spectrum — Sharp Peaks from Aperiodic Order

The existence of sharp diffraction peaks despite aperiodicity is the defining
experimental signature of quasicrystals. The mathematical explanation:

Sharp peaks arise because the autocorrelation measure gamma of the point set Lambda
has a non-trivial pure-point component in its Fourier transform (diffraction measure).

For a cut-and-project set Lambda:
    autocorrelation gamma = lim_{R->inf} (1/vol(B_R)) * sum_{x,y in Lambda, |x|,|y|<R} delta_{x-y}

The Fourier transform of gamma (= the diffraction measure) is:
    diffraction = sum_{k in L*_par} |FT[W](k_perp)|^2 * delta_k

where L* is the reciprocal lattice, k_par is the physical component, k_perp is
the internal component, and FT[W] is the Fourier transform of the window W.

Since FT[W] is non-zero on a dense set (W has positive measure), the diffraction
measure is a dense set of sharp delta functions — exactly what is observed!

## 9. Connection to Ergodic Theory

The hull (or "tiling space") of a Penrose tiling is the completion (under a suitable
metric) of the set of all tilings locally isomorphic to a given Penrose tiling.
This is a compact topological space Omega.

The group R^2 acts on Omega by translation. This action is:
- Minimal (every orbit is dense) — corresponds to repetitivity
- Uniquely ergodic (there is a unique invariant probability measure) — corresponds to
  unique tile frequencies

The unique ergodic measure on Omega corresponds to the relative frequencies of tile
types (ratio phi for thick:thin in Penrose P2), which are therefore uniquely determined
and cannot depend on the specific Penrose tiling chosen.

This ergodic framework provides the most rigorous foundation for quasicrystal mathematics
and connects to Connes' noncommutative geometry, K-theory of C*-algebras, and other
modern mathematical physics.
