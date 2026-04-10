# Pinwheel Tiling

**Discoverers:** John Conway and Charles Radin, 1994  
**Unique property:** Tiles appear at **infinitely many orientations** — unlike all other known aperiodic tilings  
**Base triangle:** Right triangle with legs 1 and 2, hypotenuse √5  
**Inflation factor:** √5 (scale factor for one substitution step)  
**Number of sub-tiles:** 5 triangles per larger triangle  
**Statistical symmetry:** Full continuous rotational symmetry SO(2) in the limit

---

## Definition

The **pinwheel tiling** is an aperiodic tiling of the plane discovered by mathematician **John Horton Conway** and physicist **Charles Radin** in 1994. It uses a single tile — a right triangle with legs in ratio 1:2 — and a self-similar substitution rule that divides one large triangle into five smaller similar triangles. What makes the pinwheel tiling unique among all known aperiodic tilings is that tiles appear at **infinitely many distinct orientations** throughout the plane. No finite set of orientations can describe the tiling: every angle between 0° and 360° eventually appears.

This property contrasts sharply with Penrose tilings (5 orientations per tile type), Ammann-Beenker (8 orientations), and all other known aperiodic tilings, which use only finitely many orientations.

---

## Discoverers

### John Horton Conway (1937–2020)
John Conway was one of the most creative and prolific mathematicians of the 20th century. Best known to the general public for inventing Conway's **Game of Life** (1970), he made fundamental contributions to group theory (the Monster group and other sporadic groups), number theory (surreal numbers), knot theory, combinatorial game theory, and geometry. He held positions at Cambridge and Princeton. Conway proposed the pinwheel tiling construction and brought it to Radin's attention.

### Charles Radin (born 1945)
Charles Radin is a mathematical physicist at the University of Texas at Austin. He has worked extensively on statistical mechanics and the mathematics of aperiodic order. His 1994 paper with Conway in the *Annals of Mathematics* rigorously proved that the pinwheel tiling is aperiodic and that tiles appear at all orientations with equal statistical frequency. Radin extended this work to understand the thermodynamic stability of quasicrystalline order.

---

## The Base Triangle

The single tile is a **right triangle** with:

| Property | Value |
|----------|-------|
| Legs | 1 and 2 (in normalized units) |
| Hypotenuse | √5 ≈ 2.23607 |
| Angles | 90°, arctan(1/2) ≈ 26.565°, arctan(2) ≈ 63.435° |
| Area | (1 × 2)/2 = **1.0** |
| Chirality | Two mirror-image versions (left and right) both used |

This specific triangle was chosen because:
1. Five copies of it can tile one larger similar triangle at scale √5
2. The angle arctan(1/2) is **irrational** as a fraction of π (i.e., arctan(1/2)/π is irrational)
3. This irrationality ensures infinitely many distinct orientations appear

The irrationality of arctan(1/2)/π follows from the Niven-type theorem for trigonometric values and is crucial: if the angle were a rational fraction of π, the tiling would use only finitely many orientations.

---

## Inflation Rule: The Pinwheel Substitution

The pinwheel substitution divides one triangle with legs 1 and 2 (normalized) into five triangles with legs 1/√5 and 2/√5:

### Step-by-Step Subdivision

Starting with a right triangle ABC (right angle at C, short leg CA = 1, long leg CB = 2):

1. **Find midpoint M of hypotenuse AB** → M = midpoint(A,B)
2. **Find point P** one-fifth of the way from C toward A (along the short leg)
3. **Find point Q** dividing CB in ratio 2:1
4. **Connect**: CP, PM, QM, QA, QB in a specific pattern that creates 5 sub-triangles

The resulting five sub-triangles are all similar to the original (right triangle with legs in ratio 1:2) but scaled by 1/√5 and arranged in **5 distinct orientations**. Crucially, each subdivision introduces new orientations by rotating the triangle through arctan(1/2).

### Rotation Accumulation
After n applications of the substitution rule:
- Triangles appear in orientations that are sums/differences of n multiples of arctan(1/2)
- Since arctan(1/2)/π is irrational, these orientations are all distinct and dense in [0°, 360°)
- In the limit n → ∞, **every orientation appears** with equal frequency

This is the source of the tiling's name: the five sub-triangles fan out in a pinwheel pattern, and successive inflation steps create a spiraling, ever-rotating structure.

---

## Statistical Rotational Symmetry

The pinwheel tiling exhibits a form of symmetry found in no other aperiodic tiling:

### Definition
A tiling T is **statistically rotationally symmetric** (or has **statistical SO(2) symmetry**) if for any rotation R and any region Ω, the statistical frequency of any local pattern in T is the same as in R(T).

### Radin's Theorem (1994)
Radin proved that the pinwheel tiling is statistically rotationally symmetric: when you average any local property over all positions in the tiling, the result is independent of direction. This means:
- The Fourier transform of the tiling has **circular symmetry** (diffraction rings rather than spots)
- No orientation is preferred over any other
- The tiling "looks the same" statistically from any angle

### Implications
This property has profound implications:
1. **No preferred directions**: Unlike Penrose (5 preferred directions) or Ammann-Beenker (8), pinwheel has no crystallographic-like directions
2. **Circular diffraction pattern**: X-ray or electron diffraction would show rings, like an amorphous material — but the rings would be *sharp* (long-range order) rather than broad (amorphous)
3. **Intermediate between crystal and glass**: Truly novel structural category

---

## Tile Counts and Frequency

After n substitution steps starting from 1 triangle:
- Total triangles: **5ⁿ**
- Total area: **5ⁿ** (each has area 1 in normalized units, after scaling)

