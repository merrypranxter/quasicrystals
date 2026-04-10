# Stampfli Tiling (Dodecagonal / 12-Fold Tiling)

**Proper name:** Stampfli tiling (also called **Shield tiling** or **12-fold tiling**)  
**Common alias:** "stampot" in some generative art communities  
**Discoverer:** Peter Stampfli (1986)  
**Symmetry:** 12-fold (dodecagonal), D₁₂ locally  
**Inflation ratio:** 2 + √3 ≈ **3.73205080756887729353**  
**Tile types:** 3 (equilateral triangle, square, regular hexagon) — or simplified to 2  
**Shader reference:** `shaders/stampfli_12fold.glsl`

---

## Definition

The Stampfli tiling is a quasiperiodic covering of the plane exhibiting **12-fold (dodecagonal) rotational symmetry**. It uses three regular polygon tiles — **equilateral triangles**, **squares**, and in some formulations **regular hexagons** — arranged with matching rules that prevent any periodic translation. The tiling's name comes from its discoverer Peter Stampfli, who described it in a 1986 paper in *Helvetica Physica Acta*.

The Stampfli tiling is sometimes called the **"Shield tiling"** because of the shield-like hexagonal motifs that appear in it, or simply the **dodecagonal tiling** for its 12-fold symmetry. In generative art communities, the informal name "stampot" (a portmanteau of Stampfli + octagonal/pot) occasionally appears, but **"Stampfli tiling"** is the proper scientific name.

---

## Discoverer

### Peter Stampfli (1986)
Peter Stampfli published the dodecagonal tiling in 1986 in the Swiss physics journal *Helvetica Physica Acta*, predating several independent rediscoveries. His construction used a recursive (inflation-based) approach: starting from a central 12-gon, triangles and squares fill in the surrounding space, and each iteration reveals the same structure at scale 2 + √3.

The tiling attracted attention because dodecagonal (12-fold) quasicrystals were discovered experimentally in **1987** (Ni-Cr thin films by Ishimasa, Nissen, Fukano), immediately stimulating theoretical interest in the Stampfli tiling as a structural model.

---

## The 12-Fold Inflation Constant

The Stampfli tiling's inflation ratio is:
```
λ = 2 + √3 ≈ 3.73205080756887729353
```

This constant satisfies:
```
λ² - 4λ + 1 = 0
λ = 2 + √3
1/λ = 2 - √3 ≈ 0.26795
```

It is related to 12-fold geometry because the regular 12-gon has diagonal ratios involving 2 + √3. In particular:
```
2·cos(π/12) = √6 + √2 ≈ 3.8637... 
2·cos(π/6) = √3 ≈ 1.7320...
2 + √3 = 1 + 2·cos(30°) + ... 
```

The analogous constants for other symmetries:
- 5-fold (Penrose): φ = (1+√5)/2 ≈ 1.618
- 8-fold (Ammann-Beenker): 1+√2 ≈ 2.414
- 12-fold (Stampfli): 2+√3 ≈ 3.732

The pattern is: for n-fold symmetry, the inflation ratio is `2·cos(π/n)` in some formulations (for n = 5, 8, 12 this gives related but not identical values — the actual inflation ratio depends on the specific tiling construction).

---

## Tile Types

### Simplified (2-Tile) Version
In its most studied form, the Stampfli tiling uses:

**Equilateral Triangle:**
| Property | Value |
|----------|-------|
| All angles | 60° |
| Side length (normalized) | 1 |
| Height | √3/2 ≈ 0.86603 |
| Area | √3/4 ≈ **0.43301** |

**Square:**
| Property | Value |
|----------|-------|
| All angles | 90° |
| Side length (normalized) | 1 |
| Diagonal | √2 ≈ 1.41421 |
| Area | **1.0** |

The equilateral triangle and square combination, when arranged with specific matching rules, generates 12-fold symmetry. The key relationship is that 12·30° = 360°, and the triangle's 60° and square's 90° share the GCD 30°, making 12-fold (= 360°/30°) the natural symmetry.

### Full (3-Tile) Version
The full Stampfli construction sometimes includes a **regular hexagon** (angles 120°, area = 3√3/2 ≈ 2.598) as a third tile type. However, hexagons can be decomposed into two triangles (sharing an edge), so many treatments use only triangles and squares.

