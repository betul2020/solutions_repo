# Problem 1
Exploring the Central Limit Theorem through Simulations

1. Motivation

The Central Limit Theorem (CLT) is a fundamental concept in statistics, asserting that the sampling distribution of the sample mean approaches a normal distribution as the sample size $n$ increases, regardless of the population's underlying distribution. This task uses simulations to demonstrate the CLT, providing an intuitive understanding of its implications.

2. Simulating Sampling Distributions

We select three distinct population distributions to explore the CLT:





Uniform Distribution: Values in the range $[0, 10]$.



Exponential Distribution: With rate parameter $\lambda = 1$.



Binomial Distribution: With parameters $n = 10$ and $p = 0.5$.

For each distribution, we generate a large population dataset of 10,000 data points to simulate real-world scenarios.

3. Sampling and Visualization

For each population, we:





Draw random samples of sizes $n = 5, 10, 30, 50$.



Compute the sample mean for each sample.



Repeat this process 1,000 times to construct the sampling distribution of the sample mean.



Plot histograms of the sample means to visualize convergence to a normal distribution.

4. Parameter Exploration

Shape and Sample Size

The shape of the population distribution affects the rate of convergence:





Symmetric distributions (e.g., uniform, binomial) converge faster.



Skewed distributions (e.g., exponential) require larger sample sizes for normality.

Variance Impact

The variance of the sampling distribution is $\frac{\sigma^2}{n}$, where $\sigma^2$ is the population variance. Larger $n$ reduces the spread, and populations with larger $\sigma^2$ result in wider sampling distributions.

5. Implementation: Python Simulation

Below is a Python script that implements the simulations and visualizations using NumPy for data generation and Matplotlib/Seaborn for plotting.

 import numpy as np import matplotlib.pyplot as plt import seaborn as sns

Set random seed for reproducibility

np.random.seed(42)

Generate population datasets

population_size = 10000 uniform_pop = np.random.uniform(0, 10, population_size) # Uniform [0, 10] exponential_pop = np.random.exponential(scale=1, size=population_size) # Exponential, lambda=1 binomial_pop = np.random.binomial(n=10, p=0.5, size=population_size) # Binomial, n=10, p=0.5

Store populations

populations = { 'Uniform': uniform_pop, 'Exponential': exponential_pop, 'Binomial': binomial_pop }

Simulation parameters

sample_sizes = [5, 10, 30, 50] num_samples = 1000 # Number of samples for each sample size

Plotting

plt.figure(figsize=(15, 12)) plot_idx = 1

for dist_name, population in populations.items(): for sample_size in sample_sizes: # Compute sample means sample_means = [np.mean(np.random.choice(population, sample_size)) for _ in range(num_samples)]



    # Plot histogram with KDE
    plt.subplot(len(populations), len(sample_sizes), plot_idx)
    sns.histplot(sample_means, bins=30, kde=True, stat='density')
    plt.title(f'{dist_name}\nSample Size = {sample_size}')
    plt.xlabel('Sample Mean')
    plt.ylabel('Density')
    plt.tight_layout()
    plot_idx += 1
