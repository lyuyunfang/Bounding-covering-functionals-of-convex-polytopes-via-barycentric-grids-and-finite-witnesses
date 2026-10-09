# Bounding covering functionals of convex polytopes via barycentric grids and finite witnesses
Reproduction package for upper bounds computed on barycentric grids, and for exact lower bounds certified by finite witnesses. The three bodies are the 24-cell, the 4-dimensional cross-polytope, and the 4-simplex.

## Download

Code, certificates, grids, and numerical outputs are in one archive on the GitHub Release. This page is the description of that archive. Several certificates and grids exceed the size GitHub accepts in the repository file list.

[Bounding-covering-functionals-reproduction.zip](https://github.com/lyuyunfang/Bounding-covering-functionals-of-convex-polytopes-via-barycentric-grids-and-finite-witnesses/releases/download/v1.0/Bounding-covering-functionals-reproduction.zip) (205.09 MB), attached to the [v1.0 release](https://github.com/lyuyunfang/Bounding-covering-functionals-of-convex-polytopes-via-barycentric-grids-and-finite-witnesses/releases/tag/v1.0).

SHA-256: `f1c58e4fb1aca1d8c01a57636215f02b8ba57f6ea3bff5843b1e9148c2aea9bc`

Unpacking the archive gives the directory described below. The link matches release tag `v1.0`.

## Layout

- `upper_bound_common.py` — shared geometry and the posteriori bound `U = f + n/(k+n)*(1-f)`.
- `24cell/24cell ，k=40/` — numerical upper bounds for the 24-cell at grid level `k = 40` (`m = 8..16`). The audited run is in `rerun_output/`.
- `24cell/k-covergence/` — grid-level study at `p = 12` for `k = 5,10,...,40`.
- `24cell/Ablation experiment/` — search ablations (random vs VDI initialization, one vs three seeds, warm start). Tables and logs are in `results/`.
- `24cell/LB/` — exact certificates for the 24-cell, witness points, and `find_witness_points.py`.
- `cross/crossploytope k_60/` — numerical upper bounds for the cross-polytope at `k = 60`.
- `cross/LB/` — exact certificates for the cross-polytope.
- `simplex/simplex k_100/` — numerical upper bounds for the simplex at `k = 100` (`p = 5,6,7`).
- `simplex/LB/` — exact certificates for the simplex.

Each `rerun_output/manifest.json` (and `24cell_kstudy_p12/manifest.json`) stores SHA-256 hashes of that numerical package. These are floating-point search records.

## Checking a certificate

From the corresponding `LB` directory, pass the `.json` certificate directly:

```text
python gamma_24cell_exact_complete_v2.py --verify certificate_gamma8_24cell_exact.json
python gamma_m_4d_exact_complete.py --verify certificate_gamma8_4d_exact.json
python gamma_simplex_exact_complete_fixed.py --verify certificate_gamma5_simplex_exact.json
```

Requires Python 3, NumPy, SciPy, and NLopt. CuPy is used when a GPU is present. `find_witness_points.py` requires Gurobi.

## Large files in the archive

| File | Size | SHA-256 |
| --- | ---: | --- |
| `24cell/LB/certificate_gamma12_24cell_exact.json` | 386.22 MB | `091fb8c81a1e4276ee986cd709b574bf265c1ac5200ecbd3a26712d623ef0a91` |
| `cross/LB/certificate_gamma13_4d_direct.json` | 393.72 MB | `3079bdea1490d62b490f506b3c54752a59f0bfe0ea2263205afe4e25b83b6c26` |
| `24cell/24cell ，k=40/rerun_output/grid_k40_s76.npy` | 157.43 MB | `762193044b23f2a6eeee8adb9cc230698298ece2cadc27997945c934847d0ebf` |
| `24cell/k-covergence/24cell_kstudy_p12/24cell_grid_k40_0185d74c9f27d81b.npy` | 157.43 MB | `762193044b23f2a6eeee8adb9cc230698298ece2cadc27997945c934847d0ebf` |
| `24cell/k-covergence/24cell_kstudy_p12/24cell_grid_k35_0185d74c9f27d81b.npy` | 95.38 MB | `292ebf092264eb83d54b87fe8504d1aace4d0935ba1c19058690df4f0503a8d3` |
| `cross/crossploytope k_60/rerun_output/crosspolytope_grid_k60.npy` | 77.56 MB | `82ee2ee9ea950f23beea2938814634936d8ccbbe1974da71da645111b71e4e9a` |
| `cross/crossploytope k_60/rerun_output/grid_k60_8d00ce98fa7e8e0a9ebb37805cc1f2f4581c90c396e4df5fb929189ce6b36e5c.npy` | 77.56 MB | `82ee2ee9ea950f23beea2938814634936d8ccbbe1974da71da645111b71e4e9a` |
| `simplex/simplex k_100/rerun_output/simplex_grid_k100.npy` | 70.16 MB | `f00ba25af833b6bd88cfcf4c53fa394b75965dc9697298a58013756a549a47bc` |
| `24cell/k-covergence/24cell_kstudy_p12/24cell_grid_k30_0185d74c9f27d81b.npy` | 53.78 MB | `efeefc9505ca8ab390a68b49fb2e9f5324c94dfc7da3c3c3b550a36f7f221a16` |
| `24cell/k-covergence/24cell_kstudy_p12/24cell_grid_k25_0185d74c9f27d81b.npy` | 27.54 MB | `e2c3ecc112e8b1e7e98697741d8273a4b2678802e8072761315cd2178ae7825f` |
