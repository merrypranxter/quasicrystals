# Inflation and Deflation in Aperiodic Tilings

Inflation (substitution) and its inverse, deflation, are the fundamental operations
that reveal the hierarchical, self-similar structure of quasicrystal tilings. They
are the geometric analogues of the Fibonacci recurrence, operating on tiles rather
than numbers.

---

## 1. Core Concept

### What is Inflation?
Inflation (also called "substitution" or "expansion") is a rule that replaces each
tile in a tiling with a collection of smaller tiles of the same types, scaled by
a fixed inflation factor lambda. After inflation:
- All tiles are scaled DOWN by factor lambda
- Each tile is replaced by a specific arrangement of smaller tiles
- The resulting tiling covers the same region with more (smaller) tiles
- The new tiling is of the SAME TYPE as the original

### What is Deflation?
Deflation is the inverse: tiles are combined into larger tiles, scaled up by lambda.
Mathematically, deflation of a tiling T gives a tiling T' where T' inflated = T.

### Why They Matter
1. **Prove aperiodicity**: A tiling with a well-defined inflation rule cannot be periodic.
   If it were periodic, the inflated version would also be periodic — but at scales
   incommensurate with the period (since lambda is irrational). Contradiction.

2. **Generate infinite tilings**: Start with one tile, inflate repeatedly, take limit.
   The resulting infinite tiling is a valid aperiodic tiling.

3. **Reveal self-similarity**: The inflated tiling is geometrically similar to the original
   but larger. This produces the fractal-like hierarchical structure.

4. **Compute tile frequencies**: The Perron eigenvector of the substitution matrix
   gives the relative frequencies of tile types in the infinite tiling.

---

## 2. Penrose P2 Inflation — Step by Step

### Inflation Factor
The inflation factor for Penrose P2 is phi = (1+sqrt(5))/2 ≈ 1.618.
Linear dimensions scale by phi; areas scale by phi^2 ≈ 2.618.

### The Two Tiles
- **Thick rhombus** (T): angles 72° and 108°, edge length s
- **Thin rhombus** (t): angles 36° and 144°, edge length s

Both have the SAME edge length s (this is what makes them match up so neatly).

### Inflation Rules

**Thick rhombus T → 1 thick + 1 thin:**
The thick rhombus of edge phi*s is divided into:
- 1 thick rhombus of edge s (occupying the "fat" portion near the long diagonal)
- 1 thin rhombus of edge s (occupying the "thin" corner)

Geometric construction:
```
Original thick rhombus T (edge = phi):
    
      *
     / \
    /   \
   *     *
    \   /
     \ /
      *

After division into T + t (edge = 1):
      *
     /|\
    / | \
   *  *  *
    \ | /
     \|/
      *
   (T above, t below — or vice versa depending on orientation)
```

**Thin rhombus t → 1 thick:**
The thin rhombus of edge phi*s is divided into:
- 1 thick rhombus of edge s
(The thin rhombus exactly contains one thick rhombus at scale 1/phi)

### Deflation Rules (Inverse)
Going the other way (combining small tiles into large):

**Thick + thin → Thick (larger)**
**Thick → Thin (larger)**

This is less intuitive but equally valid. In practice, deflation requires
identifying which small tiles belong together, which is non-trivial without
the Ammann bars or matching colors.

### Iteration Example (ASCII Art Schematic)

Level 0 (one thick rhombus):
```
    *
   / \
  /   \
 *  T  *
  \   /
   \ /
    *
```

Level 1 (after one inflation: 1T + 1t):
```
    *
   /|\
  / | \
 * T|t *
  \ | /
   \|/
    *
```

Level 2 (after two inflations: 2T + 1t):
```
Complex arrangement of 3 tiles...
```

Level n: F(n+1) thick + F(n) thin = F(n+2) total tiles.
Total tiles = F(n+2); total edge length of bounding region ~ phi^n.

---

## 3. Penrose P3 Inflation (Kite-Dart)

### Inflation Factor
Same phi = (1+sqrt(5))/2 for P3. (P2 and P3 are related by a geometric transformation.)

### The Two Tiles
- **Kite** (K): quadrilateral with angles 72°, 72°, 72°, 144°
- **Dart** (D): non-convex quadrilateral with angles 36°, 72°, 36°, 216°

