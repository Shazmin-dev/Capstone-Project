#Model Card: Adaptive GP-UCB Optimiser

#Overview

Name: Adaptive Gaussian Process Optimiser (GP-UCB)
Type: Bayesian Optimisation Surrogate Model

This model implements an adaptive Gaussian Process Upper Confidence Bound (GP-UCB) strategy for efficient optimisation under strict query constraints. The approach evolves over time by dynamically adjusting exploration–exploitation behaviour based on observed function landscapes.

#Intended Use

This model is designed for optimising continuous, expensive-to-evaluate black-box functions in low-to-moderate dimensional settings (≤ 8 dimensions) where evaluation budgets are limited.

#Recommended use cases:

Hyperparameter tuning for machine learning models
Scientific simulations with costly evaluations
Engineering design optimisation problems

#Not recommended for:

High-dimensional optimisation tasks > 20 dimensions
Real-time or latency-sensitive systems
Scenarios requiring rapid or large-scale parallel evaluations
Methodology

The optimiser is built on a Gaussian Process Regressor (via scikit-learn) using a Matern kernel with dynamically bounded parameters (ν = 1.5 or 2.5).

A key feature of this approach is the adaptive tuning of the exploration parameter (β) in the GP-UCB acquisition function:

Early stages: higher β (e.g., 5.0) to encourage exploration
Later stages: lower β (e.g., 0.01) to prioritise exploitation

Over the course of ten optimisation rounds, the strategy evolved from static exploration to context-aware adaptation, where β was manually adjusted based on observed landscape characteristics (e.g., flat regions vs. sharp peaks).

#Performance

Performance was evaluated based on the maximum objective value identified for each function.

#Strengths:

Strong performance on functions with clear gradients and well-defined optima
Achieved high peak values on:
Function 5: 1012.90
Function 8: 9.18

#Weaknesses:

Reduced effectiveness on flat or deceptive landscapes (e.g., Function 1)
Performance variability due to sensitivity to early sampling decisions
Assumptions and Limitations

#Assumptions:

The objective function is continuous and reasonably smooth
Local structure can be approximated effectively by a Gaussian Process

#Limitations:

Curse of dimensionality: Performance degrades as dimensionality increases
Limited query budget: With only 10 evaluations, the model cannot fully explore higher-dimensional spaces (6D–8D)
Local optima risk: Aggressive exploitation increases the likelihood of getting trapped in suboptimal regions
Initialisation sensitivity: Early samples strongly influence the optimisation trajectory
Ethical Considerations and Transparency

This model emphasises transparency and reproducibility by explicitly documenting weekly adjustments to the exploration parameter (β).

By making these decisions visible, the project highlights:

The practical trade-offs between exploration and exploitation
The impact of human-in-the-loop optimisation decisions
The uncertainty inherent in optimisation under limited information

This transparency supports reproducibility and provides insight into real-world optimisation challenges where perfect information is unavailable.