Orientation frequency: after n steps, each of the 5ⁿ triangles has a distinct orientation from the set {k · arctan(1/2) mod 360° : various k combinations}. As n → ∞, these fill [0°, 360°) uniformly.

---

## Connection to √5 and Penrose Tilings

The scale factor √5 is no accident — it is also the diagonal of a 1×2 rectangle, which appears in Penrose geometry (the diagonal of the thin Penrose rhombus at certain scales). The golden ratio φ satisfies φ² = φ+1, and the Penrose substitution uses φ as its scale. The pinwheel uses √5, which is related to φ by:

```
√5 = 2φ - 1 = φ + 1/φ
φ = (1 + √5)/2
```

However, despite sharing √5, the pinwheel and Penrose tilings are **not** mutually locally derivable — they belong to different tiling families with fundamentally different symmetry properties.

---

## Significance in Tiling Theory

### Disproof of "Rotational Alignment" Expectation
Before the pinwheel tiling, it was implicitly assumed that aperiodic tilings always had some preferred set of orientations (like the 5 orientations of Penrose tiles). The pinwheel disproved this, showing that rotational disorder and aperiodic order are compatible.

### Statistical Mechanics Connection
Radin placed the pinwheel tiling in a thermodynamic context: he showed that certain spin systems (particles with orientational degrees of freedom) can have a ground state that is a pinwheel tiling — aperiodic order emerging from energetic minimization. This suggests a physical mechanism for why some materials might form pinwheel-like structures.

### Connection to Molecular Motors
The rotational symmetry of the pinwheel has been invoked in theoretical studies of:
- **Biological molecular motors** (ATP synthase, flagellar motors): rotating machinery in cells
- **Artificial molecular motors**: synthetic molecules that rotate continuously
- The pinwheel's statistical circular symmetry is analogous to the equal-probability rotational motion of a freely rotating motor

### Role in the Aperiodic Tile Landscape
The pinwheel demonstrates that the space of aperiodic tilings is richer than previously thought. It motivated the search for more exotic tilings with:
- More than 2 types of tiles appearing with infinite orientations
- 3D analogues
- Tilings with other non-crystallographic statistical symmetries

---

## Visual Appearance

The pinwheel tiling looks dramatically different from Penrose or Ammann-Beenker:

- **Chaotic appearance**: No obvious large-scale pattern visible at first glance
- **No dominant directions**: Unlike Penrose (5 clear directions), pinwheel looks isotropic
- **Spiral motifs**: Pinwheel-like spirals appear at multiple scales
- **High visual complexity**: The variety of orientations creates intricate boundary patterns
- **Self-similar chaos**: Zooming in or out by √5 reveals the same statistical texture

### Visual Comparison with Other Tilings

| Tiling | Visual feel | Dominant features |
|--------|-------------|-------------------|
| Penrose P2 | Ordered, sunflower-like | Sun/star 5-fold centers |
| Ammann-Beenker | Grid-like, geometric | 8-pointed stars, square grids |
| Stampfli | Mosaic, regular-feeling | 12-fold stars, triangles+squares |
| **Pinwheel** | **Chaotic, isotropic** | **Spirals at all angles** |
| Robinson | Nested squares | Square hierarchy |

### Suggested Color Schemes

| Scheme | Triangle (version 1) | Triangle (version 2) | Notes |
|--------|---------------------|---------------------|-------|
| Direction-coded | Hue = orientation angle | — | Maps each orientation to color |
| Scale-coded | Color by inflation level | — | Shows self-similar hierarchy |
| Two-color | `#FF6B35` coral | `#004E89` blue | Chirality distinction |
| Monochrome | `#DDDDDD` light | `#333333` dark | Parity of subdivision |

The most informative visualization colors tiles by their **orientation angle**, mapping the interval [0°, 360°) to a full hue wheel. This reveals the statistical isotropy visually — all colors appear everywhere with equal frequency.

---

## GLSL Implementation Notes

The pinwheel tiling is significantly harder to implement in GLSL than Penrose tilings, because:
1. No simple pentagrid-like formula exists
2. Direct subdivision must be computed recursively
3. The variety of orientations requires careful floating-point handling

A practical approach for shader implementation:
```glsl
// Iterative pinwheel subdivision
// Start from a large triangle, subdivide n times
// At each pixel, binary-search the subdivision tree to find
// the triangle containing the point

// Key rotation matrix for arctan(1/2):
// cos(arctan(1/2)) = 2/sqrt(5), sin(arctan(1/2)) = 1/sqrt(5)
const float PINWHEEL_COS = 2.0 / sqrt(5.0);  // ≈ 0.89443
const float PINWHEEL_SIN = 1.0 / sqrt(5.0);  // ≈ 0.44721
const float SQRT5 = sqrt(5.0);               // ≈ 2.23607

mat2 pinwheelRot = mat2(PINWHEEL_COS, PINWHEEL_SIN,
                        -PINWHEEL_SIN, PINWHEEL_COS);
```

---

## References

- Conway, J.H.; Radin, C. (1998). "Quaquaversal tilings and rotations." *Inventiones Mathematicae* 132(1): 179–188.
- Radin, C. (1994). "The pinwheel tilings of the plane." *Annals of Mathematics* 139(3): 661–702.
- Radin, C.; Sadun, L. (1998). "Subgroups of SO(3) associated with tilings." *Journal of Algebra* 202(2): 611–633.
- Senechal, M. (1995). *Quasicrystals and Geometry*. Cambridge University Press. pp. 222–225.
- Baake, M.; Grimm, U. (2013). *Aperiodic Order, Vol. 1*. Cambridge. Chapter 4.

**See also:** [`05_trilobite_sphinx.md`](05_trilobite_sphinx.md) | [`07_robinson.md`](07_robinson.md) | [`master_index.md`](master_index.md)
