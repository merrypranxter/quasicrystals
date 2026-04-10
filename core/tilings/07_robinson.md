# Robinson Tiling

**Discoverer:** Raphael Mitchell Robinson, 1971  
**Historical significance:** One of the earliest aperiodic tile sets; dramatically reduced Berger's 20,426 tiles to **6**  
**Tile types:** 6 (modified square tiles with notches and projections)  
**Symmetry:** 4-fold (square) locally, hierarchical  
**Inflation factor:** 2 (hierarchical doubling structure)  
**Structure:** Self-similar nested squares at scales 2, 4, 8, 16, ...  
**Connection to:** Wang's undecidability proof, Berger's result, precursor to Penrose tiles

---

## Definition

The **Robinson tiling** is an aperiodic tiling discovered by mathematician **Raphael Robinson** in 1971. It uses **6 tile types** — all modified squares with notches and projections on their edges — that can tile the infinite plane but only in aperiodic arrangements. The tiling produces a hierarchical, fractal-like structure of nested squares at exponentially growing scales.

Robinson's achievement was to reduce Berger's unwieldy 20,426-tile set to a mere 6 tiles, making aperiodic tiling accessible to direct mathematical analysis. His construction provided a cleaner proof of the undecidability of the tiling problem and directly inspired Roger Penrose's search for even simpler aperiodic tile sets, leading to the Penrose tiles.

---

## Historical Context

### Wang's Domino Problem (1961)
Logician **Hao Wang** posed the **domino problem** in 1961: given a finite set of square tiles with colored edges (Wang tiles), is there an algorithm that determines whether they can tile the infinite plane? Wang conjectured the answer was yes, and further that any tileable set could tile periodically.

### Berger's Proof (1966)
Wang's student **Robert Berger** proved Wang wrong in 1966 (published 1966 in *Memoirs of the American Mathematical Society*). Berger:
1. Constructed a set of **20,426 Wang tiles** that tile the plane only aperiodically
2. Used this to prove the domino problem is **undecidable** (equivalent to the halting problem)
3. His construction encoded a Turing machine's computation into the tiling pattern

Berger's construction was mathematically correct but enormously complex and practically unworkable. The 20,426 tile count made it impractical to visualize or analyze directly.

### Robinson's Simplification (1971)
**Raphael Robinson** dramatically simplified Berger's result. In a 1971 paper in *Inventiones Mathematicae*, Robinson:
1. Reduced the tile count from 20,426 to **6** tiles (or 28 if rotations/reflections counted separately)
2. Gave a cleaner, more geometric proof of aperiodicity
3. Made the underlying structure (hierarchical nested squares) transparent
4. Provided the conceptual framework that Penrose would later use

---

## The Discoverer