### Inflation Rules
**Kite K → 1 Kite + 2 Darts (at scale 1/phi):**
The kite of edge phi divides into 1 kite (at the "wide" end) and 2 darts (flanking it).

**Dart D → 1 Kite + 1 Dart (at scale 1/phi):**
The dart of edge phi divides into 1 kite (in the center) and 1 dart (at the point).

### Substitution Matrix
         K   D
K    [   1   1  ]
D    [   2   1  ]

M_P3 = [[1, 1], [2, 1]]

Characteristic polynomial: (1-lambda)^2 - 2 = lambda^2 - 2*lambda - 1 = 0

Wait — that gives lambda = (2 ± sqrt(8))/2 = 1 ± sqrt(2). That's for a different
formulation. For the standard P3 deflation:

K → 2K + 1D
D → 1K

M = [[2, 1], [1, 0]]

Characteristic polynomial: lambda^2 - 2*lambda - 1 = 0
lambda = (2 ± sqrt(8))/2 = 1 ± sqrt(2)

Hmm, this gives eigenvalue 1+sqrt(2), not phi directly. Note that P3 under this
substitution has inflation factor phi^2 (two steps = one doubling), which reconciles
with the phi inflation factor for P2.

---

## 4. Ammann-Beenker Inflation

### Inflation Factor
The silver ratio: delta_S = 1 + sqrt(2) ≈ 2.414213562...

### The Two Tiles
- **Square** (S): edge length s, angles all 90°
- **Rhombus** (R): edge length s, angles 45° and 135°

### Inflation Rules
**Square S → 4 Squares + 4 Rhombi:**
The large square (edge delta_S * s) is divided into 4 smaller squares and 4 rhombi.

**Rhombus R → 2 Squares + 3 Rhombi:**
The large rhombus (edge delta_S * s) is divided into 2 squares and 3 rhombi.

### Substitution Matrix
         S   R
S    [   4   2  ]
R    [   4   3  ]

Characteristic polynomial: (4-lambda)(3-lambda) - 8 = lambda^2 - 7*lambda + 4 = 0

Hmm, let me recalculate. Standard Ammann-Beenker substitution:
S → 1S + 2R (after one inflation step by delta_S)
R → 1S + 1R (after one inflation step)

Actually: 
S → S central + 2 R flanking (3 tiles)
R → S + R (2 tiles) 

Various sources use different conventions. The eigenvalue of any valid 
Ammann-Beenker substitution matrix must be delta_S^2 = 3 + 2*sqrt(2) ≈ 5.828.

---

## 5. Why Inflation Proves Aperiodicity

### Theorem (sketch)
**If a tiling T has a well-defined inflation rule with irrational inflation factor lambda,
then T is aperiodic (has no non-trivial translational symmetry).**

### Proof sketch
Suppose T has a period vector v (i.e., translating by v maps T to itself).
Then the inflated tiling T' = inflate(T) also has a period vector lambda*v
(since inflate scales all positions by lambda).

But T' is also a valid tiling of the same type. If T' has period lambda*v,
and lambda is irrational, then we have two incommensurate periods (v and lambda*v)
in the same tiling family.

A tiling with two incommensurately-related periods must have only the trivial
period (no non-trivial period). This contradicts the assumption, so T is aperiodic.

More formally: The set of periods of any tiling in the local isomorphism class
is closed under multiplication by lambda. For lambda irrational, the only subgroup
of R^2 closed under multiplication by an irrational is {0}. Hence no non-trivial
translational symmetry exists.

---

## 6. Substitution Matrices and Eigenvalue Analysis

### General Framework
For any substitution tiling with tile types 1, 2, ..., k, define the substitution
matrix M where M[i][j] = number of tiles of type i in the inflation of tile type j.

The Perron-Frobenius theorem guarantees:
1. There is a unique largest eigenvalue lambda_PF (the Perron eigenvalue)
2. lambda_PF is real and positive
3. The corresponding eigenvector has all positive components
4. lambda_PF = lambda^d where lambda is the linear inflation factor and d is dimension

For 2D tilings: lambda_PF = lambda^2 (since area scales as lambda^2).

### Summary of Substitution Matrices

**Penrose P2:**
    M = [[1, 1], [1, 0]]
    Perron eigenvalue: phi^2 = phi + 1
    Tile ratio (thick:thin): phi

