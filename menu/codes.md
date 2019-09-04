---
layout: page
title: Codes & Useful Tools
---

Some of the codes that I have developed over the years are published in my github site. I am publishing them for the sake of reproducibility, and also that someone may find them usefull.

### Codes

### [aztools](https://zoghbi-a.github.io/aztools): 
This is a collection of python tools that I have been using over the years in the analysis of Astronomical time series and X-ray telescope data. It handles light curves from X-ray satellites, calculated power and cross/spectra, phase/time lags and related products.

### [plag](https://zoghbi-a.github.io/plag)
This is an implementation of the method used in the [Zoghbi+2013](https://arxiv.org/abs/1308.5852) paper (Astrophysical Journal; 2013. 777. 24Z) to calculate lags in the frequency domain from unevenly-sampled light curves. It uses Gaussian Processes modeling along with Maximum Likelihood optimization. The code is implemented in python/cython.

### [xspec_emcee](https://zoghbi-a.github.io/xspec_emcee): 
This is an implementation of the Goodman & Weare’s [Affine Invariant Markov chain Monte Carlo (MCMC) Ensemble sampler](http://msp.berkeley.edu/camcos/2010/5-1/p04.xhtml) in [XSPEC](https://heasarc.gsfc.nasa.gov/xanadu/xspec/), which is an X-Ray Spectral Fitting Package, distributed as part of the high energy astrophysics software package, [HEASoft](https://heasarc.gsfc.nasa.gov/docs/software/lheasoft/) from NASA. XSPEC has its own implementation of the GW algorithm, but I find it difficult to use, so I created my own implementation, which gives more control on the chains.

### [gr](https://zoghbi-a.github.io/gr): 
A ray tracing code for simulating light rays around a black hole implemented in C++ using gsl.
