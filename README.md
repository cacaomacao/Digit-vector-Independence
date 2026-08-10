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

- [DigitIndependence(1).lean](upload/DigitIndependence%281%29.lean) contains
  the Lean formalization.
- [DigitIndependence.tex](DigitIndependence.tex) contains the complete
  mathematical statement, proof, explanation of the construction, and a guide
  to the Lean file.
- [DigitIndependence.pdf](output/pdf/DigitIndependence.pdf) is the compiled
  version of the LaTeX document.

## Provenance and use of AI

The mathematical idea and the underlying construction are due to
**Mikhail Katkov** (Weizmann Institute of Science, Institute for Advanced Studies).

The present Lean formalization and the accompanying English proof were created
with the assistance of **ChatGPT 5.6 (OpenAI)**. They are shared for human
review. 


## Checking the Lean file

Place the file in a Lean project depending on a compatible recent version of
mathlib and run:

```bash
lake env lean 'DigitIndependence.lean'
```

## License

This work is licensed under the
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)
(CC BY 4.0). See [LICENSE.md](LICENSE.md) for the attribution notice.