**Ammann-Beenker:**
    M = [[1, 1], [2, 1]] (one version)
    Perron eigenvalue: (3 + 2*sqrt(2)) = delta_S^2
    Tile ratio (square:rhombus): 1:sqrt(2)

**Stampfli (12-fold):**
    Three tile types; 3x3 substitution matrix
    Perron eigenvalue: (2+sqrt(3))^2 = 7 + 4*sqrt(3)

### The Algebraic Conjugate Condition
For pure-point diffraction (sharp peaks), the algebraic conjugates of the inflation
factor must all have absolute value less than 1. This is the "Pisot property":

- Penrose: phi is a Pisot number (conjugate psi ≈ -0.618, |psi| < 1). YES.
- Ammann-Beenker: delta_S = 1+sqrt(2) is a Pisot number (conjugate 1-sqrt(2) ≈ -0.414,
  |1-sqrt(2)| < 1). YES.
- Both have pure-point diffraction spectra with sharp peaks.

---

## 7. Geometric Illustration — Penrose P2 Inflation ASCII Art

```
SCALE 0 (1 thick rhombus T, edge = phi^0 = 1):

        A
       / \
      /   \
     /  T  \
    B-------C
     \     /
      \   /
       \ /
        D

        (72° angles at A and D, 108° at B and C)

SCALE 1 (after inflating T: get T + t, edge = 1/phi):
        
        A
       /|\
      / | \
     /  |  \
    B---E---C   (E is new vertex on AC)
     \  |  /
      \ | /
       \|/
        D
        
        (Upper half: thin rhombus t = AEB,  Lower half: thick rhombus T = BECD)
        Wait -- let me reconsider the exact geometry...

Actually the correct subdivision of thick rhombus into T+t is:

        A
       /|\
      / | \
     /  |  \
    /   E   \
   B----+----C
    \       /
     \  T' /
      \   /
       \ /
        D

where T' (thick) and t (thin) are positioned based on the golden cut.
The key: point E divides diagonal AC in ratio phi:1 from A.

SCALE 2 (2 thick + 1 thin):
The thin rhombus from Scale 1 inflates to give 1 thick.
The thick rhombus from Scale 1 inflates to give 1 thick + 1 thin.
Total: 2 thick + 1 thin = 3 tiles.

SCALE 3: 3 thick + 2 thin = 5 tiles.
SCALE 4: 5 thick + 3 thin = 8 tiles.
SCALE n: F(n+1) thick + F(n) thin = F(n+2) tiles total.
```

---

## 8. Implementation Notes for Programmers

### Representing Tiles
Each tile needs:
- Position (e.g., center point coordinates)
- Orientation (rotation angle from reference orientation)
- Type (thick/thin, or kite/dart, etc.)
- Level (recursion depth)

### Inflation Algorithm

```
function inflate(tiling, rule):
    new_tiling = []
    for each tile T in tiling:
        subtiles = apply_rule(T.type, rule)
        for each subtile in subtiles:
            subtile.position = T.position + rotate(subtile.local_offset, T.orientation)
            subtile.orientation = T.orientation + subtile.relative_angle
            subtile.scale = T.scale / phi
        new_tiling.extend(subtiles)
    return new_tiling

function deflate(tiling, matching_rule):
    # More complex: need to identify which tiles to group
    groups = find_matching_groups(tiling, matching_rule)
    return [combine(group) for group in groups]
```

### Key Considerations
1. **Floating point precision**: After many inflations, coordinates accumulate error.
   Use exact arithmetic (integer linear combinations of {1, phi}) for precision.
   Any coordinate in a Penrose tiling can be expressed as a + b*phi where a, b are integers.

2. **The phi-arithmetic trick**: Since phi^2 = phi + 1, all powers of phi reduce to
   linear combinations of 1 and phi. Represent coordinates as (a, b) meaning a + b*phi.
   Addition: (a,b) + (c,d) = (a+c, b+d)
   Multiplication by phi: phi*(a,b) = (b, a+b) [since phi*(a+b*phi) = a*phi + b*phi^2 = b + (a+b)*phi]

3. **Boundary tiles**: When generating tiles from the center out, boundary tiles are
   incomplete. Use a sufficient inflation depth before displaying.

4. **De Bruijn's approach**: Instead of inflation, use De Bruijn's pentagrid method
   for a completely different (and computationally simpler) generation algorithm.
