Black Scholes Merton (BSM) option pricing model is based on the assumption that stock prices are lognormally distributed.

Examine calculation of call and put options using BSM option pricing model and current option prices.

Objectives:

1. <input type="checkbox" checked /> How to calculate value of call and put option using BSM Model
2. <input type="checkbox"/> Able to incorporate dividends, currencies, and futures into the model if necessary
3. <input type="checkbox" /> Apply Put-Call Parity to calculate call and put since BSM model requires the use of European Options

BSM assumes stock prices are log-normally distributed:

$ln(S_t) \sim N[ ln(S_0) + (\mu - \sigma^2 /2)T, \sigma\sqrt{T} ]$  
where,  
| Variable | Description |
|:--------:|----------------------------------------------------------|
| $S_0$ | Stock Price at Time 0 |
| $S_t$ | Stock Price at Time T |
| $\mu$ | expected stock return on stock per year |
| $\sigma$ | volatility of stock price per year |
| N[m,s] | Normal Distribution with mean m and standard deviation s |

Dividing both mean and standard deviation of the log-normal process returns the continuously compounded average annual returns of the stock price. These returns are **normally distributed** with a mean of $m\_annual = \mu - \sigma^2/2$ and standard deviation of $\sigma/\sqrt{T}$

**NOTE**:

> BSM Model assumes stock prices are lognormally distributed but the stock returns are normally distributed. In the Standard Deviation formula, volatility will be lower for longer time periods.

## Expected Value

$E(S_t) = S_0*e^{\mu*T}$, where $\mu$ is the expected rate of return

## Estimating historical volatility

Scale from shorted times to longer times by multiplying by $\sqrt{T}$
If weekly standard deviation is 5%, annual standard deviation is $5\% *\sqrt(52)$

Volatility estimation is a matter of collecting daily price data and then computing standard deviation of series of corresponding continuously compounded returns.

## Black-Scholes-Merton Model

Values options in continuous time and is derived from no-arbitrage assumption to value options with binomial model.

> Assumptions:
>
> > 1. Price of underlying asset follows log-normal distribution
> > 2. Risk-free rate is constant and known + always available for borrowing and lending
> > 3. Trading is continuous
> > 4. Markets are frictionless - no taxes, no transaction costs, no restrictions on short sales or use of short sale proceeds
> > 5. Underlying asset has no cash flow such as dividends or coupon payments
> > 6. Options valued are European options, which can only be exercised at Maturity. **Model DOES NOT correctly price American Options**.

## Black-Scholes-Merton Formulas

$c_0 = [ S_0 * N(d_1) ] - [X * e^{-R_f^C * T} * N(d_2)]$  
$p_0 = -[S_0 * \{1 - N(d_1)\}] + [X * e^{-R_f^C * T} * \{1 - N(d_2)\}]$

where:

$d_1 = (ln(S_0/X) + [R_f^c + (0.5*\sigma^2)] * T)/(\sigma * \sqrt{T})$  
$d_2 = d1 - (\sigma*\sqrt{T})$

| Variable | Description                                                |
| -------- | ---------------------------------------------------------- |
| T        | Time to Maturity as % of a 365 day year                    |
| $S_0$    | asset price                                                |
| X        | exercise price                                             |
| R_f^c    | Continuously compounded risk-free rate                     |
| $\sigma$ | volatility of continuously compounded returns on the stock |
| N(.)     | Cumulative normal probability                              |

Put Call Parity

P + S = C + X*$e^(-R_f^c * T)$

## Dividends, Warrants and Implied Volatility

Relaxing the assumptions of BSM to account for dividends. Cash flows will increase put values and decrease call values.
Instead of using S, discount the S using the dividend yield, so $S_0*e^{-q*T}$.

When using BSM for options on futures, the model is called **Black's Model**.
For options on Futures,

1. $S_0$ in $S_0*e^{-q*T}$ is replaced with futures prices(F)
2. Dividend yield is replaced with the domestic risk-free rate.
3. Volatility of the futures price is used in place of the volatility of the stock price under the traditional model.
4. Black’s model can be used to value an option on an asset’s spot price in terms of its forward price.
