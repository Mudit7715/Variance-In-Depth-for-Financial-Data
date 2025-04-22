# Dynamic Value-at-Risk Engine: An Open-Source Solution for Real-Time Financial Risk Management

**Authors**  
|------------------------|
| Mudit Gupta | 220968094 |
| Vansh Verma | 220911622 |  
| Arjyabir Chatterjee | 220953332 | 
| Tanuj Bajargan | 220911520 |

## Introduction  
The 2008 financial crisis and COVID-19 market collapse exposed critical flaws in traditional Value-at-Risk (VaR) models, which underestimated tail risks due to rigid assumptions like normal return distributions. This project develops an open-source Dynamic VaR Engine combining Monte Carlo simulations with historical volatility scaling, optimized for single-node computation to democratize access to crisis-responsive risk tools for SMEs.

## Objectives  
**Primary Objectives**  
1. **Hybrid VaR Model**: Improve tail risk prediction by ≥20% compared to parametric approaches.  
2. **Computational Efficiency**: Achieve 1-hour VaR updates for 1,000-asset portfolios on consumer hardware.  
3. **Crisis Validation**: Backtest against 2008 and 2020 market crashes.  

**Secondary Objectives**  
- Apache-licensed codebase with Jupyter Notebook tutorials.  
- Seamless transition to distributed systems (e.g., Spark clusters).  

## Methodology  
**Phase 1: Data Infrastructure**  
- **Historical Data**: Collect daily returns for 50 global indices (S&P 500, NIFTY 50) via Yahoo Finance API, stored as Parquet files.  
- **Real-Time Feeds**: Hourly updates using Apache Kafka.  

**Phase 2: Hybrid Model Design**  
1. **Monte Carlo Engine**:  
   - Simulate 10,000 correlated asset paths.  
   - Incorporate stochastic jumps via Merton’s (1976) model.  
2. **Historical Volatility Scaling**:  
   - Apply GARCH(1,1) for volatility regime adjustments.  
   - Use EWMA (λ=0.94) for covariance matrix updates.  

**Phase 3: Validation**  
- **2008 Backtest**: Evaluate VaR estimates from September 12–15, 2008.  
- **COVID-19 Test**: Assess responsiveness to March 2020 VIX surge.

## Workflow
![image](https://github.com/user-attachments/assets/e439035a-c6c2-4db6-9aa3-038d85886efa)


## Expected Results  

| Metric                  | Target        | Baseline (Parametric VaR) |  
|-------------------------|---------------|---------------------------|  
| Tail Risk Accuracy (99% CI) | +22%         | 68%                       |  
| Runtime (1,000 assets)  | ≤1 hour       | 4+ hours                  |  
| Crisis Detection Rate   | 90%           | 60%                       |  

## Potential Limitations  
1. **Data Latency**: yFinance’s 15-minute delay vs. Bloomberg SAPI feeds.  
2. **Hardware Constraints**: Scalability capped at ~1,000 assets.  

## Conclusion  
This open-source framework combines hybrid modeling with single-node optimization to address SME needs in financial risk management. Validated against historical crises, it offers a modular design for future extensions, filling a critical gap in accessible risk analytics. The approach is novel, with no prior single-node implementations combining Monte Carlo and GARCH scaling for SMEs.
