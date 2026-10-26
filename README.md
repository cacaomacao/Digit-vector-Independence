[![DOI](https://zenodo.org/badge/1329870895.svg)](https://doi.org/10.5281/zenodo.21874854)
# Digit independence under a common multiplier

This repository contains a Lean formalization of an elementary theorem about
base-`p` digit vectors.

## What is proved

For every natural-number base `p >= 2` and every finite set `S` of distinct
positive natural numbers, there exists a single natural number `K` such that
the infinite, zero-padded base-`p` digit vectors of

```text
a * K,  for a in S,
```

are linearly independent over `ZMod p`.

The theorem includes composite bases. In that case `ZMod p` has zero divisors,
so the proof uses a triangular matrix whose determinant is exactly `1` (and
therefore a unit), rather than merely nonzero.

The main Lean theorem is `DigitIndependence.exists_digits_linearIndependent`.

## Files

- [DigitIndependence.lean](DigitIndependence.lean) contains
  the Lean formalization.
- [DigitIndependence.tex](DigitIndependence.tex) contains the complete
  mathematical statement, proof, explanation of the construction, and a guide
  to the Lean file.
- [DigitIndependence.pdf](DigitIndependence.pdf) is the compiled
  version of the LaTeX document.

## Provenance and use of AI

The mathematical idea and the underlying construction are due to
**Mikhail Katkov** (Weizmann Institute of Science, Institute for Advanced Studies).

The present Lean formalization and the accompanying English proof were created
with the assistance of **ChatGPT 5.6 (OpenAI)**. They are shared for human
review. 


## Checking the Lean file

The repository is already a Lake project. It pins Lean `4.32.1` in
[`lean-toolchain`](lean-toolchain), mathlib `v4.32.1` in
[`lakefile.toml`](lakefile.toml), and exact dependency revisions in
[`lake-manifest.json`](lake-manifest.json).

With [elan](https://github.com/leanprover/elan) installed, check a fresh clone:

```bash
git clone https://github.com/cacaomacao/Digit-vector-Independence.git
cd Digit-vector-Independence
lake exe cache get
lake build
```

Elan selects the toolchain from `lean-toolchain`. The first run fetches missing
dependencies and the compiled mathlib cache; the download can be substantial.
`lake build` checks the `DigitIndependence` library, the default Lake target.

To check the source file directly after dependencies are available:

```bash
lake env lean DigitIndependence.lean
```

The [Lean workflow](.github/workflows/lean.yml) runs the same build on pushes
and pull requests using the committed toolchain and manifest.

## License

This work is licensed under the
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)
(CC BY 4.0). See [LICENSE.md](LICENSE.md) for the attribution notice.
