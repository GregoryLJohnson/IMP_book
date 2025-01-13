# Ising Model as a Playground

Consider the classical 2D Ising Hamiltonian
\begin{eqnarray*}
\mathcal{H}[\{s_i\}]=-J\,\sum_{NN} s_i\,s_j- H\,\sum\,s_i
\end{eqnarray*}
for a given configuration of spins $\{s_i\}$ on an $L^2$ lattice with periodic boundary conditions and nearst neighbor (NN) interactions. We will use Monte-Carlo techniques to simulate the partition function 
\begin{eqnarray*}
\mathcal{Z}=\exp\left(-\beta \sum_{\{s_i\}} \mathcal{H}[\{s_i\}]\right)
\end{eqnarray*}

In this notebook, we will examine aspects of Markov Chain Monte Carlo. Then using the simulated data, test various data analysis techniques. The idea of this notebook is to tie together the physics of the Ising model, Monte Carlo simulations, and statistical analysis into one project. Below we give a rough sketch of the outline of this project.

__Overview of ideas:__
1. Exact computation of Ising model for small lattices - L = 2,3,4
    - Generation of configurations, thermodynamic functions, density of states, energy distributions
    - Computational complexity - basic algorithm scaling
    - Zeros of partition functions - complex H and complex T
2. Markov Chain Monte Carlo
    - Implementations: Metropolis-Hastings, Swedsen-Wang, Wolff, Heatbath, and Wang-Landau
    - Diagnostics of MCMC: equilibriation, trace plots, initial condition dependence, autocorrelation
    - Error analysis: benchmarking against exact results, effective sample size, thinning, batching, jackknife, bootstrap
    - Extensions: rewighting (multiple histogram reweightings), parallel tempering, simulated annealing
3. Statistical methodology playground:
    - PCA on raw spin configurations and on the energy-order parameter phase space (E,M)
    - Maximum likelihood, fisher information, and estimation of the temperature
    - Multiple layer perceptron for classifying phases
    - Logistic regression for $J$.

__Sources:__
1. [Bryan Clark - Computing in Physics (Course notes)](https://clark.physics.illinois.edu/html/Ising/Measure.html) For details on implementation and RG 
<!-- 2. [here](https://sites.physics.wustl.edu/gradcomputer/wiki/images/6/63/Ising_notes_v2.pdf) ( not acutally used ) -->
3. [Prof. Bernd A. Berg - Markov Chain Monte Carlo Simulations (Course notes)](http://www.hep.fsu.edu/~berg/teach/mcmc08/material/lecture07mcmc3.pdf) For detatils on autocorrelation time. See full [text](https://www.amazon.com/Markov-chain-simulations-statistical-analysis/dp/9812389350) for many details on implementation for statistical systems - __likely the best resource in that regard__.
5. __Ross - Introduction to Probability Models__: For general properties of Markov Chains
6. __Barbu and Zhu - Monte Carlo Methods__: For a techinical definiton and aspects of the Metropolis Hastings Algorithm; underlying notions of detailed balance and stationarity; and the relevance of the Perron–Frobenius theorem
7. __Casella and Bergman - Statistical Inference__: For details on maximum likelihood estimation, likelihood ratio tests, and Fisher information/Cramer-Rao bound.
8. __Carl Sigman -__ [__Lecture Notes on Stochastic Modeling I, Section 4__](http://www.columbia.edu/~ks20/stochastic-I/stochastic-I.html): For general properties of Markov Chains, particularly the effect of aperiodicity.
9. __Timothy Budd - Monte Carlo Techniques__: Jupyter book and lecture notes. Discussion of Wolff algorithm and Monte Carolo error analysis.
10. __Kari Rummukainen - Monte Carlo simulation methods:__ [webpage](https://www.mv.helsinki.fi/home/rummukai/lectures/montecarlo_oulu/) - rewighting, error analysis

__Additional sources:__
1. See my handwritten notes
2. My notebook on statistical models
3. Perplexity AI

```{tableofcontents}
```
