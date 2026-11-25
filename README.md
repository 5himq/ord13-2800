# ORD13-2800 — Multiplicative Order of 13, Verified Dataset

ORD13-2800 is a verified numerical dataset of the multiplicative order of 13.

For each n, let m_n be the n-th positive integer coprime to 13
(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 15, …). The dataset tabulates

    a(n) = ord_13(m_n)

the multiplicative order of 13 modulo m_n: the least a ≥ 1 such that
13^a ≡ 1 (mod m_n).

First 20 values: 1, 1, 1, 1, 4, 1, 2, 2, 3, 4, 10, 1, 2, 4, 4, 4, 3, 18, 4, 2.

No dedicated OEIS entry or b-file for this sequence was found in the range
surveyed when the dataset was compiled, so the values are not a copy of an
existing OEIS b-file.

## Free sample

Points 1–100 of the full product (n = 1 .. 100,000; 100,000 values), in the
same CSV + JSON format as the full product, with per-file SHA-256 hashes:

- **Product / measurement page:** https://5himq.github.io/ord13-2800/
- **Download the free sample (ZIP, ~1.5 MB):**
  https://github.com/5himq/ord13-2800/releases/download/sample-v1/ord13-2800-sample.zip
  (release page: https://github.com/5himq/ord13-2800/releases/tag/sample-v1)

Sample totals: sum of all 100,000 values = 796,417,113; minimum = 1;
maximum = 108,300. Example values: a(1,000) = 342 (m = 1,083);
a(100,000) = 6,018 (m = 108,333).

## Full product

- **Price: $39.99**
- **Release date: December 30, 2026** (planned listing: Getly, Windows Apps
  category)
- All 2,800 points (n = 1 .. 2,800,000), CSV + JSON + README + manifest per
  point, an index file, and a single master file of all 2,800,000 values.
- Full-dataset reference figures: sum of all values = 511,687,189,205;
  maximum value = 3,033,322 (at n = 2,799,991); 385,730 distinct values.
  Master-file SHA-256:
  `5a703013b96da295649782a3f1837facd4bde88fa5aa0125c05b4de7eba9424b`

Nothing is sold through this repository and there is no checkout here.
This repository supports a demand measurement for the upcoming release;
the measurement page collects no personal information.

## How the values were verified

1. **Generation** — each order was computed by reducing φ(m) over its prime
   factorization.
2. **Defining-property check** — for every term, 13^a ≡ 1 (mod m) and
   minimality were verified directly. Violations: 0.
3. **Independent recomputation** — every term was recomputed by a different
   algorithm (prime-power decomposition of m, orders combined by lcm).
   Mismatches: 0.

Spot-check any value in Python: `pow(13, a, m) == 1`, plus the same test
with `a` divided by each of its prime factors (all must differ from 1).
