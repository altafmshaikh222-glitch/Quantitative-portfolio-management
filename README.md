# Portfolio Optimization & Minimum Variance Analysis
A Python implementation of Modern Portfolio Theory (Markowitz) using SciPy's `SLSQP` optimizer to construct optimal asset allocation strategies across 15 equity assets and a market benchmark.

## Features & Methodology

1. **Data Preprocessing & Correlation Matrix Analysis**
   - Cleaned daily asset returns and dropped market benchmark columns for covariance calculations.
   - Built full and lower-triangular correlation matrices (`np.tril`) to evaluate diversification potentials across assets.

2. **Constrained Portfolio Optimization (`scipy.optimize.minimize`)**
   - Objective Function: Portfolio Variance $w^T \Sigma w$
   - Constraints: Fully invested portfolio ($\sum_{i=1}^{n} w_i = 1$)
   - Bounds: Long-only positions ($0 \le w_i \le 1$)
   - Algorithm: Sequential Least Squares Programming (`SLSQP`)

3. **Performance Metrics & Optimization Outcomes**

| Benchmark / Portfolio | Expected Return | Annualized Risk (Std Dev) |
| :--- | :---: | :---: |
| **Initial Portfolio** | 20.69% | 19.00% |
| **Market Benchmark** | 13.80% | 16.96% |
| **Minimum Variance Portfolio (MVP)** | **13.15%** | **12.51%** |
| **Target Risk = Market Risk** | **28.11%** | **16.96%** |

## Optimal Weights (Minimum Variance Portfolio)
* **JNJ**: 31.95%
* **PG**: 24.28%
* **WMT**: 17.06%
* **JPM**: 8.12%
* **MSFT**: 4.69%
* **UNH**: 4.07%
* **GOOGL**: 2.29%
* **MA**: 2.05%
* **HD**: 1.73%
* **V**: 1.66%
* **NVDA**: 1.16%
* **AMZN**: 0.94%

## Dependencies
* `python 3.14+`
* `pandas`
* `numpy`
* `scipy`