### Tile Area Ratios
In an infinite Stampfli tiling:
```
N(triangles) : N(squares) = (2+√3) : 1
```
i.e., for every square there are approximately 3.732 triangles.

---

## 12-Fold Symmetry

12-fold symmetry is special because 12 = 4 × 3 — it combines the symmetry groups of squares (4-fold) and equilateral triangles (3-fold). Equivalently, the regular 12-gon has 12-fold dihedral symmetry, and its vertices are at angles 30°, 60°, 90°, ..., 330°.

**Why 12-fold is "easier" than 5- or 8-fold:**
- The angles 60° (triangle) and 90° (square) are both divisors of 360°/n for n = 12
- This makes the tiling more "grid-like" in appearance
- However, no combination of these tiles tiles periodically with 12-fold symmetry — the inflation constant 2+√3 is irrational, forcing aperiodicity

**The dodecagonal Ammann lines:**
The Stampfli tiling has 6 families of Ammann lines (at 0°, 30°, 60°, 90°, 120°, 150°), compared to Penrose's 5 families and Ammann-Beenker's 4 families. These lines reveal the 12-fold structure.

---

## Connection to Physical Dodecagonal Quasicrystals

### Ni-Cr System (1987)
T. Ishimasa, H.-U. Nissen, and Y. Fukano reported the first dodecagonal quasicrystal in thin films of **Ni-Cr** alloy in 1987 in *Physical Review Letters*. Electron diffraction showed a clear 12-fold symmetric pattern with sharp spots — exactly the pattern predicted by the Stampfli tiling model.

### Ta-Te System
Dodecagonal quasicrystals have also been found in tantalum-telluride (Ta-Te) compounds. The structure consists of layers — within each layer, the arrangement follows the Stampfli tiling; layers stack periodically along the perpendicular axis, making this a "2D quasicrystal + 1D periodic" structure.

### V-Ni-Si and Cr-Ni-Si
Ternary alloy systems based on transition metals show dodecagonal phases. The stability is attributed to electronic structure effects (Hume-Rothery rules applied to quasiperiodic structures).

---

## Mathematical Basis

### Ring of Integers Z[e^(iπ/6)]
The algebraic framework for 12-fold quasicrystals uses the **12th cyclotomic field**:
```
Z[e^(iπ/6)] = Z[ζ₁₂]
```
where ζ₁₂ = e^(iπ/6) = cos(30°) + i·sin(30°). This is the ring of algebraic integers in Q(√3, i), which contains both √3 and i.

Vertex positions in the Stampfli tiling are elements of Z[e^(iπ/6)] restricted to a suitable cut.

### Projection from 4D
The Stampfli tiling can be derived by cutting a 4D lattice with basis vectors at 30°, 60°, 90°, 120° (four of the twelve dodecagonal directions). The acceptance window in internal space is a regular 12-gon.

Equivalently, the tiling is related to the **D₄ root lattice** in 4D.

---

## Vertex Configurations

For the triangle-square Stampfli tiling, vertex configurations must satisfy:
- Angle sum = 360° at each vertex
- Combinations of 60° (triangle) and 90° (square) that sum to 360°

Possible combinations:
```
6 × 60° = 360°  → 6 triangles (all-triangle vertex)
4 × 90° = 360°  → 4 squares (all-square vertex)  
3 × 60° + 2 × 90° = 180° + 180° = 360°  → 3 triangles + 2 squares
2 × 60° + 3 × 90° → 120 + 270 ≠ 360  (invalid)
4 × 60° + 1 × 90° + ... → need to enumerate
```

All valid vertex types for the 12-fold tiling:
| Type | Configuration | Angle check |
|------|---------------|-------------|
| T6 | 6 triangles | 6×60 = 360° ✓ |
| S4 | 4 squares | 4×90 = 360° ✓ |
| T3S2 | 3 tri + 2 sq | 3×60+2×90 = 360° ✓ |
| T4S1 | 4 tri + 1 sq (not always valid) | 240+90 ≠ 360° ✗ |
| T2S2T... | various | check: ≤360° arrangements |

The matching rules of the Stampfli tiling restrict which vertex configurations actually appear.

---

## Inflation Rules

