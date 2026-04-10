# Penrose P2 Tiling (Rhombus Tiling)

**Also known as:** Penrose rhombus tiling, Penrose R tiling, de Bruijn pentagrid tiling  
**Symmetry:** 5-fold (pentagonal), locally C₅ᵥ  
**Inflation ratio:** φ = (1+√5)/2 ≈ 1.6180339887498948482  
**Tile types:** 2 (thick rhombus, thin rhombus)  
**Shader reference:** `shaders/penrose_p2_tiling.glsl`

---

## Definition

The Penrose P2 tiling is a covering of the infinite plane by two types of rhombus — the **thick rhombus** (sometimes called the "fat rhombus" or "wide rhombus") and the **thin rhombus** (also "skinny rhombus" or "acute rhombus") — that tiles aperiodically when edge-matching rules are observed. The tiling exhibits 5-fold rotational symmetry locally and globally at special centers, but has no translational symmetry: no shift of the pattern maps it onto itself.

The P2 tiling is one of three equivalent forms of Penrose tiling; it is related to the **P3 (kite-dart)** tiling by a deflation/inflation procedure and to the **P1 (pentagonal)** tiling by a more complex substitution. All three tile the plane with the same statistical properties.

---

## Tile Specifications

### Thick Rhombus (Wide Rhombus)

| Property | Value |
|----------|-------|
| Acute angle α | 72° (= 2π/5) |
| Obtuse angle β | 108° (= 3π/5) |
| Side length (normalized) | 1 |
| Short diagonal | 2·sin(36°) ≈ 2 × 0.58779 = **1.17557** |
| Long diagonal | 2·sin(72°) ≈ 2 × 0.95106 = **1.90211** |
| Diagonal ratio (long/short) | φ = 1.6180339887... |
| Area | sin(72°) ≈ **0.95106** |
| GLSL color suggestion | gold `#FFD700` or warm ochre |

The thick rhombus has acute angles at two opposite vertices (72° each) and obtuse angles at the other two (108° each). It appears sunflower-like in clusters. The ratio of the long diagonal to the short diagonal equals exactly **φ** — the golden ratio — a fundamental geometric relationship that permeates the entire tiling.

### Thin Rhombus (Skinny Rhombus)

| Property | Value |
|----------|-------|
| Acute angle α | 36° (= π/5) |
| Obtuse angle β | 144° (= 4π/5) |
| Side length (normalized) | 1 |
| Short diagonal | 2·sin(18°) ≈ 2 × 0.30902 = **0.61803** = 1/φ |
| Long diagonal | 2·sin(72°) ≈ **1.90211** |
| Diagonal ratio (long/short) | φ² = 2.6180339... |
| Area | sin(36°) ≈ **0.58779** |
| GLSL color suggestion | silver `#C0C0C0` or cool grey |

The thin rhombus has acute angles of 36° — so narrow it can look nearly needle-like in complex tilings. Note that its short diagonal equals **1/φ = φ - 1 ≈ 0.61803**, directly connecting to the Fibonacci/golden ratio chain.

### Area and Frequency Ratio

The ratio of thick to thin tiles in any infinite Penrose P2 tiling approaches **φ²:1 = (φ+1):1 = 2.6180...:1** as the tiling grows. Equivalently:

```
N(thick) / N(thin) → φ² ≈ 2.618034...
```

This means approximately 72.36% of tiles are thick and 27.64% are thin (since φ²/(φ²+1) = φ²/φ³ = 1/φ).

The total area covered by thick vs. thin tiles approaches ratio:
```
Area(thick) / Area(thin) → φ² × (sin 72° / sin 36°) = φ² × φ = φ³ ≈ 4.236...
```

---

## Symmetry and Structure

### Rotational Symmetry
- **Local 5-fold centers** appear throughout the tiling — neighborhoods of "sun" or "star" configurations that exhibit local C₅ symmetry
- **No global translational symmetry** — no vector **v** maps the tiling to itself
- **Statistical rotational symmetry**: averaged over large patches, all 5 orientations appear with equal frequency

### The 5 Tile Orientations
In any Penrose P2 tiling, each tile type appears in exactly **5 distinct orientations**, separated by 72° rotations. The orientations of thick and thin rhombi are:
- Thick: 0°, 72°, 144°, 216°, 288°
- Thin: 36°, 108°, 180°, 252°, 324°
(or offset by some global rotation)

---

## Vertex Configurations

Seven distinct types of vertex configurations (vertex stars) appear in the P2 tiling. These are the only configurations compatible with the matching rules:

