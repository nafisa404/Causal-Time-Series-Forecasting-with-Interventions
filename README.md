Causal Time Series Forecasting with Interventions
Electrolux ESOC Project Demo – Nafisa Tahasin

Project Overview
This notebook demonstrates an end-to-end pipeline for causal learning on time series data, focused on real-world applications like marketing, discounting, and retail sales forecasting. The work simulates how strategic decisions impact outcomes using causal interventions (do()-calculus), not just correlations.

Key Components
Synthetic Retail Dataset
Simulates weekly marketing spend, discount rate, competitor pricing, and resulting sales over 120 weeks.

Causal Structure Learning (pgmpy)
Learns a probabilistic graphical model (Bayesian Network) using:

HillClimbSearch + BicScore (preferred)

PC Algorithm (fallback)

Parameter Learning & Inference
Fits the model and performs probabilistic queries like P(sales) or P(sales | marketing=high).

Time Series Forecasting (sktime)
Uses a simple drift-based model to predict future sales in the absence of interventions.

Causal Interventions (do() Simulation)
Applies true causal reasoning by:

Removing parents of marketing_spend and discount_rate

Replacing their CPDs with forced values (do(X=3))

Computing P(sales | do(...)) with VariableElimination

Why It Matters
This demo showcases how causal AI can support decision-making in supply chains and retail by:

Quantifying the impact of strategic actions like discounts or promotions

Forecasting under different causal scenarios

Laying the foundation for integrating causal reasoning into production AI systems