### Triangle Inflation (at scale λ = 2+√3)
One equilateral triangle at scale λ decomposes into:
- (2+√3)² / (√3/4) × (√3/4) triangles ≈ several triangles + squares

More precisely, the substitution (in terms of triangle T and square S):
```
T → (2+√3) scaling:
    contains: 2+√3 ≈ 4 triangles + 1 square per original triangle
S → contains: 4+2√3 ≈ several triangles + squares per original square
```

The precise inflation system (as a substitution matrix):
```
M = | 4  2 |
    | 1  1 |
```
(approximate; exact entries involve √3)

The eigenvalue of M relevant to growth is λ = 2+√3 ≈ 3.732 (confirming the inflation ratio).

---

## Visual Appearance

The Stampfli tiling has a distinctive appearance:

- **12-pointed star motifs**: Central 12-fold stars appear at intervals, surrounded by rings of triangles and squares
- **Shield shapes**: Hexagonal (6-sided) patches from 6 triangles meeting look like shields
- **Square corridors**: Chains of squares run along 4-fold axes
- **More "tiled" feel**: The combination of 60°/90° angles gives it a more familiar mosaic look than Penrose
- **Large-scale self-similarity**: Zooming out by factor λ ≈ 3.732 reveals the same pattern

### Suggested Color Schemes

| Scheme | Triangles | Squares | Notes |
|--------|-----------|---------|-------|
| Islamic | `#008080` teal | `#FFD700` gold | Islamic geometric aesthetic |
| Ceramic | `#FFFFFF` white | `#1E3A5F` dark blue | Portuguese azulejo |
| Minimal | `#E8E8E8` light grey | `#333333` charcoal | Modern minimal |
| Warm mosaic | `#D4956A` terracotta | `#5C8A3C` sage green | Mediterranean |

---

## Relationship to Other Tilings

### vs. Penrose P2 (5-fold)
- Both use 2 tile types with matching rules
- Penrose: φ-based, 5-fold; Stampfli: (2+√3)-based, 12-fold
- Stampfli looks more regular due to right angles

### vs. Ammann-Beenker (8-fold)
- Both use a square as one tile type
- Ammann-Beenker pairs square with 45°-rhombus; Stampfli pairs square with 60°-triangle
- 8-fold vs. 12-fold symmetry

### Relation to Penrose P1 (Pentagonal)
- The Penrose P1 tiling also mixes polygon types (pentagons, stars, boats, diamonds)
- Both tilings involve multiple polygon shapes
- No direct mathematical relationship (different symmetry groups)

---

## GLSL Shader Notes

```glsl
// Stampfli 12-fold tiling
// Key constants
const float LAMBDA = 3.7320508075688772935; // 2 + sqrt(3)
const float INV_LAMBDA = 0.26794919243;      // 2 - sqrt(3)
const float SQRT3 = 1.7320508075688772935;

// 12 direction vectors at 30° spacing
vec2 dir12[12];
for (int k = 0; k < 12; k++) {
    float angle = float(k) * PI / 6.0;  // 30 degree steps
    dir12[k] = vec2(cos(angle), sin(angle));
}

// Identify tile type at each point using 6 grid families
// (directions at 0°, 30°, 60°, 90°, 120°, 150°)
```

See `shaders/stampfli_12fold.glsl` for complete implementation.

---

## References

- Stampfli, P. (1986). "A dodecagonal quasiperiodic lattice in 2 dimensions." *Helvetica Physica Acta* 59: 1260–1263.
- Ishimasa, T.; Nissen, H.-U.; Fukano, Y. (1985). "New ordered state between crystalline and amorphous in Ni-Cr particles." *Physical Review Letters* 55(5): 511–513.
- Socolar, J.E.S. (1989). "Simple octagonal and dodecagonal quasicrystals." *Physical Review B* 39(15): 10519–10551.
- Schlottmann, M. (1993). "Periodic and quasi-periodic Laguerre tilings." *International Journal of Modern Physics B* 7(6–7): 1351–1363.
- Gähler, F. (1988). "Quasicrystal structures from the crystallographic viewpoint." PhD thesis, ETH Zürich.

**See also:** [`03_ammann_beenker.md`](03_ammann_beenker.md) | [`06_pinwheel.md`](06_pinwheel.md) | [`master_index.md`](master_index.md)
