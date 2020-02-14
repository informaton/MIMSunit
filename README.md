
<!-- README.md is generated from README.Rmd. Please don't edit that file -->

# MIMS-unit algorithm

![Pkgdown](https://github.com/mHealthGroup/MIMSunit/workflows/Pkgdown/badge.svg?branch=master)
![.github/workflows/test.yml](https://github.com/mHealthGroup/MIMSunit/workflows/.github/workflows/test.yml/badge.svg)
[![CRAN
Status](https://www.r-pkg.org/badges/version/MIMSunit)](https://cran.r-project.org/package=MIMSunit)

**Please create github
[issues](https://github.com/mhealthgroup/MIMSunit/issues/) if you have
any question related to the package.**

## Short introduction

MIMS-unit is abbreviated for *Monitor Independent Movement Summary*
unit. This measurement is developed to harmonize the processing of
accelerometer data from different devices. You may refer to the
[manuscript](https://doi.org/10.1123/jmpb.2018-0068) for the detail
description of the algorithm.

## Copyright and citation

The copyright of the work belongs to Northeastern University, [mHealth
Research Group](https://mhealthgroup.org). Please kindly [cite the
manuscript](https://mhealthgroup.github.io/MIMSunit/authors.html) if you
have used the package or referred to the algorithm in your work.

## System Requirements

1.  R (\>= 3.6.0)
2.  memory (\> 4GB)

### For Windows

Rtools 3.5 (see: <https://cran.r-project.org/bin/windows/Rtools/>)

### For Linux (use ubuntu as an example)

Install dependency system packages for `devtools`: `build-essential`,
`libcurl4-gnutls-dev`, `libxml2-dev`, `libssl-dev`.

## Installation

1.  Stable version on CRAN (bundled or binary)

*Coming soon…*

2.  Development version (source codes)

<!-- end list -->

  - For Windows users  

<!-- end list -->

``` r
install.packages("devtools")
devtools::install_github("mhealthgroup/MIMSunit", type='win.binary')
```

  - For mac or Linux users  

<!-- end list -->

``` r
install.packages("devtools")
devtools::install_github("mhealthgroup/MIMSunit")
```

*Note: It is recommended to use Rstudio when installing the package,
because `devtools` has some compatible issues with R command line
interface.*

## Usage

``` r
MIMSunit::mims_unit(input_dataframe, dynamic_range=c(-3,3), epoch='1 min')
```

Assume the input dataframe is in following format, with the first column
(timestamp) in `POSXlct` objects and the device used to collect this
data has dynamic range being -3g to 3g. You may set the epoch length to
be `1 min`, `1 sec`, `5 sec`, `10 sec` and so on.

    HEADER_TIME_STAMP,X,Y,Z
    2016-10-03 14:51:14.236,0.007,-0.005,0.984
    2016-10-03 14:51:14.256,0.008,-0.007,0.981
    2016-10-03 14:51:14.276,0.009,-0.006,0.978
    2016-10-03 14:51:14.297,0.009,-0.007,0.984
    2016-10-03 14:51:14.317,0.010,-0.010,0.982
    2016-10-03 14:51:14.337,0.011,-0.010,0.982