| Name | Description | Tiles at vertex | Angle sum |
|------|-------------|-----------------|-----------|
| **Sun** | 5 thick rhombi, acute vertices | 5 × 72° = 360° | 5 thick acute |
| **Star** | 5 thin rhombi, acute vertices | 5 × 72° = 360° | 5 thin acute |
| **Ace** | 1 thin + 2 thick rhombi | 36° + 2×72° + ... | mixed |
| **Deuce** | 2 thin + 2 thick | mixed arrangement | mixed |
| **Jack** | 3 thick + ... | mixed | mixed |
| **Queen** | 2 thick + 2 thin | mixed | mixed |
| **King** | 2 thick + 3 thin | 2×72° + 3×36° = 360° | mixed |

The **Sun** vertex (five thick rhombi meeting at acute angles) is the most visually striking and appears in roughly 1 in φ⁴ ≈ 6.85... vertices.

The **Star** vertex (five thin rhombi, creating a 5-pointed star pattern) is equally iconic and appears at the same frequency as Sun by symmetry.

---

## Matching Rules (Arrow Decorations)

To prevent periodic tilings, edge-matching rules must be enforced. In the P2 tiling, each edge carries an **arrow** (direction indicator). The rule is:

> **Arrows on shared edges between adjacent tiles must point in the same direction.**

This can be implemented by:
- Marking edges with single or double arrowheads
- Using colored edge segments (two colors, each directed)
- Physical bumps and notches (as in some 3D physical tile sets)

The matching rules are **local**: only neighboring tiles need to be checked. Yet these local constraints enforce global aperiodicity — no arrangement satisfying all matching rules can be periodic.

Without matching rules, it is possible to tile periodically with the two rhombus shapes (they can form a parallelogram periodic tiling). The matching rules are essential to the aperiodicity.

---

## Inflation Rules (Substitution System)

The P2 tiling has a self-similar structure described by inflation rules. Starting from a tiling at scale 1, scale up by factor **φ** and subdivide each tile:

### Thick Rhombus Inflation
One thick rhombus at scale φ decomposes into:
- **1 thick rhombus** (at scale 1) at the "wide" end
- **2 thin rhombi** (at scale 1) flanking the center

In matrix/vector notation, if T = thick count and t = thin count:
```
T' = T + t      (each old thick → 1 thick + pieces from thin)
t' = 2T + t     (after full substitution)
```

### Thin Rhombus Inflation
One thin rhombus at scale φ decomposes into:
- **1 thick rhombus** (at scale 1)
- **1 thin rhombus** (at scale 1)

### Substitution Matrix
The substitution matrix **M** for (thick, thin) counts:
```
M = | 1  1 |
    | 2  1 |
```
The eigenvalues of M are φ² and -φ⁻² (where φ² ≈ 2.618), confirming that after n inflation steps, tile counts grow as φ²ⁿ, and the ratio T/t → φ².

### Inflation Sequence Example
Starting with 1 thick tile:
- Step 0: T=1, t=0
- Step 1: T=1, t=2
- Step 2: T=3, t=4
- Step 3: T=7, t=10
- Step 4: T=17, t=24
- Step 5: T=41, t=58

These follow the Fibonacci-like recurrence, and ratios approach φ²:1.

---

## de Bruijn Pentagrid Construction

The most elegant construction method, due to **N.G. de Bruijn (1981)**, uses a **pentagrid**: five families of parallel lines, each family perpendicular to one of the 5 unit vectors:

```
e_k = (cos(2πk/5), sin(2πk/5)),  k = 0, 1, 2, 3, 4
```

Each family k consists of lines:
```
L_k(n) = { x : x · e_k = n + γ_k },  n ∈ ℤ
```

where γ_k are offset parameters (with constraint Σγ_k = 0 for "standard" tilings).

The intersection of two lines from different families corresponds to a vertex of the Penrose tiling. Each intersection point is labeled by a 5-tuple of integers (k₀, k₁, k₂, k₃, k₄) indicating which "strip" it lies in for each direction. The tile type (thick/thin) and orientation at each intersection are determined combinatorially from the indices.

**Algorithm sketch (GLSL implementable):**
```glsl
float pentagrid_index(vec2 p, int k, float gamma_k) {
    float angle = 2.0 * PI * float(k) / 5.0;
    vec2 ek = vec2(cos(angle), sin(angle));
    return floor(dot(p, ek) - gamma_k);
}
```

For each pixel, compute all 5 pentagrid indices, identify which rhombus the pixel falls in, and color accordingly.

---

## Golden Ratio Relationships

The golden ratio φ permeates the P2 tiling geometry:

| Relationship | Formula | Value |
|---|---|---|
| Thick rhombus diagonal ratio | long/short | φ ≈ 1.618 |
| Thin rhombus short diagonal | 1/φ = φ-1 | ≈ 0.618 |
| Tile frequency ratio | T/t | φ² ≈ 2.618 |
| Inflation scale factor | 1 step | φ ≈ 1.618 |
| n-step inflation scale | φⁿ | varies |
| Area ratio | A(thick)/A(thin) | φ ≈ 1.618 |
| Sun vertex frequency | 1 in N vertices | ~1/φ⁴ |
| Diffraction peak ratio | adjacent peaks | powers of φ |

