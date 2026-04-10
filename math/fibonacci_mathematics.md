# Fibonacci Mathematics in Quasicrystal Context

The Fibonacci sequence is not merely a curiosity of recreational mathematics.
It is the discrete shadow of the golden ratio φ, and through φ it permeates
every aspect of 5-fold quasicrystal geometry. Understanding Fibonacci
mathematics is essential for understanding Penrose tilings and icosahedral
quasicrystals.

---

## 1. The Fibonacci Sequence — Definition and Properties

### Recurrence Relation
    F(0) = 0
    F(1) = 1
    F(n) = F(n-1) + F(n-2)  for n ≥ 2

Sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597...

### Extended Sequence (Negative Indices)
The recurrence extends to negative n via F(n-2) = F(n) - F(n-1):

    F(-1) = 1, F(-2) = -1, F(-3) = 2, F(-4) = -3, F(-5) = 5
    F(-n) = (-1)^(n+1) * F(n)

### Binet's Formula (Closed Form)
    F(n) = (phi^n - psi^n) / sqrt(5)

where:
    phi = (1 + sqrt(5)) / 2 ≈ 1.61803...  (golden ratio)
    psi = (1 - sqrt(5)) / 2 ≈ -0.61803... (= -1/phi, conjugate)

Since |psi| = 1/phi < 1, for large n: F(n) ≈ phi^n/sqrt(5) (to nearest integer).

This formula shows that Fibonacci numbers grow exponentially with base phi:
    F(n) ~ phi^n / sqrt(5)  as n → ∞

### Convergence to phi
    lim_{n→∞} F(n+1)/F(n) = phi

The error: F(n+1)/F(n) - phi = (-1)^n / (sqrt(5) * F(n) * F(n+1))

### Key Identities
- Cassini's identity: F(n+1)*F(n-1) - F(n)^2 = (-1)^n
- Addition formula: F(m+n) = F(m)*F(n+1) + F(m-1)*F(n)
- GCD property: gcd(F(m), F(n)) = F(gcd(m,n))
- Every 3rd Fibonacci is even, every 4th divisible by 3, every 5th by 5...
- Sum formula: F(1)+F(2)+...+F(n) = F(n+2) - 1
- Sum of squares: F(1)^2+F(2)^2+...+F(n)^2 = F(n)*F(n+1)

---

## 2. The Fibonacci Word — A 1D Quasicrystal

### Definition
The Fibonacci word is a binary sequence obtained by repeated substitution:

Substitution rule sigma:
    0 → 01
    1 → 0

Starting from 0, apply sigma repeatedly:

    sigma^0: 0
    sigma^1: 01
    sigma^2: 010
    sigma^3: 01001
    sigma^4: 01001010
    sigma^5: 0100101001001
    sigma^6: 010010100100101001010

The infinite Fibonacci word is the limit:
    w = 0100101001001010010100100101001001010010...

### Length Grows as Fibonacci Numbers
|sigma^n(0)| = F(n+2)  [length of nth iteration]

So sigma^0 has length 1, sigma^1 has length 2, sigma^2 has length 3, etc.

### Properties of the Fibonacci Word
1. **Aperiodic**: The sequence never repeats (no period)
2. **Uniformly recurrent**: Every finite subword appears infinitely often
3. **Minimal complexity**: For any word of length n, there are exactly n+1
   distinct subwords of that length (minimum for an aperiodic word)
4. **Self-similar**: sigma(w) = w (the word is its own substitution image in the limit)

### The Fibonacci Word as a 1D Quasicrystal
Interpret 0 as "long interval L" and 1 as "short interval S":
- L has length phi (long), S has length 1 (short)
- The sequence of intervals forms a 1D aperiodic sequence: LLS LS LLS LLS LS...

This is a genuine 1D quasicrystal:
- Long-range order (sharp Fourier peaks)
- No translational periodicity
- Self-similarity (inflation by phi maps S→L, L→LS)

The diffraction spectrum of the Fibonacci chain has sharp peaks at positions:
    k = (2*pi/d)*(m + n*phi)  for integers m, n
where d is the average spacing. The peaks form a dense set that is NOT periodic.

### Cut-and-Project Derivation of Fibonacci Word
The Fibonacci word can be obtained by projecting a 2D square lattice:

1. Take the 2D integer lattice Z^2
2. Draw a strip of width 1 around the line y = x/phi (slope 1/phi)
3. Project all lattice points in the strip onto the line
4. The gaps between projected points alternate in ratio phi:1 (L and S)
5. Their sequence is exactly the Fibonacci word!

This is the 1D version of the cut-and-project method that produces 2D Penrose tilings.

---

## 3. Zeckendorf's Theorem

Every positive integer has a UNIQUE representation as a sum of non-consecutive
Fibonacci numbers. This is called Zeckendorf's representation.

### Examples
     1 = F(2) = 1
     2 = F(3) = 2
     3 = F(4) = 3
     4 = F(4) + F(2) = 3 + 1
     5 = F(5) = 5
     6 = F(5) + F(2) = 5 + 1
     7 = F(5) + F(3) = 5 + 2
     8 = F(6) = 8
     9 = F(6) + F(2) = 8 + 1
    10 = F(6) + F(3) = 8 + 2
    11 = F(6) + F(4) = 8 + 3
    12 = F(6) + F(4) + F(2) = 8 + 3 + 1
    13 = F(7) = 13

