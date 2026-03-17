# xtpqroot

**Panel Quantile Unit Root Tests with Common Shocks and Structural Breaks**

<!-- badges: start -->
[![CRAN status](https://www.r-pkg.org/badges/version/xtpqroot)](https://CRAN.R-project.org/package=xtpqroot)
<!-- badges: end -->

## Overview

`xtpqroot` implements two panel unit root tests for data with cross-sectional
dependence:

- **CIPS(tau)**: Quantile extension of Pesaran's (2007) CIPS test. Detects
  asymmetric persistence across different quantiles.
- **tFR**: Combines fractional Fourier function (smooth breaks) with a
  logistic smooth transition (sharp breaks) — Corakci & Omay (2023).

## Installation

```r
install.packages("xtpqroot")
```

## Usage

```r
library(xtpqroot)
dat <- grunfeld_pqroot()

# CIPS(tau) test
res <- xtpqroot(dat, var = "invest", panel_id = "firm",
                time_id = "year", test = "cipstau",
                quantiles = c(0.1, 0.5, 0.9), reps = 500L)
print(res)

# tFR test
res2 <- xtpqroot(dat, var = "invest", panel_id = "firm",
                 time_id = "year", test = "tfr",
                 model = "intercept", bootreps = 500L)
print(res2)
```

## References

- Yang, Z., Wei, Z. & Cai, Y. (2022). Econ. Letters, 219, 110809.
  <https://doi.org/10.1016/j.econlet.2022.110809>
- Corakci, A. & Omay, T. (2023). Renewable Energy, 205, 648–662.
  <https://doi.org/10.1016/j.renene.2023.01.060>
- Pesaran, M.H. (2007). J. Appl. Econometrics, 22, 265–312.
  <https://doi.org/10.1002/jae.951>

## Author

Muhammad Alkhalaf <muhammedalkhalaf@gmail.com>