---

## Relationship to Physical Quasicrystals

The P2 tiling is the 2D analogue of the 3D icosahedral quasicrystals such as Al-Cu-Fe and Al-Pd-Mn. In 3D, the icosahedral tiling uses two types of rhombohedra (oblate and prolate) with 3D golden ratio relationships. The icosahedral quasicrystal is, in a precise mathematical sense, a 3D generalization of the P2 tiling:

- Both have φ-based inflation rules
- Both project from higher-dimensional periodic lattices (Z⁵ for 2D Penrose, Z⁶ for 3D icosahedral)
- Both show diffraction patterns with peaks at φ-spaced irrational positions
- Both have two types of building blocks (rhombi → rhombohedra)

---

## Visual Appearance

The P2 tiling has a distinctive visual character:

- **Sunflower-like patches**: clusters of 5 thick rhombi around a "sun" vertex
- **Star-shaped voids**: 5 thin rhombi around a "star" vertex form a 5-pointed star
- **Long "chains"**: thin rhombi sometimes line up in quasi-linear chains (related to Ammann bars)
- **Hierarchical structure**: zooming out reveals the same patterns at larger scales (φ², φ⁴, ... scales)
- **Radiating spiral arms**: large-scale pinwheel-like spirals visible in big patches
- **No distinguishable "grain boundaries"**: structure is globally coherent

### Suggested Color Schemes

| Color Scheme | Thick Rhombus | Thin Rhombus | Background |
|---|---|---|---|
| Classic gold/silver | `#FFD700` gold | `#C0C0C0` silver | `#1a1a2e` dark blue |
| Warm desert | `#D4813A` ochre | `#8B6914` bronze | `#0D0D0D` black |
| Ice/winter | `#87CEEB` sky blue | `#FFFFFF` white | `#00264D` deep navy |
| Monochrome | `#EEEEEE` light | `#444444` dark | `#000000` black |
| Neon | `#FF6B35` coral | `#00FFB3` mint | `#0A0A0A` near-black |

---

## Creative Applications

### Floor and Wall Tiling
The P2 tiling is perhaps most famous as a floor pattern. The **Oxford University Mathematical Institute** building (designed by Keith Murray, 1966) featured Penrose tiles before Penrose published his results. More famously, **Carleton University** installed a large Penrose P2 floor tiling in 1996. The pattern never repeats but looks ordered — creating a visually rich surface that rewards extended observation.

### Textile Design
The two-rhombus structure translates directly to weaving patterns. The angular geometry is compatible with jacquard weaving, where the limited tile types (only 10 distinct orientations total: 5 per tile type) simplify the threading pattern.

### Architectural Facades
The **Darb-i Imam shrine** in Isfahan, Iran (1453) features a quasi-periodic girih tile pattern that approximates a Penrose-like tiling — evidence that Islamic artisans discovered aspects of quasicrystalline geometry 500 years before Western mathematics. Modern architectural use includes facade panels, perforated screens, and decorative ceiling systems.

### Logo and Graphic Design
The 5-fold symmetry and the distinctive "sun" and "star" motifs create memorable graphic elements. The tiling can be used as:
- Background texture for digital/print media
- Icon framework with 5-fold symmetry
- Sculptural framework (3D-printed Penrose tiles)

---

## Construction Algorithm Summary

### Method 1: Pentagrid (de Bruijn)
1. Define 5 grid families with angle offsets 72°k (k=0..4)
2. For each grid intersection, determine which rhombus it corresponds to
3. Project the 5D index to 2D vertex position

### Method 2: Inflation/Deflation
1. Start with a seed (e.g., one thick rhombus or a "sun" patch)
2. Apply inflation: scale by φ, subdivide each tile per rules above
3. Repeat for desired resolution

### Method 3: Direct GLSL (Fragment Shader)
See `shaders/penrose_p2_tiling.glsl` for a complete WebGL/Shadertoy implementation using the pentagrid method, optimized for real-time rendering.

---

## References

- Penrose, R. (1974). "The role of aesthetics in pure and applied mathematical research." *Bull. Inst. Math. Appl.* 10: 266–271.
- de Bruijn, N.G. (1981). "Algebraic theory of Penrose's non-periodic tilings of the plane." *Proc. Kon. Ned. Akad. Wetensch.* A84(1): 39–66.
- Grünbaum, B.; Shephard, G.C. (1987). *Tilings and Patterns*. W.H. Freeman. Chapter 10.
- Gardner, M. (1977). "Extraordinary nonperiodic tiling that enriches the theory of tiles." *Scientific American* 236(1): 110–121.
- Senechal, M. (1995). *Quasicrystals and Geometry*. Cambridge. pp. 160–210.

**See also:** [`02_penrose_p3.md`](02_penrose_p3.md) | [`master_index.md`](master_index.md) | [`../quasicrystals_database.json`](../quasicrystals_database.json)
