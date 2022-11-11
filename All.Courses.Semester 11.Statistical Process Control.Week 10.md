---
id: bptobzgz1bja3g4loqvnqd6
title: Week 10
desc: ''
publishing:
enableKatex: true
updated: 1668088708034
created: 1668081905577
---

ACF: Autocorrelation function
* A function that plots the aurocorrelation between different number of lags. If they are uncorrelated the autocorrelation should be zero for every lags except for lag equal to zero.
* Rho hat should be inside +- 2/sqrt(T), this is 95% confidence interval if assuming normality. z_{alpha} * sigma_phat
* Sample ACF: ACF based on the data or sample, wow.
* Backshift operator: B*y_t = y_t-1.
* Backshift operator: B^2*y_t = y_t-2.

## Finite MA Models: 
* y = mu + epsilon_t - theta_1 * epsilon_t-1... 
* Do not use infinitely many. We cut it off at some point. 
* Memory of past events. 
* q many lags. 
* Errors are random. The same disturbance affects both. Yes I can see it. Consecutive observations are correlated. 
* Why could consecutive observations not be correlated? Epsilons are not correlated. Assumption that we make. This is the answer to my question. 
* ACF is zero after lag q. All points below the confidence level are considered to mean that there is no correlation. 
* We can observe "runs" in the signal. Where the data points move up multiple times in a rows. This happens if the autocorrelations is positive. If data points move up and down and vice versa for consecutive runs it could mean that the correlation is negative. 
* Correlations can be inferred from the formular used to generate the data. 
* How can we assume that the errors are normally distributed? I would make a normal qq-plot after estimating the regression model parameters. 
* Error are estimated by subtracting the observations from the predicted values, called residuals. Are these residuals normally distributed. 
* Generalized linear model: We do not have to assume normally distributed errors. 
* Good point: Error term, epsilon, could be a function of infinitely many variables. That would theoretically make the regression model deterministic. Simplifing assumption, 

## Autoregressive Process
* I want to retain all past errors, we use a AR process since all past error are incapsulated in the previous observations. Good point. 
* $y_t - phi * y_{t - 1} = (mu + \sum phi^i * epsilon_{t-1}) - phi(mu + sum phi^i * epsilon_{t - 1 - i})$. All errors except one cancelles out, leaving only a constant times the previous observation plus delta plus epsilon. This contains all previous observations. Exponentially reduced effect since phi is below 1 and above 0? This is different from an AM process which cuts of disturbances from the past.
* $y_t = \sum_{i}^{p} phi_i * y_{t - 1} + delta - epsilon_t$
* $\rho_y(k) = \frac{\gamma_y(k)}{\gamma_y(0)} = \phi^k$
* ACF for the AR process. Roots of an AR(k) process should have an absolute value less than one. ACF will show an exponential decay or an exponentially damped decay. 
* We always want the most parsimonious model. 
* ACF of AR(p) model mixture of exponential decay and damped sinusoidal behavior. 
* Plot ACF. Good point. ACF will be hard to use to determine the p the of the AR(p) model. 

## Partial Correlation
* PACF: Taking out certain correlations to expose patterns from the harder to determine AR(p) process. Taking out the last observation from the AR process and then doing this for every p terms of the AR(p) process.
* PACF will cut of when see reach p of the underlying process. 


## ARMA Process
* Autoregressive Moving Average process
* I can see it! 

## Non-Stationary models
* The mean is not stationary
* It is hard to model. To adjust for this we take the difference between consecutive observations.
* Start by differencing
* Stationary by definition means that a process is out of control, since process is in the process of changing. 
* ACF and PACF should be used as tools to gauge the process.
* Tables on how to use ACF and PACF should only be used after process is stationary. 
* ARMA models brute force start with ARMA(3, 3)
* Apply model on control data. When residual are in-control, we are done. 

## Examples ARIMA models
I should port all my notes by making a new vault in Dendron and simply copy my notes into that. 

## AIC, Akaike Information Criterion
* Information criteria. Favors smaller model, adjusts for model parameters.
* AIC is really interesting. I should read up on difference between AIC and BIC. 

## Residuals
* We use ARIMA to adjust data, if there is autocorrelation in the data we can remove it by using ARIMA. 
* We make the control chart on the residuals. 






# I really should get these notes working on my work PC. 









I should focus on the person that I am talking to... Remember.