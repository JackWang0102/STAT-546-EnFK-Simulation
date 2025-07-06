# STAT-546-EnFK-Simulation

## Abstract
State-space models have been extensively used in various fields such as signal processing, economics, and weather forecasting due to their versatility in handling time series data. Among the techniques developed for filtering and state estimation, the Ensemble Kalman Filter (EnKF) has proven to be effective in addressing the challenges of non-linearity and high dimensionality, though it often suffers from issues such as covariance underestimation and filter divergence. Inspired by the Langevinized Ensemble Kalman Filter (LEnKF), this study explores the effects of modifying the Kalman gain computation by replacing the observation noise $R_t$ with $2R_t$ in the EnKF. Through numerical studies on low-dimensional and high-dimensional systems—including the Ornstein-Uhlenbeck model, Van der Pol oscillator, and Lorenz-96 model, we demonstrate that the modified EnKF achieves better uncertainty quantification without compromising state estimation accuracy. These findings suggest the potential for further improvements in ensemble-based filtering methods, particularly in high-dimensional and non-linear systems.


## Main Experiment Results
- Empirically showed the superior uncertainty quantification ability of the proposed improvement, 2R EnKF, without compromising the state estimation.
- Empirically showed the short of coverage of the EnKF.

### Table 1: Ornstein-Uhlenbeck Model  
**Comparison of Kalman Filter (KF) and Ensemble Kalman Filter (EnKF) with Different Ensemble Sizes (Random Seed 701)**

| Method              | Coverage Probability (q=5) | MSE (q=5) | Coverage Probability (q=30) | MSE (q=30) |
|---------------------|-----------------------------|-----------|------------------------------|------------|
| KF                  | 0.94                        | 0.095     | 0.94                         | 0.095      |
| EnKF                | 0.71                        | 0.120     | 0.91                         | 0.096      |
| EnKF with R = 2R    | 0.79                        | 0.110     | **0.93**                         | 0.100      |


### Table 2: Van der Pol Oscillator  
**Comparison of Ensemble Kalman Filter (EnKF) and 2R EnKF with Different Ensemble Sizes (Random Seed 801)**

| Method                          | Coverage Probability (q=30) | MSE (q=30) | Coverage Probability (q=1500) | MSE (q=1500) |
|--------------------------------|-----------------------------|------------|-------------------------------|---------------|
| EnKF $x_{1,t}$               | 0.67                        | 0.63       | 0.65                          | 0.67          |
| EnKF $x_{2,t}$               | 0.69                        | 0.19       | 0.68                          | 0.15          |
| EnKF with R=2R $x_{1,t}$     | 0.66                        | 0.76       | **0.79**                          | 0.88          |
| EnKF with R=2R $x_{2,t}$     | 0.79                        | 0.19       | **0.92**                          | 0.16          |

### Table 3: Lorenz-96 Model  
**Comparison of Ensemble Kalman Filter (EnKF) and 2R EnKF with Different Ensemble Sizes (Random Seed 801)**

| Method                    | Coverage Probability (q=50) | MSE (q=50) | Coverage Probability (q=500) | MSE (q=500) |
|---------------------------|-----------------------------|------------|-------------------------------|-------------|
| EnKF                      | 0.61                        | 32         | 0.88                          | 22          |
| EnKF with R = 2R          | 0.73                        | 22         | **0.95**                          | 11          |
