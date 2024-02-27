# Measures of Financial Risk

Objectives:  
<input type="checkbox" /> 1. Calculation of VaR  
<input type="checkbox" /> 2. Properties of Coherest Risk Measures  
<input type="checkbox" /> 3. Expected Shortfall Methodology

## Portfolio Theory & Value at Risk

### Mean-Variance Framework

<u>**Necessary assumption**</u>: Return distributions of portfolios are elliptical distributions. The most commonly known elliptical probability distribution function is the normal distribution.

Normal distribution - most common elliptical distribution.  
Approx. 66.7% of returns occur within $\plusmn1\sigma$  
Approx. 95% of returns occur within $\plusmn2\sigma$

Portfolio with 2 assets. Mean will be  
$\mu_P = W_1*\mu_1 + W_2*\mu_2$  
$\sigma_p = \sqrt{w_1^2*\sigma_1^2 + w_2^2*\sigma_2^2 + 2*\rho*w_1*w_2*\sigma_1*\sigma_2*\rho}$

### Limitations of Mean-Variance Framework

1. mean,standard deviations, correlations are assumed to be consistent from perspectives of all investors.
2. Assumption that mean and standard deviation are all that matters
3. All investors are assumed to be able to borrow at the risk-free rate of interest
4. Use of standard deviation as a risk measure is not appropriate for non-normal distributions (if distribution is not symmetrical, then stand)

## Coherent Risk Measures and Expected Shortfall

1. Monotonicity:
