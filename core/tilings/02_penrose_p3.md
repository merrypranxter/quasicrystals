# Penrose P3 Tiling (Kite and Dart)

**Also known as:** Penrose kite-dart tiling, Penrose KD tiling  
**Symmetry:** 5-fold (pentagonal), locally C₅ᵥ  
**Inflation ratio:** φ = (1+√5)/2 ≈ 1.6180339887498948482  
**Tile types:** 2 (kite, dart)  
**Relationship to P2:** Dual/related via deflation; topologically equivalent tiling family

---

## Definition

The Penrose P3 tiling uses two quadrilateral tiles — the **kite** and the **dart** — to cover the infinite plane aperiodically. Both shapes are derived from the golden gnomon and the golden triangle (the 36-72-72° and 36-36-108° isosceles triangles that appear in the regular pentagon). The tiles interlock with bumps and notches (matching rules) that prevent any periodic arrangement.

Like the P2 (rhombus) tiling, the P3 tiling exhibits 5-fold rotational symmetry at special points, has inflation ratio φ, and projects from a 5D periodic lattice. The two tilings are **mutually locally derivable (MLD)** — any sufficiently large patch of one determines the other uniquely. However, they are not identical: the P3 tiling has a more organic, flowing appearance compared to the angular P2 rhombus pattern.

---

## Tile Specifications

Both tiles have all sides of **equal length** (normalized to 1). They are **not** parallelograms — they have two axes of mirror symmetry, unlike the rhombi of P2.

### The Kite

The kite is a convex quadrilateral with bilateral symmetry:

| Property | Value |
|----------|-------|
| Shape | Convex quadrilateral, bilaterally symmetric |
| Top angle (apex) | **72°** |
| Left side angle | **72°** |
| Right side angle | **72°** |
| Bottom angle (base) | **144°** |
| Angle sum | 72° + 72° + 72° + 144° = **360°** ✓ |
| Side length (all equal) | 1 |
| Longer diagonal | φ (connecting apex to base) |
| Shorter diagonal | 1 (connecting side vertices) |
| Area | (φ/2)·sin(72°) + (1/2)·... = **(φ·sin72°)/2** ≈ **0.9755** |
| GLSL color suggestion | warm gold `#E8B84B` |

The kite has a distinctive "kite" shape: broad at the sides, narrower at top and bottom. The top vertex has angle 72°, the two side vertices each 72°, and the bottom vertex 144°. It is the broader of the two P3 tiles.

> **Note on angle sum:** For any quadrilateral, interior angles sum to 360°. Kite: 72+72+72+144 = 360° ✓. Dart: see below.

### The Dart

The dart (also called "arrowhead") is a non-convex quadrilateral — it has one reflex-like concavity at the base:

| Property | Value |
|----------|-------|
| Shape | Non-convex quadrilateral, bilaterally symmetric |
| Top angle (apex) | **36°** |
| Left side angle | **72°** |
| Right side angle | **72°** |
| Bottom angle (base notch) | **216°** |
| Angle sum | 36° + 72° + 72° + 180° = **360°** ✓ (see note) |

> **Note on the dart's base angle:** The dart is a non-convex quadrilateral. The two 72° side angles and 36° apex account for 180°. For the interior angle sum of any quadrilateral to equal 360°, the base (notch) interior angle = 360° − 36° − 72° − 72° = **180°**. However, measured from inside the concave notch, the dart's base vertex is often described as a **reflex angle of 216°** in specialized literature (measuring the larger interior arc), while the complementary 144° or 180° are used depending on convention. Geometrically, the dart is composed of two golden gnomons (36-36-108° isosceles triangles) sharing their long edges.

