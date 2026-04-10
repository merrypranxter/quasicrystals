# Vertex & Edge Calculations for Aperiodic Tilings

## Golden Ratio Foundation

All geometric measurements in 5-fold quasicrystal tilings are expressed in terms of φ (the golden ratio):

```
φ = (1 + √5) / 2 ≈ 1.6180339887498948...
φ² = φ + 1 ≈ 2.6180339887...
1/φ = φ - 1 ≈ 0.6180339887...
```

---

## Penrose P2 (Rhombi Tiling)

### Tile Definitions

**Thick Rhombus (Acute Rhombus)**
- Acute angles: 72°
- Obtuse angles: 108°
- Edge length: 1 (normalized)
- Area: sin(72°) ≈ 0.9511
- Diagonal (short): 2·sin(36°) ≈ 1.1756
- Diagonal (long): 2·sin(72°) ≈ 1.9021 = φ · short diagonal

**Thin Rhombus (Obtuse Rhombus)**
- Acute angles: 36°
- Obtuse angles: 144°
- Edge length: 1 (normalized)
- Area: sin(36°) ≈ 0.5878
- Diagonal (short): 2·sin(18°) ≈ 0.6180 = 1/φ
- Diagonal (long): 2·sin(72°) · ... ≈ 1.9021

### Ratio
- Area(thick) / Area(thin) = sin(72°) / sin(36°) = φ
- Count(thick) / Count(thin) → φ as tiling grows infinitely

### Vertex Angles in Penrose P2 (all multiples of 36°)
| Vertex Type | Tile combination | Total angle |
|-------------|-----------------|-------------|
| S (Star) | 5 thin rhombi | 5 × 36° = 180° → 360° |
| D (Deuce) | 3 thick + ... | varies |
| J (Jack) | 2 thick + 2 thin | 360° |
| K (King) | ... | 360° |
| Q (Queen) | ... | 360° |
| A | 1 thick + 4 thin | 360° |
| B | 2 thick + 1 thin | 360° |

---

## Penrose P3 (Kite-Dart Tiling)

### Tile Definitions

**Kite**
- Angles: 72°, 72°, 72°, 144° (two pairs)
- More precisely: top 72°, two sides 72°, bottom 144°
- Edge lengths: long edges φ, short edges 1 (or long = 1, short = 1/φ)
- Area: φ · sin(72°) / 2 ≈ 0.769

**Dart**
- Angles: 36°, 36°, 36°, 252°... 
- Actually: top 36°, two wings 72°, concave 216°
- Edge lengths match kite edges exactly at joins
- Area: sin(36°) / 2 ≈ 0.294

### Kite-to-Dart Ratio
- Area(kite) / Area(dart) = φ²
- Count(kite) / Count(dart) → φ² in infinite tiling

### Vertex Configurations for P3
There are 7 legal vertex configurations:

1. **Sun (S)**: 5 kites, top vertices meeting — 5 × 72° = 360°
2. **Star (St)**: 5 darts, concave vertices meeting — 5 × 72° = 360°
3. **Ace (A)**: 2 kites + 1 dart — at dart tip
4. **Deuce (D)**: kite/dart combination
5. **Jack (J)**: kite/dart combination
6. **Queen (Q)**: kite/dart combination
7. **King (K)**: kite/dart combination

---

## Ammann-Beenker (8-fold)

### Silver Ratio
```
δ_s = 1 + √2 ≈ 2.41421356...
```

### Tile Definitions

**Square**
- All angles: 90°
- Edge length: 1
- Area: 1

**45°-135° Rhombus**
- Acute angles: 45°
- Obtuse angles: 135°
- Edge length: 1
- Area: sin(45°) = √2/2 ≈ 0.7071

### Edge Lengths in Terms of Silver Ratio
- Inflation factor: δ_s = 1 + √2
- After one inflation, 1 unit tile becomes δ_s unit pattern
- Diagonal of rhombus: 2·sin(67.5°) ≈ 1.8478 (long), 2·sin(22.5°) ≈ 0.7654 (short)