### Raphael Mitchell Robinson (1911–1995)
Raphael Robinson was an American mathematician at the University of California, Berkeley, known for:
- **Robinson tiling** (1971) — aperiodic tiles
- **Robinson's theorem** in number theory
- Work on decidability and logic (connected to the broader context of Wang's problem)
- Contributions to formal logic and set theory

Robinson was a logician by training (a student of Alfred Tarski), and his approach to aperiodic tilings reflected his logical background: encoding computational structure (hierarchical self-reference) into a geometric pattern.

---

## Tile Descriptions

Robinson's 6 tile types are all **modified squares** with notches (concave indentations) and projections (convex bumps) on their edges. The modifications serve as matching rules: two adjacent tiles must have complementary edges (a projection in one matches a notch in the other, or flat-to-flat).

### The Six Tile Types

All tiles are square with unit side length. The modifications are:

| Tile ID | Description | Edge modifications |
|---------|-------------|-------------------|
| **R1** | Corner tile | Two projections on adjacent edges, two notches on others |
| **R2** | Cross tile | Four projections (on all 4 edges) — this is the "plus sign" tile |
| **R3** | T-junction | Three projections, one notch |
| **R4** | Straight tile | Two opposite projections, two opposite notches |
| **R5** | Corner notch tile | Two adjacent notches, two projections |
| **R6** | Flat tile | Various combinations |

*Note: The exact labeling varies by source. Robinson's original paper uses a specific notation; modern expositions often use diagrams rather than explicit edge descriptions.*

### Edge Compatibility Rules
- **Projection + notch** = compatible (tiles can be adjacent)
- **Projection + projection** = incompatible
- **Notch + notch** = incompatible
- **Flat + flat** = compatible (if same "signal level")
- **Projection/notch + flat** = incompatible

These 6 tile types (with their 4 rotations and possible reflections, yielding up to 28 oriented tiles) produce all valid Robinson tilings.

---

## The Hierarchical Square Structure

The key to understanding Robinson's tiling is its **hierarchical structure** of nested squares:

### Level-1 Structure: 2×2 Squares
Four tiles can be combined into a 2×2 "super-tile" that forms the first hierarchical level. There is one type of level-1 super-tile (up to symmetry).

### Level-2 Structure: 4×4 Squares
Four level-1 super-tiles combine into a 4×4 super-tile. The boundary of this super-tile has specific projection/notch patterns.

### Level-n Structure: 2ⁿ×2ⁿ Squares
The pattern continues: level-n super-tiles are 2ⁿ × 2ⁿ squares. The entire infinite plane is partitioned into an infinite hierarchy of nested squares at scales:
```
2¹ × 2¹,  2² × 2²,  2³ × 2³,  ...,  2ⁿ × 2ⁿ,  ...
```

Each scale contains exactly one "corner" or "cross" tile of the Robinson type in the interior.

### Why Hierarchical → Aperiodic
Robinson's elegant proof of aperiodicity:
1. Any valid tiling must form the hierarchical structure (forced by matching rules)
2. At each level n, there is a unique 2ⁿ×2ⁿ super-tile
3. Each corner of each super-tile has a specific orientation
4. If the tiling were periodic with period (a,b), then the super-tile at level n would repeat
5. But for large enough n, 2ⁿ > ||(a,b)||, making periodicity impossible
6. Contradiction: the tiling cannot be periodic ∎

This argument is cleaner and more intuitive than Berger's original proof.

---

## Connection to Wang's Domino Problem and Undecidability

The Robinson tiling provides a simplified proof that the **domino problem is undecidable**:

### Encoding Computation
The hierarchical structure of Robinson tiles can encode the execution of a Turing machine:
- Each level-n super-tile encodes n steps of a computation
- A specific computation halts ↔ the corresponding tile set does/doesn't tile the plane
- Since the halting problem is undecidable, so is the tiling problem

### The Significance
Robinson's work showed:
1. **Aperiodic tiling is fundamental**: any tile set capable of tiling the plane aperiodically can encode arbitrarily complex computations
2. **No algorithm for periodicity**: there is no algorithm that, given a tile set, determines whether all its tilings are periodic
3. **Connection to incompleteness**: the undecidability of tiling connects to Gödel's incompleteness theorems via the undecidability of arithmetic

---

## Visual Appearance

The Robinson tiling has a distinctive **fractal square** aesthetic:

- **Square-dominated**: All tiles are squares, giving a regular, grid-like base structure
- **Nested squares at all scales**: The 2ⁿ×2ⁿ hierarchy is visible — large squares contain medium squares contain small squares
- **Fractal-like**: Similar to the Sierpinski carpet or Cantor set, but in a tiling rather than a set
- **Regular in appearance**: More "orderly" looking than Penrose tilings despite being aperiodic
- **Hierarchical corners**: Special corner tiles mark the corners of each level-n super-tile

### Visual Hierarchy at Different Scales

```
Zoom level 1 (individual tiles): 
    See individual square tiles with notch/projection edges
    Basic square pattern visible

Zoom level 2 (2×2 blocks):
    See level-1 super-tiles
    2×2 square blocks visible

Zoom level 3 (4×4 blocks):
    See level-2 super-tiles
    Nested square structure emerging

Zoom level n (2ⁿ×2ⁿ blocks):
    See level-n super-tiles
    Fractal square nesting clear
```

### Suggested Color Schemes

| Scheme | Level-1 tiles | Level-2 tiles | Higher | Notes |
|--------|--------------|--------------|--------|-------|
| Hierarchical | `#FF0000` red | `#00FF00` green | `#0000FF` blue | Color by level |
| Grayscale | White to black | — | — | Shade by level number |
| Technical | `#0066CC` blue | `#CC6600` orange | alternating | Blueprint-like |
| Classic | `#FFFFFF` white | `#000000` black | alternating | B&W, clearest hierarchy |

---

## Relationship to Other Tilings

### Precursor to Penrose
After seeing Robinson's 6-tile result, Roger Penrose set himself the challenge of reducing the number further. Within a few years, he achieved:
- P1: 6 tiles (then various reductions)
- P2/P3: 2 tiles!

Penrose has acknowledged Robinson's work as direct inspiration.

### Wang Tiles
Robinson's tiles can be seen as an elegant reformulation of Wang's colored-edge tiles: the notches and projections encode edge colors geometrically, reducing the abstraction level.

### Comparison

| Property | Robinson | Penrose P2 | Wang (Berger) |
|----------|----------|------------|---------------|
| Tile count | 6 | 2 | 20,426 |
| Tile shapes | Modified squares | Rhombi | Unit squares |
| Matching rules | Geometric notches | Arrow decorations | Edge colors |
| Inflation factor | 2 | φ ≈ 1.618 | — |
| Visual character | Nested squares | 5-fold patterns | Grid |
| Symmetry | 4-fold (locally) | 5-fold | 4-fold |

---

## Modern Reductions and Variants

Following Robinson's 6 tiles, researchers continued to reduce tile counts:

- **Ammann (1977)**: 2 tiles for aperiodic tiling (independently, different approach)
- **Penrose (1974)**: 2 tiles (P2 or P3 sets)
- **Socolar-Taylor (2011)**: 1 tile with disconnected faces (technicality in "one tile")
- **Smith et al. (2023)**: 1 tile ("Hat" and "Spectre" — true single tiles without edge markings)

Robinson's 6 tiles thus sit historically between Berger's 20,426 and Penrose's 2, representing a crucial simplification that made the mathematics accessible.

---

## Mathematical Importance for Logic and Computability

### The Tiling Problem
The domino problem (or tiling problem) asks: given a finite tile set T, does T tile the plane? The connection is:

```
Halting Problem: "Does program P halt on input n?" — UNDECIDABLE
         ↕ (via Robinson/Berger construction)
Tiling Problem: "Does tile set T tile the plane?" — UNDECIDABLE
```

Robinson's simplified construction provides a more transparent encoding.

### Consequences
1. There is no algorithm that determines whether an arbitrary finite tile set tiles the plane
2. There is no algorithm that determines whether an arbitrary finite tile set tiles the plane **periodically** (even if we know it tiles)
3. These results are related to the undecidability of the first-order theory of arithmetic

---

## GLSL Notes

The Robinson tiling is practical to implement in GLSL because of its square/hierarchical structure:

```glsl
// Robinson tiling via hierarchical squares
// Level n: 2^n x 2^n grid
const int MAX_LEVEL = 8;

// Find which level-n super-tile contains point p
ivec2 coords = ivec2(floor(p));  // integer grid coordinates

// Detect corner/cross positions at each hierarchy level
for (int n = 0; n < MAX_LEVEL; n++) {
    ivec2 levelCoord = coords / (1 << n);
    bool isLevelCorner = (levelCoord.x % 2 == 0) && (levelCoord.y % 2 == 0);
    // ... assign tile type based on level and position
}
```

---

## References

- Robinson, R.M. (1971). "Undecidability and nonperiodicity for tilings of the plane." *Inventiones Mathematicae* 12(3): 177–209.
- Berger, R. (1966). "The undecidability of the domino problem." *Memoirs of the American Mathematical Society* 66: 1–72.
- Wang, H. (1961). "Proving theorems by pattern recognition II." *Bell System Technical Journal* 40(1): 1–41.
- Grünbaum, B.; Shephard, G.C. (1987). *Tilings and Patterns*. W.H. Freeman. §11.1.
- Senechal, M. (1995). *Quasicrystals and Geometry*. Cambridge. pp. 130–145.
- Goodman-Strauss, C. (2010). "Can't decide? Undecide!" *Notices of the AMS* 57(3): 343–356.

**See also:** [`05_trilobite_sphinx.md`](05_trilobite_sphinx.md) | [`06_pinwheel.md`](06_pinwheel.md) | [`master_index.md`](master_index.md)