> **Standard description:** The dart has angles: apex 36°, each wing 72°, and the concave base is the reflex vertex (216° measured through the tile's interior concavity). When tiled, the concave base faces other tile boundaries. The polygon's signed angle sum = 360° as required for any simple polygon.

| Property | Value |
|----------|-------|
| Side length (all equal) | 1 |
| Longer diagonal | 1 (connects wings) |
| Shorter diagonal | 1/φ ≈ 0.618 |
| Area | sin(36°)/φ ≈ **0.3633** |
| GLSL color suggestion | cool silver `#9BB7D4` |

The dart is the narrower, arrow-like tile. Its concave base notch interlocks with the kite's broader base, forming the distinctive "bat" or "butterfly" shape when two darts join.

### Tile Frequency Ratio
In any infinite P3 tiling:
```
N(kites) / N(darts) → φ² ≈ 2.61803...
```
The same ratio as thick:thin rhombi in P2 — this is expected since P2 and P3 are equivalent tilings.

---

## Relationship to Regular Pentagons and Golden Triangles

The kite and dart derive from two fundamental golden triangles:

### Golden Gnomon (Obtuse golden triangle)
- Isosceles triangle with apex angle **36°** and base angles **72°** each
- Ratio of leg to base = φ
- **Two gnomons → one dart** (by joining along the equal sides)

### Golden Triangle (Acute golden triangle)
- Isosceles triangle with apex angle **108°** and base angles **36°** each
- Ratio of leg to base = φ
- **One kite = two golden triangles** (joined at their bases)

This decomposition into triangles is key to the inflation procedure.

---

## Symmetry

### Global Symmetry
- No translational symmetry
- 5-fold rotational symmetry at "Sun" and "Star" centers
- Mirror symmetry lines radiate from these centers

### Orientations
Each tile type (kite and dart) appears in **5 orientations** (rotated by multiples of 72°). The kite orientations are offset by 36° from the dart orientations, just as thick and thin rhombi are offset in P2.

---

## Vertex Configurations

The P3 tiling admits the same **7 vertex configurations** as P2 (they are equivalent tilings), but the shapes are named differently:

| Name | Tiles meeting | Description |
|------|---------------|-------------|
| **Sun** | 5 kites (apex meeting) | 5 kite tops meeting at a point — 5 × 72° = 360° |
| **Star** | 5 darts (apex meeting) | 5 dart tips meeting — 5 × 72° = 360° |
| **Ace** | 2 kites + 1 dart | 2×72° + 1×216°? asymmetric |
| **Deuce** | 2 darts + 1 kite | forms a "butterfly" |
| **Jack** | 1 kite + ... | mixed |
| **Queen** | 2 kites + 2 darts | symmetric arrangement |
| **King** | 2 darts + 3 kites | large cluster |

The **Sun** configuration — five kites meeting at their 72° apex vertices — is the most iconic, creating a perfect 5-fold star flower. The **Star** configuration — five darts with their 36° apices meeting — creates a 5-pointed star shape.

---

## Matching Rules (Bumps and Notches)

The P3 tiling's matching rules are enforced by the physical shape of the tiles: the **kite's base is convex** and the **dart's base is concave**, so they physically interlock. This is a significant advantage over the P2 rhombus tiling (where matching rules must be explicitly marked with arrows): the kite-dart pair can be manufactured as physical tiles that **automatically** enforce the matching rules through their shape.

Additionally:
- Each tile has an arc marking (painted stripe) in the original Penrose design
- **Short arcs** on the dart and **long arcs** on the kite must form continuous curves across tile boundaries
- These arc continuity conditions uniquely determine valid tilings

---

## Inflation Rules

### Kite Inflation
One kite at scale φ decomposes into:
- **1 kite** (at scale 1) near the apex
- **2 half-darts** → effectively **1 dart** (at scale 1) near the base

```
Kite → 1 kite + 1 dart  (after φ-scaling)
```

### Dart Inflation
One dart at scale φ decomposes into:
- **1 kite** (at scale 1)
- **1 half-dart** pair → **1 dart** (at scale 1)

```
Dart → 1 kite + 1 dart  (hmm, need to be careful about half-tiles)
```

More precisely, the inflation uses half-kites and half-darts (golden triangles):

**Half-kite inflation:**  H_K → H_K + H_D (where H = half-tile)
**Half-dart inflation:**  H_D → H_K

Written as full tile substitution:
```
K → K + D   (one kite becomes one kite + one dart)
D → K       (one dart becomes one kite)
```

Substitution matrix:
```
M = | 1  1 |
    | 1  0 |
```
Eigenvalues: φ and -1/φ. The ratio K/D → φ after many iterations. ✓

### Fibonacci Connection
Starting from 1 kite: K=1, D=0
- Step 1: K=1, D=1
- Step 2: K=2, D=1
- Step 3: K=3, D=2
- Step 4: K=5, D=3
- Step 5: K=8, D=5

These are Fibonacci numbers! K(n) = F(n+2), D(n) = F(n+1) approximately. This is the clearest demonstration of the Fibonacci/golden-ratio structure of Penrose tilings.

---

## Conway Worms (Cartwheel Structure)

**John Conway** described a remarkable global structure of Penrose tilings:

**Conway worms** are infinite chains of kites and darts that meander through the tiling. They are created by following the "river" patterns formed by specific tile edges. These worms:
- Never close on themselves
- Divide the plane into two half-planes
- Meander in a quasiperiodic fashion
- Have a 1:1 correspondence with Ammann bars

**The Cartwheel:** Conway's term for the global structure. Every point in a Penrose tiling lies in a "cartwheel" — a nested hierarchy of decagonal regions where the local environment is visible. This is equivalent to the self-similar hierarchical structure.

---

## Conway's Classification: Composition and Decomposition

Conway proposed the terms:
- **Composition**: combining small tiles into larger tiles (= deflation of scale)
- **Decomposition**: splitting larger tiles into smaller ones (= inflation of scale)

The kite-dart tiling admits both operations, creating a self-similar hierarchy of tilings at scales φ, φ², φ³, ... — all mutually locally derivable, all equivalent tilings.

---

## Famous Penrose Installations

### Kite-Dart Floors and Patterns
1. **Magdalen College, Oxford** (the Mathematical Institute building): Large P3 floor tiling
2. **Texas A&M University**: Penrose tiling in a corridor floor
3. **San Francisco City Hall**: Geometric floor with approximate Penrose-like patterns

### The Penrose vs. Kimberly-Clark Patent Dispute
In 1997, Roger Penrose successfully sued **Kimberly-Clark** (makers of Kleenex) for producing toilet paper with a Penrose-like quasicrystalline embossed pattern. The pattern used two diamond shapes (thick and thin rhombi) in an aperiodic arrangement. Penrose held a patent on aperiodic tilings, and the dispute was settled.

### Penrose's Bat Signal
The 5-fold pattern produced by five darts meeting at their acute angles creates a shape sometimes called the "bat" or "bat signal" — a bilinear motif that appears repeatedly throughout the tiling.

---

## Relationship to P2 (Rhombus Tiling)

The P3 (kite-dart) and P2 (rhombus) tilings are related by a **deflation** procedure:

Every P3 tiling can be converted to a P2 tiling by:
1. Splitting each kite along its shorter diagonal → two golden triangles
2. Regrouping adjacent golden triangles into thick and thin rhombi

And vice versa: each P2 tiling → P3 by:
1. Splitting each rhombus along one diagonal
2. Regrouping half-tiles into kites and darts

This means the tilings are **mutually locally derivable**: local information (what tiles appear in a bounded region) of one tiling determines the other.

---

## Physical Applications and Analogies

### Crystal Analogy
The kite-dart geometry is analogous to the local atom cluster arrangements in icosahedral quasicrystals:
- Kite-like clusters of atoms (Bergman cluster)
- Dart-like connecting units

In the Al-Pd-Mn icosahedral quasicrystal, electron density maps reveal pseudo-pentagonal clusters that correspond topologically to Penrose tiles.

### Molecular Motors
Conway and Radin noted that Penrose-like aperiodic order could explain certain properties of biological molecular machines where parts must fit together without repeating. The kite-dart's non-repeating fit is analogous to allosteric protein conformations.

---

## GLSL Implementation Notes

```glsl
// P3 Kite-Dart via triangle decomposition
// Split each tile into golden triangles, then shade by triangle type

const float PHI = 1.6180339887498948482;
const float PI5 = 3.14159265358979 / 5.0;  // 36 degrees

// Golden triangle type A (kite half): apex angle 36°, legs = PHI * base
// Golden triangle type B (dart half): apex angle 108°, legs = base * PHI

// Use the de Bruijn pentagrid, then map to kite-dart via diagonal choice
```

See `shaders/penrose_p3_kite_dart.glsl` for complete implementation.

---

## References

- Penrose, R. (1978). "Pentaplexity: A class of non-periodic tilings of the plane." *Eureka* 39: 16–22.
- Gardner, M. (1977). "Mathematical games: Extraordinary nonperiodic tiling." *Scientific American* 236(1): 110–121.
- Grünbaum, B.; Shephard, G.C. (1987). *Tilings and Patterns*. W.H. Freeman.
- Senechal, M. (1995). *Quasicrystals and Geometry*. Cambridge. Chapter 5.
- Socolar, J.E.S.; Steinhardt, P.J. (1986). "Quasicrystals. II. Unit-cell configurations." *Phys. Rev. B* 34(2): 617–647.

**See also:** [`01_penrose_p2.md`](01_penrose_p2.md) | [`master_index.md`](master_index.md) | [`../quasicrystals_database.json`](../quasicrystals_database.json)
