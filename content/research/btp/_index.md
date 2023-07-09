---
title: "Applications of q-statistics with Big Bang Nucleosynthesis"
date: 2022-04-20T18:08:10+05:30
layout: "simple"
---
{{< katex >}}

## Abstract
In this project, we used the framework of Tsallis non-extensive statistics (q-statistics) to modify the
Maxwell-Boltzmann velocity distribution of nucleons to calculate the primordial abundances of light
elements during big bang nucleosynthesis. Using the best-fit curves of the S-factor as a function of
temperature for 12 primary reactions in the reaction network, we calculated the new reaction rates using
the non-extensive Tsallis framework. The abundances of light nuclei were computed using a BBN code, and
the impact of this q-parameter and the drawbacks of this model were discussed. By adding a non-extensive
parameter (q), the abundances of primordial abundances of light nuclei were in better agreement with the
observed values. The predictions can be improved by using a more vast code that includes additional
reactions along with their reverse reaction rates, where all the rates are calculated in the Tsallis framework.
But even with the limitations of this project, we observed that the abundances of elements like Lithium
were better predicted in this non-extensive framework.

## A Brief Description
Big-bang nucleosynthesis (BBN) describes the production of the lightest nuclides, such as elements like H, He, Li, and Be, during the first seconds of cosmic time. But, the current theory overestimates the abundance of 7Li. The generally accepted prediction for Lithium abundance is \\( ^{7}Li/H = (4.68 \pm 0.67)10^{-10} \\), which is about three times greater than the widely accepted central value of observations, \\( ^{7}Li/H = (1.58 \pm 0.30)10^{-10} \\). And Tsallis's statistics can be helpful in solving this.

The idea is to use a generalized version of the Maxwell-Boltzmann Distribution to estimate these abundances. The concept was introduced in 1988 by Constantino Tsallis as a basis for generalizing the standard statistical mechanics. 

The Maxwell-Boltzmann velocity distribution for one particle is given by:
$$
f_{MB}(v)=\left(\frac{m}{2\pi k_{B}T}\right)^{3/2}exp\left(-E/k_{B}T\right) 
$$ 
And the Tsallis distribution is given by:
$$
f_{q}(v)=B_{q}\left(\frac{m}{2\pi k_{B}T}\right)^{3/2}\left[1-(q-1)\frac{E}{k_{B}T}\right]^{1/q-1}
$$
Where \\( B_{q} \\) is a normalization constant determined from the requirement \\( \int f_{q}(v_{i})dv_{i}=1 \\) and is given by:
$$
    B_{q}=(q-1)^{1/2}\left(\frac{3q-1}{2}\right)\left(\frac{1+q}{2}\right)\frac{\Gamma(\frac{1}{2}+\frac{1}{q-1})}{\Gamma(\frac{1}{q-1})}\left[\frac{m}{2\pi k_{B}T}\right]^{3/2}
$$

You can also construct the q-Deformed Planck Distribution equation for photon-induced reactions. Now, you calculate the abundances with this new distribution using the same steps with standard maxwell distribution.

For a charged particle reaction: \\(1+2\rightarrow3+4\\), the reaction rate is given by:
$$r_{12}=N_{1}N_{2}\left< \sigma(v) v\right>$$
Where v is the relative velocity of the particles 1 and 2, \\(N_{1}\\) and \\(N_{2}\\) are the number of particles of 1 and 2 per unit volume, $\sigma$ is the cross-section, and \\(\left< \sigma v\right>\\) is the average reaction rate per particle pair.
Since the particles will have a velocity distribution, in order to calculate \\( \left< \sigma v\right> \\), we have to
integrate it over a velocity distribution.
$$\left< \sigma v\right>=\int f^{rel}(\boldsymbol{v})v\sigma(v)dv$$

The relation between \\(\sigma(E)\\) and \\(S(E)\\)is:
\begin{equation}
    \sigma(E)=\frac{1}{E}S(E)e^{-2\pi\eta}
\end{equation}

A detailed derivation is given in Chapter 3 of C. Iliadis. Nuclear Physics of Stars. We can derive \\(f^{rel}_{q}(v)\\) from the \\( f _{q}(v)\\) mentioned before. For the Tsallis distribution, the new rate equation becomes:

\begin{equation}
    \left< \sigma v\right>= \left( \frac{8}{\pi\mu} \right)^{1/2}\frac{1}{(k_{B}T)^{3/2}} \int e^{-2\pi\eta} S(E) f^{rel}_{q}(E)dE
\end{equation}

Using the best-fit curves of the S-factor for 12 primary reactions in the reaction network, we calculated the new reaction rates using the non-extensive Tsallis framework. The abundances of light nuclei were calculated using a BBN code, and the impact of this q-parameter and the drawbacks of this model were discussed. By adding a non-extensive parameter (q), the abundances of primordial abundances of light nuclei were in better agreement with the observed values. The predictions can be improved by using a more vast code that includes additional reactions along with their reverse reaction rates, where all the rates are calculated in the Tsallis framework. But even with the limitations of this project, we observed that the abundances of elements like Lithium were better predicted in this non-extensive framework. This experience vastly improved my understanding of nucleosynthesis and enriched my computational skills, playing a crucial role in maturing me as a researcher.