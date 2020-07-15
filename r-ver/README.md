# Image: r-ver

This is a fork from `rocker/r-ver:3.6.3` and the original Dockerfile is available [here](https://raw.githubusercontent.com/rocker-org/rocker-versioned/master/r-ver/3.6.3.Dockerfile).

Two main customisations are added to our build:

1. Replace the base image from `debian:buster` to `debian:stretch`, which is older.  Debain Stretch is the last Debian distribute that support libgfortran-3 and that is required by some of Shiny apps we need to support.

2. Pin R to install packages from a snapshot of CRAN taken on 2019-04-26, just before R4.0 was released.  The date pined by the original image seems to cause many dependency conflicts when deploying packages required by Shiny apps we need to support.
