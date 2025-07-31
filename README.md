# Algorithmic Pricing Cognitive Bias Consumer Protection Policy  
*Exploring how cognitive biases in algorithmic pricing affect consumers.*

Algorithmic pricing strategies can exploit cognitive biases such as **anchoring** (fixating on an initial reference price) and **loss aversion** (preferring to avoid losses over acquiring gains).
This project simulates how these biases influence purchasing decisions and evaluates the impact on consumers, focusing on **overpayment** and **consumer surplus**.

> **Tech stack**: Python · pandas · NumPy · Matplotlib · SHAP

---

## The dataset

This project uses a synthetic dataset of transactions with the following key variables:

| Variable          | Description                                                                                 |
|-------------------|---------------------------------------------------------------------------------------------|
| `group`           | Treatment group (Control, Anchoring, LossAversion, Both)                                    |
| `price`           | Actual transaction price                                                                    |
| `fair_price`      | Estimated fair price without treatment cues                                                 |
| `overpayment`     | `price - fair_price` (amount paid above the fair price)                                     |
| `consumer_surplus`| `fair_price - price` (when positive, the consumer’s gain)                                   |
| `income_decile`   | Income group of the consumer (1 = lowest, 10 = highest)                                     |
| `WP`              | Whether consumer was exposed to bias cues (1 = yes, 0 = no)                                 |

---

## The analysis includes

- **Counterfactual Simulation** – Simulating counterfactual prices (what prices would have been without any bias cues) for treated groups and computing treatment effects using a Difference-in-Differences (DID) approach.  
- **Welfare Metrics per Income Group** – Estimating consumer overpayment and consumer surplus for each income decile to see how different income groups are affected.  
- **Risk Distribution** – Visualizing the distribution of overpayment and calculating risk metrics (e.g. the fraction of transactions where overpayment exceeds a certain threshold) to identify potential consumer harm.  
- **Model Interpretability** – Using SHAP (SHapley Additive exPlanations) to interpret the influence of different features and biases on pricing outcomes, helping to explain how cognitive biases impact prices.

---

*Note: This project is intended to inform consumer-protection policy by highlighting how bias-influenced pricing algorithms can affect consumer welfare.
Because of program-related confidentiality, this repository reproduces the methodology on **simulated data only**; results are illustrative and for reference purposes.*









