# Quasicrystal Structures Database

![Status](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Tilings](https://img.shields.io/badge/tilings-7-orange) ![Materials](https://img.shields.io/badge/materials-8-purple) ![Symmetry](https://img.shields.io/badge/symmetry-5%2F8%2F10%2F12--fold-gold)

A comprehensive scientific and creative resource for **quasicrystal structures**, aperiodic tilings, mathematical data, GLSL shaders, and generative art assets. This repository bridges rigorous crystallography with practical tools for shader artists, game designers, musicians, and scientific visualizers.

---

## What Are Quasicrystals?

Quasicrystals occupy a remarkable middle ground between the perfect periodicity of crystals and the complete disorder of amorphous solids. They exhibit:

- **Long-range order** — sharp diffraction peaks, just like crystals
- **Aperiodic structure** — no repeating unit cell, unlike crystals
- **Forbidden symmetries** — 5-, 8-, 10-, and 12-fold rotational symmetry, impossible in periodic lattices
- **Self-similarity** — structure repeats at multiple scales via inflation rules

The mathematical backbone is the **golden ratio** φ = (1+√5)/2 ≈ **1.6180339887498948482**, which appears throughout quasicrystal geometry as the irrational spacing ratio that prevents periodicity while maintaining long-range coherence. For 8-fold systems, the **silver ratio** δ_s = 1 + √2 ≈ **2.41421356237309504880** plays the analogous role.

> *"A quasicrystal is a structure that is ordered but not periodic."*  
> — Dan Shechtman, Nobel Laureate in Chemistry 2011

---

## Repository Overview

This database provides:

| Category | Contents |
|----------|----------|
| **Scientific data** | Material properties, symmetry groups, diffraction data for 8 real quasicrystalline alloys |
| **Tiling mathematics** | Full specifications for 7 aperiodic tilings with inflation rules, vertex configurations, matching rules |
| **GLSL shaders** | Ready-to-use fragment shaders for real-time rendering |
| **Creative assets** | Color palettes, pattern generators, music sequences, design templates |
| **Analysis tools** | Fourier transform profiles, symmetry analysis, diffraction simulation |
| **Physics data** | Electronic structure, phonon spectra, thermal properties |

---

## Directory Structure

```
quasicrystals/
├── README.md                          # This file
├── QUASICRYSTAL_PRIMER.md             # Detailed scientific introduction
│
├── core/                              # Core mathematical and scientific data
│   ├── tilings/                       # Aperiodic tiling specifications
│   │   ├── master_index.md            # Summary index of all tilings
│   │   ├── 01_penrose_p2.md           # Penrose P2 rhombus tiling (5-fold)
│   │   ├── 02_penrose_p3.md           # Penrose P3 kite-dart tiling (5-fold)
│   │   ├── 03_ammann_beenker.md       # Ammann-Beenker octagonal tiling (8-fold)
│   │   ├── 04_stampot.md              # Stampfli dodecagonal tiling (12-fold)
│   │   ├── 05_trilobite_sphinx.md     # Trilobite-Sphinx aperiodic pair
│   │   ├── 06_pinwheel.md             # Pinwheel tiling (∞ orientations)
│   │   └── 07_robinson.md             # Robinson tiling (hierarchical squares)
│   └── quasicrystals_database.json    # Material properties for 8 QC alloys
│
├── shaders/                           # GLSL fragment shaders
│   ├── penrose_p2_tiling.glsl         # Real-time Penrose P2 renderer
│   ├── ammann_beenker.glsl            # Ammann-Beenker 8-fold renderer
│   ├── penrose_p3_kite_dart.glsl      # Kite-Dart renderer
│   ├── stampfli_12fold.glsl           # 12-fold dodecagonal renderer
│   └── quasicrystal_diffraction.glsl  # Diffraction pattern simulation
│
├── math/                              # Mathematical utilities and formulas
│   ├── golden_ratio_sequences.md      # Fibonacci, Lucas, Pell sequences
│   ├── inflation_matrices.md          # Substitution/inflation matrices
│   ├── projection_method.md           # Cut-and-project from higher dims
│   └── vertex_coordinates.csv         # Numerical vertex position data
│
├── physics/                           # Physical properties and phenomena
│   ├── electronic_structure.md        # Unusual electron localization
│   ├── phonon_spectra.md              # Vibrational modes (phasons/phonons)
│   ├── tribology.md                   # Low-friction surface properties
│   └── diffraction_theory.md          # X-ray and electron diffraction
│
├── analysis/                          # Analysis and pattern recognition
│   ├── fourier_profiles.md            # Fourier transform characteristics
│   ├── symmetry_detection.md          # Algorithmic symmetry analysis
│   └── correlation_functions.md       # Statistical order parameters
│
├── creative/                          # Creative and artistic applications
│   ├── color_palettes.md              # Quasicrystal-inspired color schemes
│   ├── music_sequences.md             # Quasiperiodic rhythm and pitch patterns
│   ├── pattern_library.md             # SVG pattern templates
│   └── architecture_guide.md          # Architectural facade applications
│
├── visual/                            # Visual assets and rendering data
│   ├── palettes/                      # Color palette files
│   ├── render_params.md               # Rendering parameter reference
│   └── animation_sequences.md         # Keyframe animation data
│
├── data/                              # Raw numerical data files
│   ├── diffraction_peaks.csv          # Experimental diffraction data
│   ├── phonon_frequencies.csv         # Phonon measurement data
│   └── structural_parameters.csv      # Lattice/quasilattice parameters
│
└── metadata/                          # Repository metadata
    ├── sources.md                     # Academic references and sources
    ├── glossary.md                    # Terminology and definitions
    └── changelog.md                   # Version history
```

---

## Use Cases

### 🎨 AI Art & Generative Art
Use quasicrystal tiling patterns as prompts, style references, or procedural masks. The 5-fold and 10-fold Penrose patterns create visually striking aperiodic backgrounds impossible to achieve with standard periodic textures.

```
# Reference files for AI art:
core/tilings/01_penrose_p2.md       → Rhombus geometry, color zone descriptions
creative/color_palettes.md          → Suggested palettes (golden, silver, icosahedral)
visual/palettes/                    → Ready-to-use palette files
```

### 🖥️ Shader Art (GLSL / Shadertoy)
Drop-in fragment shaders with configurable parameters for real-time quasicrystal rendering:

```glsl
// Quick start: Penrose P2 tiling in GLSL
// Reference: shaders/penrose_p2_tiling.glsl
// Uses de Bruijn pentagrid construction
// Uniforms: u_zoom, u_rotation, u_thick_color, u_thin_color

// Quick start: Ammann-Beenker 8-fold
// Reference: shaders/ammann_beenker.glsl
// Silver ratio: delta_s = 1.0 + sqrt(2.0) = 2.41421356
```

### 🎵 Music Generation
Quasiperiodic sequences generate rhythms and pitch patterns with self-similar structure — familiar but never repeating:

```
creative/music_sequences.md → Fibonacci rhythms, Penrose pitch sequences
math/golden_ratio_sequences.md → Substitution sequences for music
```

### 🔬 Scientific Visualization
Accurate material data and diffraction patterns for scientific figures:

```
core/quasicrystals_database.json → 8 real QC alloys with properties
physics/diffraction_theory.md    → Diffraction pattern mathematics
physics/phonon_spectra.md        → Phonon/phason dispersion data
```

### 🏗️ Game Design & Architecture
Aperiodic floor tilings, non-repeating texture atlases, procedural level generation:

```
core/tilings/03_ammann_beenker.md → 8-fold floor patterns
core/tilings/04_stampot.md        → 12-fold decorative patterns
creative/architecture_guide.md    → Facade design reference
```

### 📐 Pattern Design (Textiles, Wallpaper, Logos)
Mathematically precise non-repeating patterns for fabric, wallpaper, and branding:

```
core/tilings/01_penrose_p2.md → Rhombus tile specs for vector art
core/tilings/02_penrose_p3.md → Kite-dart for organic aesthetics
creative/pattern_library.md   → SVG templates
```

---

## Key Mathematical Constants

| Constant | Symbol | Exact Form | Decimal Approximation | Role |
|----------|--------|------------|-----------------------|------|
| Golden ratio | φ | (1+√5)/2 | **1.6180339887498948482** | 5- and 10-fold quasicrystals |
| Silver ratio | δ_s | 1+√2 | **2.4142135623730950488** | 8-fold (Ammann-Beenker) |
| Bronze ratio | — | (3+√13)/2 | **3.3027756377319946...** | Higher-order systems |
| Supergolden | ψ | real root of x³=x+1 | **1.4655712318767680...** | Rare 3D constructions |
| √5 | — | √5 | **2.2360679774997896964** | Penrose geometry base |
| τ = φ | τ | (1+√5)/2 | **1.6180339887498948482** | Alternative notation (physics) |
| 2+√3 | — | 2+√3 | **3.7320508075688772935** | 12-fold inflation ratio |
| cos(π/5) | — | (1+√5)/4 | **0.8090169943749474241** | Penrose vertex geometry |
| sin(π/5) | — | √(10-2√5)/4 | **0.5877852522924731502** | Thin rhombus area |

---

## Quick Start Examples

### Load material data (Python)
```python
import json

with open('core/quasicrystals_database.json') as f:
    qc_data = json.load(f)

# Find all icosahedral quasicrystals
icosahedral = [m for m in qc_data if m['symmetry_type'] == 'icosahedral']
print(f"Found {len(icosahedral)} icosahedral quasicrystals")

# Get hardness of Al-Cu-Fe
al_cu_fe = next(m for m in qc_data if 'Al-Cu-Fe' in m['name'])
print(f"Al-Cu-Fe hardness: {al_cu_fe['hardness_vickers']} HV")
```

### Penrose inflation (Python pseudocode)
```python
PHI = 1.6180339887498948482

def inflate_thick_rhombus(tile):
    """One thick → one thick + two thin (scaled by φ)"""
    return [thick_rhombus(scale=PHI), thin_rhombus(scale=PHI), thin_rhombus(scale=PHI)]

def inflate_thin_rhombus(tile):
    """One thin → one thick + one thin (scaled by φ)"""
    return [thick_rhombus(scale=PHI), thin_rhombus(scale=PHI)]
```

### GLSL golden ratio constant
```glsl
const float PHI = 1.6180339887498948482;
const float SILVER = 2.4142135623730950488;
const float PI = 3.14159265358979323846;
const float TAU = 6.28318530717958647692;
```

---

## Key Files at a Glance

| File | What It Contains |
|------|-----------------|
| [`QUASICRYSTAL_PRIMER.md`](QUASICRYSTAL_PRIMER.md) | Full scientific introduction, history, theory |
| [`core/quasicrystals_database.json`](core/quasicrystals_database.json) | 8 QC alloys, all physical properties |
| [`core/tilings/master_index.md`](core/tilings/master_index.md) | Summary comparison of all 7 tilings |
| [`core/tilings/01_penrose_p2.md`](core/tilings/01_penrose_p2.md) | Penrose P2 (rhombi), full specification |
| [`core/tilings/03_ammann_beenker.md`](core/tilings/03_ammann_beenker.md) | Ammann-Beenker 8-fold, silver ratio |
| [`shaders/penrose_p2_tiling.glsl`](shaders/penrose_p2_tiling.glsl) | Real-time P2 shader |
| [`math/golden_ratio_sequences.md`](math/golden_ratio_sequences.md) | φ-based sequences and series |

---

## Contributing

Contributions welcome! Priority areas:

1. **Additional tilings** — Socolar-Taylor, Penrose P1 (pentagonal), Danzer's 3D tiling
2. **Shader improvements** — distance field rendering, animation, ray-marched 3D QC
3. **Material data** — more alloy systems, experimental measurements
4. **Creative applications** — music theory extensions, textile pattern generators

Please ensure:
- Mathematical data cites primary sources (see `metadata/sources.md`)
- JSON data validates against the schema in `core/quasicrystals_database.json`
- Shader code compiles on Shadertoy / WebGL 2.0
- Use φ = 1.6180339887498948482 (full precision) in all calculations

---

*Built for artists, scientists, and everyone fascinated by the beautiful mathematics at the edge of order and chaos.*
