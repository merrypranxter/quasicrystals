# Ammann-Beenker Tiling (Octagonal Tiling)

**Also known as:** Ammann A4 tiling, octagonal tiling, 8-fold quasiperiodic tiling  
**Discoverers:** Robert Ammann (1977), independently F.P.M. Beenker (1982)  
**Symmetry:** 8-fold (octagonal), D₈ locally  
**Inflation ratio:** Silver ratio δ_s = 1 + √2 ≈ **2.41421356237309504880**  
**Tile types:** 2 (square, 45°-rhombus)  
**Shader reference:** `shaders/ammann_beenker.glsl`

---

## Definition

The Ammann-Beenker tiling covers the infinite plane using two tile types — a **square** and a **45° rhombus** (a rhombus with acute angle 45°) — both with equal edge lengths. It is the canonical example of an 8-fold (octagonal) aperiodic tiling, analogous to the 5-fold Penrose tilings. Unlike the Penrose tiling's golden ratio φ = 1.618..., the Ammann-Beenker tiling is governed by the **silver ratio** δ_s = 1 + √2 ≈ 2.41421356.

---

## Discoverers

### Robert Ammann (1946–1994)
Robert Ammann was an American amateur mathematician who worked as a postal sorter. He corresponded extensively with Martin Gardner and later with professional mathematicians, discovering multiple aperiodic tile sets independently. In 1977 he found the octagonal tiling (later called Ammann-Beenker) and also discovered Ammann bars — sets of parallel lines that appear in quasiperiodic tilings. Despite having no formal mathematical training beyond high school, Ammann made contributions recognized as significant by the professional community. He was known for being reclusive and communicating primarily by mail.

### F.P.M. Beenker (1982)
Dutch mathematician F.P.M. Beenker independently discovered the same tiling in 1982 and provided a more formal mathematical treatment. His 1982 technical report from Eindhoven University of Technology gave the tiling its second name and provided the systematic pentagrid-analogous construction (the "octagonal grid" method).

---

## Tile Specifications

### Square Tile

| Property | Value |
|----------|-------|
| Shape | Regular square |
| All angles | 90° |
| Side length (normalized) | 1 |
| Area | **1.0** |
| Diagonals | √2 ≈ 1.41421 |
| GLSL color suggestion | warm white `#F5F5DC` (bisque) |

### Rhombus Tile (45°-Rhombus)

| Property | Value |
|----------|-------|
| Shape | Rhombus with acute angle 45° |
| Acute angles | **45°** |
| Obtuse angles | **135°** |
| Side length (normalized) | 1 |
| Short diagonal | 2·sin(22.5°) ≈ 2 × 0.38268 = **0.76537** |
| Long diagonal | 2·cos(22.5°) ≈ 2 × 0.92388 = **1.84776** |
| Diagonal ratio | long/short = cot(22.5°) = 1 + √2 = δ_s ≈ 2.41421 |
| Area | sin(45°) = √2/2 ≈ **0.70711** |
| GLSL color suggestion | steel blue `#4682B4` |

**Key relationship:** The diagonal ratio of the rhombus equals exactly the silver ratio δ_s = 1 + √2.

### Tile Frequency Ratio
In any infinite Ammann-Beenker tiling:
```
N(squares) / N(rhombi) → δ_s / 2 ... 
```

More precisely, the ratio approaches:
```
N(squares) / N(rhombi) = 1 / √2 ≈ 0.7071
```
(i.e., more rhombi than squares: for every square, there are √2 rhombi)

Area ratio:
```
Area(squares) / Area(rhombi) = 1 / (√2/2) = √2
```

---

## Symmetry Group

- **Local D₈ symmetry**: The tiling has local regions with 8-fold dihedral symmetry
- **No global translational symmetry**: aperiodic
- **Statistical 8-fold symmetry**: all 8 orientations equally represented in the limit
- **Mirror symmetry**: 8 lines of mirror symmetry through 8-fold centers
- **Orientation set**: squares appear in 1 orientation (or 2, for the coloring); rhombi appear in **4 orientations** at 45°, 90°, 135°, 180° (±)

Each rhombus appears at angles:
```
θ = 0°, 45°, 90°, 135°  (and their reflections)
```
Each at two complementary orientations (flipped), giving 8 orientations total.

---

## The Silver Ratio

The **silver ratio** δ_s = 1 + √2 ≈ 2.41421356237309504880 plays the same fundamental role in the Ammann-Beenker tiling as φ plays in Penrose tilings:

