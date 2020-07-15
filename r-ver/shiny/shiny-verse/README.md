# Image: shiny-verse

This is a fork from `rocker/shiny-verse:3.6.3` and the original Dockerfile is
available
[here](https://raw.githubusercontent.com/rocker-org/shiny/master/Dockerfile).

We are rebuilding it to use our custom base image `agresearch\shiny:3.6.3`
without any additional changes. This is required to support third-party and
private R packages that cannot be installed on top of community images because
their base OS is too recent.
