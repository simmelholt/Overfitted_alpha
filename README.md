[README.md](https://github.com/user-attachments/files/31417438/README.md)
## Shrinking the Cross-Section (SCS) Factor Model

The SCS notebook implements the L2-shrinkage (ridge-type) estimator from **Kozak, Nagel, and Santosh (2019), "Shrinking the Cross-Section"**, which estimates a stochastic discount factor (SDF) as a regularized combination of a large set of candidate return factors rather than relying on a small hand-picked set.

The method works by:

- De-marketing excess returns
- Estimating SDF coefficients across a grid of shrinkage (L2 penalty / kappa) values
- Selecting the optimal shrinkage level via k-fold cross-validation (maximizing out-of-sample cross-sectional R²)
- Producing diagnostic plots (coefficient paths, t-statistics, degrees of freedom, and CV objective curves) and a summary table of the largest/most significant coefficients

The data used here are **Goldman Sachs factor portfolios**, applied as the set of candidate anomaly/factor returns fed into the shrinkage estimation. Since these GS portfolios are **updated daily**, the model can be re-estimated on a rolling basis with fresh data, giving it genuine real-world applicability.
