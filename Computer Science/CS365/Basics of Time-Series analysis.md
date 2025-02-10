## Time series - ubiquitous
Time-series appear in any domain that involves temporal measurements.

Examples:
- Signal processing
- Econometrics
- Mathematical finance
- Weather forecasting
- Electroencephalography
- Control engineering
- Astronomy
- Communications engineering
- ...

When we have a *single time-series* we wish to forecast using its past values, we call this *univariate* analysis.

When we have a *target time-series* we wish to forecast using its past values and other co-evolving time-series, we call this *multivariate analysis*.

## Time series analysis
Why do we analyze time-series?

1. Interpretation

E.g., seasonal adjustment

2. Forecasting

E.g., predict stock prices

3. Control

E.g., how does increasing VAT will affect employment?

4. Hypothesis testing

E.g., should we believe in global warming?

5. Understanding catastrophic events

E.g., will an impactful earthquake take place tomorrow?

## Forecasting
1. **Fundamentals**
- Stochastic processes, strict vs weak stationairty, correlograms, partial correlograms, periodograms, autoregressive models (AR), moving average models (MA), transformations, compact time-series description. See: [[Probability Overview]] and [[Data Steams]]

2. **Forecasting methods**
- Evaluation protocols, basic metrics, null models, spectral methods, ARMA, ARIMA, SARIMA, VAR, similarity search, deep learning.

## Stochastic process - informal description

**Definition.** A stochastic process is a collection of random variables indexed by time.
- Discrete time stochastic processes (e.g., $X_0, X_1, X_2, ...$)
- Continuous time stochastic processes ($\{X_t\}_{t \geq 0}$)

## Time series - formal definition
- A **time series** is a stochastic process consisting of random variables indexed by time $t$.
- The stochastic behavior of the *time series* is determined by specifying the probability density/mass functions $$p(x_{t_1}, x_{t_2}, ..., x_{t_n})$$ for all finite collections of time indexed $$\{(t_1, ..., t_m), m < +\infty\}$$ i.e., all finite-dimensional distributions of $\{X_t\}$

### Time series - Stationarity
**Strictly stationary time-series.** A time series $\{X_t\}$ is strictly stationary if $\forall t, m, (t_1, ..., t_m)$ $$p(t_1 + \tau, ..., t_m + \tau) = p(t_1, ..., t_m).$$
- In other words, a time series is strictly stationary if the probability distribution is invariant under time translation.

Examples:
1. iid processes are strictly stationary
2. $X_t = Z_1 \cos(t) + Z_2 \sin(t)$ is strictly stationary if $Z_1, Z_2$ are independent normal variables
3. Random walks in certain types of graphs (stationary Markov chains)

Remark: Stationary time series are typically non-stationary.

### Time-series - Covariance stationarity
**Covariance stationary time-series.** A time series $\{X_t\}$ is covariance stationary if: $$E[X_t] = \mu$$ $$Var[X_t] = \sigma^2$$
$$Cov[X_t, X_{t+h}] = \gamma(h)$$ 

Reminder: $Cov[X_t, X_{t + h}] = E[(X_t - \mu_t)(X_{t+h} - \mu_{t+h})].$
