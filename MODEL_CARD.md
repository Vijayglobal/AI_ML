Model Card: Surrogate-Based BBO Optimisation Strategy

1) Overview
Model Name: Iterative Surrogate-Based BBO Strategy  
Version: Stage 2 – Round 10  
Model Type: Hybrid surrogate optimisation framework (GP, SVR, Neural Network ensembles)

2) Intended Use
This approach is designed to propose query points for black-box optimisation problems where evaluations are expensive and data is scarce.  
It is suitable for research, benchmarking and educational purposes.

3) Not intended for:
- Safety-critical systems
- Real-world deployment without domain validation
- Decision-making affecting individuals or communities

4) Strategy Details
Across ten optimisation rounds, the approach evolved as follows:
- Early rounds: Emphasised exploration using smoother surrogate models (Gaussian Processes, SVR) in low-dimensional spaces.
- Mid rounds: Introduced hybrid acquisition strategies combining predicted mean, novelty and local sensitivity.
- Later rounds: Adopted neural network ensembles for higher-dimensional functions (3D–8D), using Sobol candidate sampling, trust-region biasing and soft boundary penalties.
Decision-making prioritised transparency, with explicit decomposition of acquisition scores into interpretable components.

5) Performance Summary
Performance was evaluated using:
- Surrogate fit metrics (RMSE and R² on observed points).
- Improvement trends in observed objective values across rounds.
- Stability of predictions across ensemble members.
Given the small data regime, performance assessment focused on qualitative trends rather than absolute accuracy.

6) Assumptions and Limitations
Assumptions:
- Local smoothness near high-performing regions.
- Surrogate predictions are informative despite limited data.
- Exploration penalties and trust regions meaningfully guide optimisation.

7) Limitations:
- Very small sample sizes per function.
- Approximate uncertainty estimation for neural networks.
- Potential bias toward early-discovered regions of the search space.
- Computational constraints limit ensemble size and candidate evaluations.

8) Ethical and Transparency Considerations
All optimisation decisions are logged and reproducible.  
The model card and datasheet document assumptions, limitations and intended use to prevent misuse.  
Although the dataset is synthetic, the approach reflects responsible ML practices applicable to real-world optimisation problems.

9) Future Improvements
- Incorporation of calibrated uncertainty estimates for neural networks.
- Adaptive trust-region sizing.
- More systematic exploration strategies for high-dimensional spaces.
