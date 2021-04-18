---
layout: page
title: Codes & Tools
subtitle: A collection of codes developed over the years
---

Some of the codes that I have developed over the years are published in my github site. I am publishing them for the sake of reproducibility of the published research, and also that someone may find them useful.

Documentations of the codes is usually embedded within the code. From time to time, I write short posts to highlight useful features:

- [aztools](#aztools): A collection of python tools for spectral/timing of X-ray data.
- [fqlag](#fqlag): A python library for modeling time series (light curves) to measure the Fourier frequency-dependent power and time lags using Gaussian Porcesses.
- [xspec_emcee](#xspec_emcee): Affine Invariant Markov chain Monte Carlo (MCMC) Ensemble sampler in XSPEC
- [azTcl](#aztcl): Spectral modeling scripts in tcl to run inside [xspec](https://heasarc.gsfc.nasa.gov/xanadu/xspec/)
- [gr](#gr): Ray tracing code in the curved space-time of for General Relativity


---
---

### [aztools](/aztools)
This is a [collection of python tools](/aztools) that I have been using over the years in the analysis of Astronomical time series and X-ray telescope data. It handles light curves from X-ray satellites, calculated power and cross/spectra, phase/time lags and related products.

Some of the functionality in `aztools.data_tools` can be useful in reducing and calibrating X-ray data from common X-ray telescopes. They organize calls to [heasoft](https://heasarc.gsfc.nasa.gov/docs/software/heasoft/) functionality and allows for reducing multiple datasets in parallel for example.

Examples of using the `aztools` package can be found in the [relevant posts](/tags/#aztools), and in the notebooks associated with [published papers](/publications).

---

### [fqlag](/fqlag)
`fqlag` is a python library to [characterize the variability in the frequency domain of light curves that are not continuously sampled](/fqlag). This supersedes the `plag` library, with a different implementation that is more stable during the calculations.

Both libraries implement the method presented in Zoghbi et. al. (2013) paper ([Astrophysical Journal; 2013. 777. 24](https://arxiv.org/abs/1308.5852)) to calculate periodogram and time/phase lags in the frequency domain from unevenly-sampled light curves.

The following are two examples of using `fqlag`:
- [Calculating frequency-dependent power and time delays](/fqlag/tutorials/getting-started.html)
- [Time Series Forecasting and Interpolation](/2020-03-12-time-series-forecasting-interpolation)


---

### [xspec_emcee](/xspec_emcee)
This is an implementation of the Goodman & Weare’s [Affine Invariant Markov chain Monte Carlo (MCMC) Ensemble sampler](http://msp.berkeley.edu/camcos/2010/5-1/p04.xhtml) in [XSPEC](https://heasarc.gsfc.nasa.gov/xanadu/xspec/), which is an X-Ray Spectral Fitting Package, distributed as part of the high energy astrophysics software package, HEASoft from NASA. 

XSPEC has its own implementation of the GW algorithm, but I find it difficult to use, and sometimes fails to converge, so I created [my own implementation](/xspec_emcee), which gives more control on the MCMC chains.

--- 

### [azTcl](/azTcl)
This repository contains a collection of scripts written in `tcl` to be used within `XSPEC`, [the X-ray spectral modeling package](https://heasarc.gsfc.nasa.gov/xanadu/xspec/). It contains several [useful functions that streamlines some of the `xspec` functionality](/azTcl). Examples of the functions include:

- `az_scan_en_norm` and `az_sim_dchi2`: which can be used for scanning fit residuals for spectral emission or absorption lines and assessing their significance. 
- `az_calc_errors`: Calculate the uncertainties on the fit parameters, making sure to restart if a new fit is found, save progress, and save the final results in clean manner.
- `az_rand_pars`: randomize the parameters given the covariance from the best fit, or give a loaded MCMC chain.
- `az_rand_plot`: Plot a set of models whose parameters are randomly-selected from the best fit parameters and their covariance.
- `az_save_pars`: return a string (`$res`) that has the current parameters, so that they can be loaded again quickly by doing `newpar $res`. 
- `az_best_chain_pars`: return a string (`$res`) of the best parameters from a loaded chain. These parameters can be applied to the model by doing: `newpar $res`.
- `az_plot_unfold`: a clean and easy function to plot the unfoled data, model and their residual and ratio to a [veusz](https://veusz.github.io/)-ready file.
- `az_free_params`: returns a list of free parameters.


---

### [gr](/gr)
A [ray tracing code](/gr) for simulating light rays around a black hole implemented in C++ using gsl. This solves the partial differential equations of the motion of a photon in curved space-time to track how the photons move from around the black hole to the detecting telescope.
