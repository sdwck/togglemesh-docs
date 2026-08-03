# Claims: ab-testing-mab.mdx

- **[CLAIM-MAB-001]** Feature Flags can be converted into Experiments linked to a Metric.
- **[CLAIM-MAB-002]** An Exposure is recorded when a user evaluates a flag.
- **[CLAIM-MAB-003]** A Track event is recorded when a user triggers a metric.
- **[CLAIM-MAB-004]** ToggleMesh uses Bayesian Statistics rather than Frequentist (p-value) math for experiments.
- **[CLAIM-MAB-005]** Binary conversion goals use a Beta Distribution.
- **[CLAIM-MAB-006]** Beta Distribution uses Monte Carlo sampling with 10,000+ iterations to calculate probability Variation B beats Variation A.
- **[CLAIM-MAB-007]** Revenue or continuous metrics calculate Variance.
- **[CLAIM-MAB-008]** Continuous metrics use a Normal Distribution to model spread.
- **[CLAIM-MAB-009]** Multi-Armed Bandit (MAB) automatically shifts traffic towards winning variations in real-time.
- **[CLAIM-MAB-010]** MAB uses Thompson Sampling.
- **[CLAIM-MAB-011]** Bayesian calculations are performed by `BayesianMathService`.
- **[CLAIM-MAB-012]** If Variation B has an 80% chance to be best, Thompson Sampling routes roughly 80% of traffic to Variation B.
- **[CLAIM-MAB-013]** Sample Ratio Mismatch (SRM) detection is executed by `SrmWorker`.
- **[CLAIM-MAB-014]** SRM monitoring starts once an experiment reaches 1,000 exposures.
- **[CLAIM-MAB-015]** SRM detection uses a Chi-Square Goodness-of-Fit test against configured Rollout weights.
- **[CLAIM-MAB-016]** An SRM anomaly is triggered if p-value is less than 0.001.
- **[CLAIM-MAB-017]** SRM detection fires an `experiment.srm_detected` webhook event.
- **[CLAIM-MAB-018]** SRM detection automatically pauses automatic MAB adjustments.
