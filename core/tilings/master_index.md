# Aperiodic Tilings: Master Index

A comprehensive reference index for all seven aperiodic tiling systems documented in this repository. Use this file to compare tilings, choose the right one for your application, and navigate to detailed documentation and associated shaders and data.

---

## Quick Reference Table

| ID | Name | Discoverer(s) | Year | Symmetry | Tile Types | Inflation Ratio | Key Constant |
|----|------|---------------|------|----------|------------|-----------------|--------------|
| 01 | Penrose P2 (Rhombus) | Roger Penrose | 1974 | 5-fold (C₅ᵥ) | 2 | φ ≈ 1.618 | √5 |
| 02 | Penrose P3 (Kite-Dart) | Roger Penrose | 1978 | 5-fold (C₅ᵥ) | 2 | φ ≈ 1.618 | √5 |
| 03 | Ammann-Beenker | Ammann (1977), Beenker (1982) | 1977 | 8-fold (D₈) | 2 | δ_s ≈ 2.414 | √2 |
| 04 | Stampfli (Dodecagonal) | Peter Stampfli | 1986 | 12-fold (D₁₂) | 2–3 | 2+√3 ≈ 3.732 | √3 |
| 05 | Trilobite-Sphinx | Goodman-Strauss | 1999 | 5-fold (local) | 2 | φ² ≈ 2.618 | √5 |
| 06 | Pinwheel | Conway & Radin | 1994 | SO(2) statistical | 1 (+ mirror) | √5 ≈ 2.236 | √5 |
| 07 | Robinson | Raphael Robinson | 1971 | 4-fold (D₄) | 6 | 2 | — |

---

## Detailed Comparison

### Mathematical Properties

| Tiling | Higher-dim lattice | Acceptance window | Tile angle set | Vertex types |
|--------|--------------------|-------------------|----------------|--------------|
| Penrose P2 | Z⁵ → R² | Regular decagon | {36°, 72°, 108°, 144°} | 7 |
| Penrose P3 | Z⁵ → R² | Regular decagon | {36°, 72°, 144°} | 7 |
| Ammann-Beenker | Z⁴ → R² | Regular octagon | {45°, 90°, 135°} | 5 |
| Stampfli | Z⁴ → R² | Regular 12-gon | {60°, 90°, 120°} | varies |
| Trilobite-Sphinx | (Z⁵ derived) | — | Curved/notched | 5+ |
| Pinwheel | — | — | {26.6°, 63.4°, 90°} | ∞ orientations |
| Robinson | — | — | {90°} only | 4–6 |

### Inflation Ratios and Algebraic Roots

| Tiling | Inflation λ | Algebraic equation | Decimal | Related sequence |
|--------|-------------|---------------------|---------|-----------------|
| Penrose P2/P3 | φ | x² - x - 1 = 0 | 1.6180339887... | Fibonacci: 1,1,2,3,5,8,... |
| Ammann-Beenker | δ_s | x² - 2x - 1 = 0 | 2.4142135623... | Pell: 1,2,5,12,29,70,... |
| Stampfli | 2+√3 | x² - 4x + 1 = 0 | 3.7320508075... | — |
| Trilobite-Sphinx | φ² | x² - 3x + 1 = 0 | 2.6180339887... | Fibonacci (2-step) |
| Pinwheel | √5 | x² - 5 = 0 | 2.2360679774... | — |
| Robinson | 2 | — | 2.0 | Powers of 2: 1,2,4,8,... |

---

## Shader File Cross-Reference

| Tiling | Shader File | Approach | WebGL Compatible |
|--------|-------------|----------|-----------------|
| Penrose P2 | `shaders/penrose_p2_tiling.glsl` | de Bruijn pentagrid | Yes |
| Penrose P3 | `shaders/penrose_p3_kite_dart.glsl` | Triangle decomposition | Yes |
| Ammann-Beenker | `shaders/ammann_beenker.glsl` | Octagonal grid | Yes |
| Stampfli | `shaders/stampfli_12fold.glsl` | 12-grid | Yes |
| Trilobite-Sphinx | (no shader yet — complex geometry) | — | — |
| Pinwheel | (no shader yet — infinite orientations) | Recursive subdivision | Partial |
| Robinson | (no shader yet — see notes) | Hierarchical squares | Possible |

---

## Data File Cross-Reference

| Tiling | Related Materials | Data Files |
|--------|------------------|------------|
| Penrose P2 | Icosahedral Al-Cu-Fe, Al-Pd-Mn | `data/diffraction_peaks.csv` |
| Penrose P3 | Icosahedral quasicrystals | `data/structural_parameters.csv` |
| Ammann-Beenker | Mn-Si-Al octagonal QC | `data/structural_parameters.csv` |
| Stampfli | Ni-Cr, Ta-Te dodecagonal QC | `data/structural_parameters.csv` |
| Trilobite-Sphinx | Theoretical only | — |
| Pinwheel | Theoretical only | — |
| Robinson | Theoretical only | — |

---

## Visual Complexity Ratings

*Scale: 1 (simple) to 10 (highly complex). Ratings are subjective but reflect how intricate the visual pattern appears to most observers.*

| Tiling | Visual Complexity | Mathematical Complexity | Render Difficulty |
|--------|-------------------|------------------------|-------------------|
| Penrose P2 | 7/10 | 6/10 | 4/10 (pentagrid easy) |
| Penrose P3 | 7/10 | 6/10 | 5/10 |
| Ammann-Beenker | 6/10 | 5/10 | 4/10 |
| Stampfli | 8/10 | 6/10 | 5/10 |
| Trilobite-Sphinx | 9/10 | 8/10 | 8/10 (complex shapes) |
| Pinwheel | 10/10 | 9/10 | 9/10 (∞ orientations) |
| Robinson | 5/10 | 7/10 (historical) | 5/10 |

---

## Use Case Recommendations

### For Shader Art / Real-Time Rendering
**Best choices:** Penrose P2, Ammann-Beenker, Stampfli  
**Why:** Clean pentagrid/multigrid constructions implementable efficiently in GLSL. Sharp visual identity. Well-established shader techniques available.  
**References:** `shaders/penrose_p2_tiling.glsl`, `shaders/ammann_beenker.glsl`

### For Scientific Visualization
**Best choices:** Penrose P2 (icosahedral QC), Ammann-Beenker (octagonal QC), Stampfli (dodecagonal QC)  
**Why:** These directly model real quasicrystalline materials. Accurate diffraction patterns, real lattice parameters.  
**References:** `core/quasicrystals_database.json`, `physics/diffraction_theory.md`

### For AI Art Generation
**Best choices:** Penrose P3 (organic kite-dart), Trilobite-Sphinx (biological shapes), Pinwheel (complex texture)  
**Why:** Most visually distinctive and non-machine-like. Penrose P3 has an organic flow; pinwheel provides complex isotropic texture; trilobite-sphinx has unique biological aesthetic.  
**References:** `creative/color_palettes.md`

### For Game Design / Level Generation
**Best choices:** Penrose P2, Ammann-Beenker  
**Why:** Regular enough to be navigable, irregular enough to be interesting. Player cannot exploit periodicity.  
**References:** `creative/pattern_library.md`

### For Music Generation
**Best choices:** Penrose P2 (Fibonacci rhythms), Pinwheel (complex rhythm), Robinson (hierarchical timing)  
**Why:** Substitution sequences → rhythmic patterns. Penrose gives golden ratio rhythm. Robinson gives dyadic (2-based) hierarchy.  
**References:** `creative/music_sequences.md`, `math/golden_ratio_sequences.md`

### For Architecture / Physical Tiling
**Best choices:** Penrose P2 or P3, Ammann-Beenker, Stampfli  
**Why:** All have clean geometry compatible with physical tile manufacturing. P2 and AB have been used in real buildings.  
**References:** `creative/architecture_guide.md`

### For Educational/Historical Purposes
**Best choices:** Robinson (historical significance), Penrose P3 (famous, widely known), Penrose P2 (most common in art)  
**Why:** Robinson has the most interesting historical story (Wang→Berger→Robinson→Penrose chain). Penrose tilings are most widely recognized.  
**References:** `QUASICRYSTAL_PRIMER.md`

---

## Physical Quasicrystal Material Associations

| Tiling Type | Associated QC Materials | Symmetry | Discovered |
|-------------|------------------------|----------|-----------|
| 3D Penrose (icosahedral) | Al-Mn, Al-Cu-Fe, Al-Pd-Mn, Cd-Yb | Icosahedral (m3̄5) | 1982–2000 |
| Ammann-Beenker (8-fold) | Mn-Si-Al, Cr-Ni-Si | Octagonal | 1985–1987 |
| Stampfli (12-fold) | Ni-Cr, Ta-Te, V-Ni-Si | Dodecagonal | 1985–1987 |
| Penrose 10-fold | Al-Co-Ni, Al-Co decagonal | Decagonal (10/mmm) | 1985–1988 |
| Penrose P2/P3 (5-fold 2D) | Al-Co-Ni (in-plane) | 5-fold within layers | Various |

> **Note:** Penrose P2 and P3 are 2D tilings; the analogous 3D icosahedral QC structures use 3D versions (oblate/prolate rhombohedra). The 2D tilings model the cross-section of decagonal QC structures.

---

## Mathematical Relationships Between Tilings

```
Penrose P1 ──────────── Penrose P2 ──────────── Penrose P3
(6 tiles)     inflate     (2 rhombi)   deflation    (kite+dart)
                            |
                            | φ-related
                            ↓
                    Trilobite-Sphinx
                   (geometric realization
                    of P2 matching rules)

Ammann-Beenker ─── analogous ─── Stampfli
  (8-fold, √2)                  (12-fold, √3)

Robinson ─── inspired ──→ Penrose
(6 tiles, 1971)              (2 tiles, 1974)

Pinwheel ─── unique family ─── (no close relatives)
  (√5, ∞ orientations)
```

---

## Tile Count and Tile Type Summary

| Tiling | Tile types | Orientations per type | Total distinct oriented tiles |
|--------|------------|----------------------|------------------------------|
| Penrose P2 | 2 | 5 each | 10 |
| Penrose P3 | 2 | 5 each | 10 |
| Ammann-Beenker | 2 | 1 sq, 4 rhombus | 5 |
| Stampfli | 2 (or 3) | many | 12+ |
| Trilobite-Sphinx | 2 | 5+10 | 15 |
| Pinwheel | 1 (+mirror) | ∞ | ∞ |
| Robinson | 6 | 4 each | 24 (or 28 with reflections) |

---

## Further Reading Index

For deeper study of each tiling and the underlying mathematics:

| Topic | File in This Repo | External Resource |
|-------|-------------------|-------------------|
| Cut-and-project method | `math/projection_method.md` | Senechal (1995), Ch. 3 |
| Golden ratio sequences | `math/golden_ratio_sequences.md` | Gardner (1977) |
| Inflation matrices | `math/inflation_matrices.md` | Grünbaum & Shephard (1987) |
| Diffraction theory | `physics/diffraction_theory.md` | de Wolff et al. (1981) |
| QC material properties | `core/quasicrystals_database.json` | Janot (1994) |
| Historical overview | `QUASICRYSTAL_PRIMER.md` | Steinhardt (2019) |
| Shader implementations | `shaders/` directory | Shadertoy community |

---

**Navigation:** [README](../../README.md) | [Primer](../../QUASICRYSTAL_PRIMER.md) | [Database](../quasicrystals_database.json)  
**Tilings:** [P2](01_penrose_p2.md) | [P3](02_penrose_p3.md) | [AB](03_ammann_beenker.md) | [Stampfli](04_stampot.md) | [Trilobite](05_trilobite_sphinx.md) | [Pinwheel](06_pinwheel.md) | [Robinson](07_robinson.md)
