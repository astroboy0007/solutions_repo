# Problem 1

# Exploring the Central Limit Theorem through simulations

## Motivation
The Central Limit Theorem (CLT) is a cornerstone of probability and statistics, stating that the sampling distribution of the sample mean approaches a normal distribution as the sample size increases, regardless of the population’s original distribution. Simulations provide an intuitive and hands-on way to observe this phenomenon in action.


This is an exciting project to explore the Central Limit Theorem (CLT)! Here's how you can break it down and implement it step by step in Python:

Step 1: Simulating Sampling Distributions
Start by generating data for three distinct population distributions:
1. **Uniform distribution**: Use `numpy.random.uniform`.
2. **Exponential distribution**: Use `numpy.random.exponential`.
3. **Binomial distribution**: Use `numpy.random.binomial`.

For example:
```python
import numpy as np

# Generating populations
uniform_population = np.random.uniform(0, 10, 10000)
exponential_population = np.random.exponential(5, 10000)
binomial_population = np.random.binomial(20, 0.5, 10000)
```

Step 2: Sampling and Visualization
Create a function to:
- Draw random samples of different sizes.
- Compute the sample mean multiple times.
- Plot histograms of sample means.

```python
import matplotlib.pyplot as plt

def sampling_distribution(population, sample_sizes, num_samples=1000):
    for size in sample_sizes:
        sample_means = [np.mean(np.random.choice(population, size, replace=False)) for _ in range(num_samples)]
        plt.hist(sample_means, bins=30, alpha=0.7, label=f'Sample Size: {size}')
    
    plt.title('Sampling Distribution')
    plt.xlabel('Sample Mean')
    plt.ylabel('Frequency')
    plt.legend()
    plt.show()

# Example usage
sample_sizes = [5, 10, 30, 50]
sampling_distribution(uniform_population, sample_sizes)
```
![alt text](image.png)

Step 3: Parameter Exploration
Analyze how different population shapes and variances affect the rate of convergence to normality. Experiment with changing:
- The range of the uniform distribution.
- The scale parameter of the exponential distribution.
- The number of trials and probability in the binomial distribution.

Step 4: Reflecting on Real-World Applications
Discuss how the CLT applies in practical contexts. For instance:
- **Estimating population parameters**: The CLT allows confidence intervals and hypothesis tests to be applied even if the population distribution is unknown.
- **Quality control**: Understanding the distribution of sample means helps ensure manufacturing processes stay within control limits.
- **Financial models**: Aggregating returns over time benefits from CLT, assuming independence and identical distributions.