### Ratio of Squares to Rhombi
- In infinite tiling: N(squares) / N(rhombi) = 1 / √2

---

## Symmetry Angle Reference Table

| Symmetry | Base Angle | Angles Present |
|----------|-----------|----------------|
| 5-fold   | 36°       | 36°, 72°, 108°, 144°, 180° |
| 8-fold   | 45°       | 45°, 90°, 135°, 180° |
| 10-fold  | 18°       | 18°, 36°, 54°, 72°, 90°, 108°, 126°, 144°, 162°, 180° |
| 12-fold  | 30°       | 30°, 60°, 90°, 120°, 150°, 180° |

---

## Inflation Scale Factors

| Tiling | Inflation Factor | Numeric Value |
|--------|-----------------|---------------|
| Penrose P2/P3 | φ = (1+√5)/2 | 1.6180... |
| Ammann-Beenker | 1+√2 (silver ratio) | 2.4142... |
| Stampfli | 2+√3 | 3.7320... |
| Pinwheel | √5 | 2.2360... |
| Socolar | 2+√3 | 3.7320... |
| 12-fold | 2+√3 | 3.7320... |

---

## Substitution Matrix Eigenvalues

The substitution matrix M for a tiling has entries M[i][j] = number of tile type i in substituted tile type j.

**Penrose P2 Substitution Matrix:**
```
         thick  thin
thick  [  1     1  ]
thin   [  2     1  ]
```
Eigenvalues: λ₁ = φ² ≈ 2.618, λ₂ = -1/φ² ≈ -0.382
Dominant eigenvalue = φ² = inflation factor squared.
Eigenvector ratio = φ (ratio of thick to thin tiles).

**Ammann-Beenker Substitution Matrix:**
```
          square  rhombus
square  [  1       2     ]
rhombus [  4       5     ]
```
Dominant eigenvalue = (1+√2)² = 3 + 2√2 ≈ 5.828

---

## Vertex Coordination Numbers

| Tiling | Vertex Type | Coordination |
|--------|-------------|-------------|
| Penrose P2 | All vertices | 3, 4, or 5 tiles meeting |
| Penrose P3 | Sun | 5 (kites) |
| Penrose P3 | Star | 5 (darts) |
| Ammann-Beenker | Corner vertex | 4–8 tiles |
| Pinwheel | Generic | variable |

---

## Edge Length Formulas in Nested Deflations

After n deflation steps in Penrose P2 (starting with unit edge = 1):
```
Edge length at level n = φ^(-n)
Tile area at level n = φ^(-2n) · original_area
Number of tiles at level n ~ φ^(2n)
```

For Ammann-Beenker:
```
Edge length at level n = (1+√2)^(-n)
```

---

## Trigonometric Identities for 5-Fold Geometry

```
cos(36°) = φ/2 = (1+√5)/4
cos(72°) = (√5-1)/4 = 1/(2φ)
sin(18°) = (√5-1)/4 = 1/(2φ)
sin(36°) = √(10-2√5)/4
sin(54°) = φ/2
sin(72°) = √(10+2√5)/4

tan(36°) = √(5-2√5)
tan(72°) = √(5+2√5)
```

These identities appear directly in computing edge intersections, vertex positions, and tile areas.

---

## Worked Example: Penrose P2 Vertex Position Calculation

To find vertex positions for a thick rhombus with one vertex at origin, bottom edge along x-axis:

```
Vertex 0: (0, 0)
Vertex 1: (1, 0)  [edge length = 1]
Vertex 2: (1 + cos(108°), sin(108°)) = (1 - 0.309, 0.9511) ≈ (0.691, 0.951)
Vertex 3: (cos(108°), sin(108°)) = (-0.309, 0.951)
```

Interior angle at V0 = V3 = 108° (obtuse).
Interior angle at V1 = V2 = 72° (acute).
