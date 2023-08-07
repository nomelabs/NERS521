---
date: "2022-03-23"
diagram: true
image:
  caption: 'NERS521'
  placement: 1
math: true
title: A quick webpage for calculating dpa;
---


#NERS521

##Calculating dpa Cheat Sheet

###Displacement cross section integrals

For simple, hard sphere elastic interactions the maximum energy transfer, $\hat{T}$, is given as,

$$\hat{T}=\gamma E_i$$

where,

$$\gamma=\frac{4M_1M_2}{( M_1+M_2 )^2}$$

See Chapter 1.1.1 of Was, 2nd Edition for derivations. We then need to compare $\hat{T}$ with the displacement energy, $E_d$ and the electronic cutoff energy, $E_c$. Based on where $\hat{T}$ lands within these ranges, we can determine the displacement cross section, $\sigma_d(E_i)$. For simple calculations assuming isotropic, elastic scattering using the [Kinchin-Pease model](#KPmodel) we can use simple "if-then" logic to determine the displacement cross section:

If $\hat{T} \ < \ E_d$, then

$$\sigma_d(E_i) = \frac{\sigma_s(E_i)}{\gamma E_i}\int_{\check{T}}^{\hat{T}}\upsilon(T) \ dT=\frac{\sigma_s(E_i)}{\gamma E_i}\int_{\check{T}}^{\hat{T}}0 \ dT=0$$

$$\therefore \ \sigma_{D}(E_{i})=0$$

If  $\ E_d < \hat{T} \ < 2E_d$, then

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\int_{0}^{E_d} \upsilon(T) \ dT + \int_{E_d}^{\hat{T}} \upsilon(T) \ dT \right) =\frac{\sigma_s(E_i)}{\gamma E_i}\left(0 + \int_{E_d}^{\hat{T}}1 \ dT \right) $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\hat{T} - E_d \right)=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\gamma E_i - E_d \right)=\sigma_s(E_i)\left(1-\frac{E_d}{\gamma E_i}\right)$$

$$\therefore \ \sigma_{D}(E_{i})=\sigma_s(E_i)\left(1-\frac{E_d}{\gamma E_i}\right)$$

If  $\ 2E_d < \hat{T} \ < 2E_c$, then

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\int_{0}^{E_d} \upsilon(T) \ dT + \int_{E_d}^{2E_d} \upsilon(T)  \ dT + \int_{2E_d}^{\hat{T}} \upsilon(T) \ dT\right) $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\int_{0}^{E_d}0 \ dT + \int_{E_d}^{2E_d}1 \ dT + \int_{2E_d}^{\hat{T}}\frac{T}{2E_d}dT\right) $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(0 + E_d+ \frac{\hat{T}^2 - \left( 2E_d\right)^2}{4E_d} \right) =\frac{\sigma_s(E_i)}{\hat{T}} \left(\frac{\hat{T}^2}{4E_d} \right)$$

$$\therefore \sigma_{D}(E_{i})=\sigma_s(E_i) \left(\frac{\gamma E_i}{4E_d} \right)$$

If  $\hat{T} \ > 2E_c$, then

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\int_{0}^{E_d} \upsilon(T) \ dT + \int_{E_d}^{2E_d} \upsilon(T)  \ dT + \int_{2E_d}^{E_c} \upsilon(T) \ dT + \int_{E_c}^{\hat{T}} \upsilon(T) \ dT\right)  $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(\int_{0}^{E_d}0 \ dT + \int_{E_d}^{2E_d}1 \ dT + \int_{2E_d}^{E_c}\frac{T}{2E_d}dT + \int_{E_c}^{\hat{T}}\frac{E_c}{2E_d}dT \right) $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(0 + E_d+ \frac{{E_c}^2 - \left( 2E_d\right)^2}{4E_d} + \frac{E_c}{2E_d}\left(\hat{T} - E_c \right) \right) $$

$$\sigma_{D}(E_{i})=\frac{\sigma_s(E_i)}{\gamma E_i}\left(0 + E_d+ \frac{1}{2E_d}\frac{{E_c}^2 - \left( 2E_d\right)^2}{2} + \frac{E_c}{2E_d}\left(\gamma E_i - E_c \right) \right) $$

$$\therefore \sigma_{D}(E_{i})=\sigma_s(E_i) \left(\frac{E_c}{2E_d} \right)\left(1- \frac{E_c}{2 \gamma E_i} \right)$$

### The Kinchin-Pease model for displacements <a id="KPmodel"></a>

The Kinchin-Pease (K-P) model is a simplified estimate of the number of displaced atoms ($N_d$) per PKA[^2] by means of the simple set of proposed relationships:

$N_d = \begin{cases}
  0 & \text{for }0< E<E_d\\\  
  1 & \text{for }E_d<E<2E_d\\\\
  \frac{E} {2E_d} &   \text{for }2E_d<E<E_c\\\\
  \frac{E_c} {2E_d} & \text{for }E_c<E\\\
\end{cases}$

Where $E$ is the energy of the PKA and $E_d$ is the threshold energy. At energies above $E_c$, the recoils lose energy only by electron excitation, while below $E_c$ the energy transfer and loss is controlled by hardsphere elastic interactions (e.g. scattering). Note, the simplified model does not account for the effects due to the crystal lattice (e.g. crystal structure effects) for either single interactions or more complex damage cascades.
