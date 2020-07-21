# Image: rstudio

This is a fork from `rocker/rstudio:3.6.3` and the original Dockerfile is
available
[here](https://github.com/rocker-org/rocker-versioned/blob/master/rstudio/3.6.3.Dockerfile).

We are rebuilding it to use our custom base image `agresearch\r-ver:3.6.3` and
shiny is deployed by default. This is required to support third-party and
private R packages that cannot be installed on top of community images because
their base OS is too recent.