| Property | Formula | Value |
|----------|---------|-------|
| Silver ratio | 1 + √2 | 2.41421356... |
| Algebraic equation | δ_s² = 2δ_s + 1 | — |
| Reciprocal | 1/δ_s = δ_s - 2 = √2 - 1 | 0.41421356... |
| Silver ratio squared | δ_s² = 3 + 2√2 | 5.82842712... |
| Pell numbers | 1, 2, 5, 12, 29, 70, 169, ... | consecutive ratio → δ_s |

The Pell sequence P(n+1) = 2·P(n) + P(n-1) is the 8-fold analogue of the Fibonacci sequence, just as δ_s is the 8-fold analogue of φ.

**√2 connection:** Note that √2 = δ_s - 1. The square root of 2 is fundamental to 8-fold geometry (the diagonal of a unit square), and its appearance here is natural: 8-fold symmetry is built on the 45-45-90° triangle, whose ratios involve √2.

---

## Ammann Lines

One of Robert Ammann's key discoveries was that Penrose (and related) tilings contain families of parallel lines — now called **Ammann lines** (or Ammann bars). In the Ammann-Beenker tiling:

- There are **4 families** of Ammann lines (at 0°, 45°, 90°, 135° to the horizontal)
- Each family is a quasiperiodic set of parallel lines with **two spacings**: long (L) and short (S)
- The ratio L:S = √2 (the square root of the silver ratio's reciprocal term)
- The sequence of L and S spacings follows the **Pell word** (8-fold analogue of Fibonacci word)

The Ammann lines are the 2D analogue of crystal lattice planes. Their existence is what makes the tiling "quasicrystalline" rather than merely aperiodic: the Fourier transform of the Ammann line density gives sharp peaks, just like crystal planes give sharp X-ray diffraction peaks.

---

## Vertex Configurations

The Ammann-Beenker tiling has **5 vertex types** (fewer than Penrose P2's 7):

| Vertex Type | Tiles meeting | Total angle | Description |
|-------------|---------------|-------------|-------------|
| **8-fold star** | 8 rhombi | 8 × 45° = 360° | Full octagonal star, the most symmetric |
| **Square + 4 rhombi** | 1 sq + 4 rhombi | 90° + 4×45° = 270°? | Occurs at square-rhombus junctions |
| **2 squares + ... rhombi** | 2 sq + rhombi | ... | Less common |
| **4-fold (squarish)** | 4 squares | 4 × 90° = 360° | Rare but present |
| **Mixed** | various | 360° | Most common in practice |

The 8-rhombus star vertex (8 rhombi meeting at their 45° acute angles) is the visual signature of the Ammann-Beenker tiling — an 8-pointed star far more regular than anything in the Penrose tiling.

---

## Inflation Rules (Substitution System)

### Square Inflation
One square at scale δ_s decomposes into:
- **1 square** (center)
- **4 half-rhombi** → **2 rhombi** (one per pair)
- **4 partial squares** from corners → additional pieces

More precisely:
```
Square → 1 square + 4 rhombi
Rhombus → 2 squares + 3 rhombi
```

Substitution matrix:
```
M = | 1  2 |
    | 4  3 |
```
Eigenvalues: 1 + 2√2 + 2... the relevant eigenvalue is δ_s² ≈ 5.828, confirming inflation by δ_s².

Tile count after n steps (starting from 1 square):
- Step 0: S=1, R=0
- Step 1: S=1, R=4
- Step 2: S=9, R=12
- Step 3: S=33, R=52
- Ratio S/R → 1/√2 ≈ 0.707...

### Visual Effect of Inflation
Each inflation step reveals the same pattern at scale δ_s ≈ 2.414, giving the Ammann-Beenker tiling its self-similar quality. Large-scale patches look like scaled copies of small-scale patches.

---

## Mathematical Basis: Projection from Z⁴

The Ammann-Beenker tiling arises from projection of the **4D integer lattice Z⁴** onto a 2D plane:

**Physical space projection vectors** (the plane E∥):
```
e₁ = (1, 0, 1, 0) / √2  →  2D: (1, 0)
e₂ = (0, 1, 0, 1) / √2  →  2D: (0, 1)
e₃ = (-1, 0, 1, 0) / √2 →  2D: (-1, 0) ... 
```

More precisely, the eight vectors used are:
```
v_k = (cos(kπ/4), sin(kπ/4)),  k = 0, 1, ..., 7
```
and the Z⁴ lattice uses the four independent directions at k = 0, 1, 2, 3 (or equivalently, the basis of Z[i√2], the ring of Gaussian-like integers over √2).

**Internal space** E⊥ is the complementary 2D plane in 4D. The **acceptance window** for the cut-and-project is a regular octagon in E⊥.

The ring **Z[e^(iπ/4)] = Z[√2·i] ≈ Z[1/√2 + i/√2]** — the integers of the 8th cyclotomic field — provides the algebraic framework. Quasicrystal vertex positions are elements of this ring.

---

## Connection to Physical Quasicrystals

### Mn-Si-Al Octagonal Phase
The first octagonal (8-fold) quasicrystal was found in thin films of **Mn-Si** and related alloys in 1987 by Bendersky. This was only the second type of quasicrystal symmetry found (after icosahedral), and confirmed that the icosahedral symmetry of Shechtman's QC was not unique.

### Cr-Ni-Si Octagonal Quasicrystal
Cr-Ni-Si alloys show stable octagonal quasicrystalline phases. The 8-fold diffraction patterns are unmistakably octagonal point symmetry, consistent with the Ammann-Beenker tiling as structural model.

### Structural Model
In the physical octagonal quasicrystals:
- Columns of atoms run along the 8-fold axis (perpendicular to the quasiperiodic plane)
- The in-plane arrangement follows the Ammann-Beenker tiling
- The tile edge length ≈ 0.6–0.8 nm (depends on alloy)

---

## Visual Appearance

The Ammann-Beenker tiling looks distinctly different from Penrose tilings:

- **More regular**: The combination of squares and 45°-rhombi gives a more "grid-like" feel
- **8-pointed star patches**: Large 8-fold star regions are visually prominent
- **Rectangular corridors**: Chains of squares and rhombi form quasi-rectangular corridors
- **Fractal squares**: Large square patterns at scale δ_s appear within the tiling
- **Less organic**: Compared to Penrose, the 90°/45° angles feel more geometric and less naturalistic

### Suggested Color Schemes

| Color Scheme | Square | Rhombus | Background |
|---|---|---|---|
| Steel and gold | `#C0C0C0` silver | `#FFD700` gold | `#1C1C1C` charcoal |
| Arctic | `#F0F8FF` alice blue | `#5B8DB8` steel blue | `#0A1628` dark navy |
| Warm octagon | `#FFF0D4` cream | `#B8860B` dark gold | `#2D1810` dark brown |
| Emerald | `#50C878` emerald | `#006400` dark green | `#001A00` very dark |

---

## GLSL Implementation Sketch

```glsl
// Ammann-Beenker tiling via octagonal grid
// 4 families of grid lines at 0°, 45°, 90°, 135°

const float SILVER = 2.4142135623730950488;  // 1 + sqrt(2)
const float INV_SILVER = 0.4142135623730950; // sqrt(2) - 1

vec2 e[4];  // unit vectors for 4 grid families
for (int k = 0; k < 4; k++) {
    float angle = float(k) * PI / 4.0;  // 0, 45, 90, 135 degrees
    e[k] = vec2(cos(angle), sin(angle));
}

// For pixel at position p, compute grid index in each family
float idx[4];
for (int k = 0; k < 4; k++) {
    idx[k] = floor(dot(p, e[k]) / SILVER);  // scaled grid
}
// Color based on tile type determined from idx
```

See `shaders/ammann_beenker.glsl` for complete fragment shader.

---

## Comparison with Penrose P2

| Property | Penrose P2 | Ammann-Beenker |
|----------|------------|----------------|
| Symmetry fold | 5-fold | 8-fold |
| Tile types | Thick + thin rhombus | Square + 45°-rhombus |
| Tile angles | 72°/108° and 36°/144° | 90° and 45°/135° |
| Inflation ratio | φ = 1.618... | δ_s = 2.414... |
| Higher-dim lattice | Z⁵ → R² | Z⁴ → R² |
| Key irrational | √5 | √2 |
| Characteristic sequence | Fibonacci | Pell |
| Physical QC | Al-Cu-Fe (icosahedral) | Mn-Si-Al (octagonal) |
| Visual feel | Organic, sunflower | Geometric, grid-like |
| Vertex types | 7 | 5 |

---

## References

- Beenker, F.P.M. (1982). "Algebraic theory of non-periodic tilings of the plane by two simple building blocks." Eindhoven Univ. of Tech., TH-Report 82-WSK-04.
- Ammann, R.; Grünbaum, B.; Shephard, G.C. (1992). "Aperiodic tiles." *Discrete and Computational Geometry* 8: 1–25.
- Bendersky, L. (1985). "Quasicrystal with one-dimensional translational symmetry and a tenfold rotation axis." *Phys. Rev. Lett.* 55(14): 1461.
- Socolar, J.E.S. (1989). "Simple octagonal and dodecagonal quasicrystals." *Phys. Rev. B* 39(15): 10519.
- Nischke, K.P.; Danzer, L. (1996). "A construction of inflation rules based on n-fold symmetry." *Discrete and Computational Geometry* 15: 221–236.

**See also:** [`01_penrose_p2.md`](01_penrose_p2.md) | [`04_stampot.md`](04_stampot.md) | [`master_index.md`](master_index.md)
