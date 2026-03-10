# SwiftCart Logistics — Statistical Audit

This notebook presents a computational audit of SwiftCart Logistics across three domains: driver tip compensation, delivery algorithm performance, and subscription service ROI. All analysis intentionally discards standard parametric assumptions in favor of empirical, computation-heavy methods suited to real-world messy data.

Phase 1 addressed zero-inflated tip data using a manual bootstrap engine (10,000 resamples) to construct an asymmetric 95% confidence interval around the median. The observed median of $0.76 versus a mean of $2.77 illustrates how summary statistic selection can misrepresent driver earnings — the bootstrap CI captures this structural skew where a parametric interval cannot.

Phase 2 tested the engineering team's Batch Routing algorithm via a manual permutation test (5,000 iterations). Zero permutations matched the observed difference in delivery times, yielding p < 0.0002 — the algorithm's effect is extremely unlikely to be due to chance.

Phase 3 used Propensity Score Matching to isolate the causal effect of SwiftPass subscription on post-treatment spending, eliminating selection bias present in the naive SDO. A Love Plot confirmed all three pre-treatment covariates balanced within ±0.1 SMD after matching, validating the ATT as a defensible causal estimate.
