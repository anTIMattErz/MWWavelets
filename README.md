# MWWavelets
Code presented for my honors physics thesis at the University of Oregon, June 2017. Contains methods for performing wavelet analyses on Northeastern US climate data derived from the USHCN dataset.

# Contents
* MWWavelets_GitHub - Jupyter notebook containing all of the methods used to analyze the USHCN data in my thesis. Includes my implementation of the Morlet and Harr wavelets and methods for the continuous wavelet transform.
* Examples_GitHub - Jupyter notebook with examples of how to access data from the database I made for the thesis including plotting/processing individual station data. I also included plots of the transforms for the NE US region as a whole, and comparisons between the regions West and East of the Appalachians.
* Thesis.pdf - a copy of my submitted thesis. 
* Plot folders - collection of various plots from various stages of the research.

# Motivation and Background
Climate data is full of periodic trends corresponding to many different physical phenomena. Traditionally, Fourier analysis is used to identify periodic behavior in data, but Fourier transforms consider the entire dataset at once and are not able to identify localized behavior. The windowed Fourier transform helps solve this problem by analyzing subsets of the data, but the windowing process introduces bias into the results. A better alternative are wavelet transforms, which are essentially a generalization of the Fourier transform. Wavelet transforms are designed to detect localized signals, and are more flexible than Fourier transforms (can choose wavelets to detect different signals). This makes them ideal for studying time-dependent behavior in climate data. 

For a more detailed introduction and analysis, please see the thesis.

# Methods
I primarily used the Morlet wavelet to extract time-dependent periodic trends from the climate dataset. We had a collection of 137 weather stations from the NE US region with data from 1900-2015. Each station had monthly averaged data for maximum and minimum temperatures and precipitation, which we z-scored to combine together for a climate index. 

The Morlet wavelet corresponds to sinusoidal periodic trends of varying periods. 

<img src="/Figures/sampled_morlet_wavelet.png" height="250">

This gives us a series of wavelet coefficients that we can plot to identify the presence of periodic trends in the data:

<img src="/Figures/avg_nei_data_with_wavelet_coefficients_all_stations.png" height="700">

I was also interested in seeing if the Harr wavelet gave useful results, but climate data is too noisy and the Harr wavelet generally returned a mess. 

# Future Work and Notes
The techniques used for performing rigorous statistical analyses on wavelet coefficients (confidence intervals) require assumptions that the z-scored data does not meet. The raw data may meet these requirements, but I only recently was able to reassemble the USHCN data for the stations we used (the USHCN dataset is no longer supported and was moved to be a subset of the GHCN). I also tried using Monte Carlo simulations to generate profiles for various noise-signal combinations, but ultimately a rigorous analysis of the raw data would be more enlightening.

Contact @ mitwomack at gmail dot com
