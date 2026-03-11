# Data Wrangling & Engineering Pipeline

## Objective
Engineer a production-ready feature matrix from a structurally compromised HR dataset by systematically resolving missingness, multicollinearity, and high-cardinality encoding challenges as a precondition for valid econometric inference.

## Methodology
- **Missingness Forensics:** Deployed `missingno` matrix visualization to diagnose the structural alignment of null values across variables, identifying the missingness mechanism as Missing At Random (MAR) based on the co-occurrence pattern of `bonus_pay` and `performance_rating`.
- **Conditional Median Imputation:** Applied grouped median imputation stratified by department to fill missing salary observations, preserving intra-group variance structures rather than collapsing to a global central tendency.
- **Dummy Variable Trap (Intentional Failure & Resolution):** Demonstrated perfect multicollinearity by constructing a full-rank indicator matrix for a categorical variable alongside an intercept term, then resolved it via the k-1 methodology — dropping a reference class to restore matrix invertibility and enable OLS estimation.
- **Target Encoding:** Compressed a high-cardinality geographic variable (~800 unique ZIP codes) into a single continuous feature vector using `category_encoders.TargetEncoder`, replacing nominal identifiers with their conditional mean salary, thereby avoiding the dimensionality explosion of one-hot encoding.

## Key Findings
The pipeline successfully resolved three distinct data pathologies that would otherwise invalidate downstream econometric modeling. Missingness was confirmed as MAR — non-random but explicable by observed covariates — permitting principled imputation without selection bias. The dummy variable demonstration confirmed that including a full set of indicator columns with a constant term produces a singular design matrix; dropping one reference category restored rank sufficiency. Target encoding reduced a ~800-dimension nominal variable to a single economically interpretable feature with no loss of predictive signal, demonstrating a scalable approach to geographic fixed effects in large HR datasets.