### Connection to Quasicrystals
Zeckendorf's theorem is related to the phinary (base-phi) number system, in which
every integer can be represented using only 0s and 1s with no two consecutive 1s.
This representation underlies the indexing of quasicrystal diffraction peaks and the
structure of the Fibonacci chain.

---

## 4. Fibonacci in Penrose Tiling Tile Counts

### Tile Frequencies
In a finite Penrose P2 tiling obtained by n inflations from a single tile:

Let T(n) = number of thick rhombi after n inflations
Let t(n) = number of thin rhombi after n inflations

The substitution rules give:
    T(n+1) = T(n) + t(n)
    t(n+1) = T(n)

This is exactly the Fibonacci recurrence! Starting from one thick rhombus:
    n=0: T=1, t=0
    n=1: T=1, t=1
    n=2: T=2, t=1
    n=3: T=3, t=2
    n=4: T=5, t=3
    n=5: T=8, t=5
    n=6: T=13, t=8

After n inflations: T(n) = F(n+1), t(n) = F(n).
The ratio T(n)/t(n) = F(n+1)/F(n) → phi as n → infinity.

---

## 5. Substitution Matrix and Its Eigenvalues

### The Substitution Matrix
For Penrose P2 inflation:
    Thick rhombus → 1 thick + 1 thin
    Thin rhombus  → 1 thick + 0 thin

Substitution matrix M:

         thick  thin
thick  [  1     1  ]
thin   [  1     0  ]

M = [[1, 1], [1, 0]]

### Eigenvalues of M
Characteristic polynomial: det(M - lambda*I) = lambda^2 - lambda - 1 = 0

Eigenvalues: lambda_+ = (1+sqrt(5))/2 = phi,  lambda_- = (1-sqrt(5))/2 = psi = -1/phi

The PERRON eigenvalue is phi! The corresponding Perron eigenvector is (phi, 1).
This means the ratio of thick to thin rhombi in an infinite Penrose tiling is exactly phi.

### Why This Matters
The Perron-Frobenius theorem guarantees:
    (T(n), t(n)) ~ C * phi^n * (phi, 1)

- Tile counts grow as phi^n
- Ratio T/t converges to phi
- The second eigenvalue psi = -1/phi has |psi| < 1, so oscillations die out
- The tiling "forgets" its initial condition and converges to universal Penrose structure

---

## 6. Fibonacci Sequence in Higher-Dimensional Quasicrystals

### 3D Icosahedral Case
For icosahedral quasicrystals in 3D, the inflation factor remains phi.
The vertex coordinates involve Fibonacci numbers through the icosahedron:
vertices at (0, +/-1, +/-phi) etc. demonstrate Fibonacci in 3D geometry directly.

The nth shell of vertices in an icosahedral quasicrystal contains a number of atoms
that grows as F(n), confirming the Fibonacci structure extends to 3D quasicrystals.

### Fibonacci Spirals in Diffraction
In the diffraction pattern of a Penrose tiling:
- Peak positions along radial directions are at distances proportional to F(n)
- Peak intensities are governed by phi-powers (decreasing as phi^(-n) for nth satellite)
- The diffraction pattern has 10-fold symmetry with Fibonacci patterns in both
  radial and angular peak distributions

---

## 7. The Fibonacci Chain — Pseudocode

```
function fibonacci_word(n):
    if n == 0: return "0"
    if n == 1: return "01"
    a = "0"; b = "01"
    for i in 1..n-1:
        (a, b) = (b, b + a)
    return b

function fibonacci_chain_positions(n, L=1.618..., S=1.0):
    word = fibonacci_word(n)
    positions = [0.0]
    for each character c in word:
        if c == '0': positions.append(positions.last + L)
        else:        positions.append(positions.last + S)
    return positions
```

Verification:
- Length of word after n steps: F(n+2)
- Number of '0's in word: F(n+1)  
- Number of '1's in word: F(n)
- Ratio 0s/1s → phi as n → infinity

This directly mirrors the thick/thin rhombus ratio in 2D Penrose tilings.

---

## 8. Summary Table: Fibonacci Appearances in Quasicrystals

| Phenomenon                        | Fibonacci Connection                    |
|-----------------------------------|-----------------------------------------|
| Penrose tile count ratio          | T(n)/t(n) = F(n+1)/F(n) → phi          |
| Substitution matrix eigenvalue    | lambda = phi (Perron eigenvalue)        |
| 1D Fibonacci chain intervals      | L/S ratio = phi; sequence = Fib word   |
| Icosahedron vertex coordinates    | (0, ±1, ±phi) uses phi directly        |
| Diffraction peak spacing ratios   | phi = limit of F(n+1)/F(n)             |
| Phyllotaxis spiral counts         | Consecutive Fibonacci numbers           |
| Cut-and-project window size       | phi governs acceptance window width     |
| Inflation recursion depth count   | Number of tiles at depth n = F(n+k)    |
