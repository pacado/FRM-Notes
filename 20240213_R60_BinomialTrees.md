# 20240213_R60_BinomialTrees

Binomial model for valuing options on stock and serves as introduction to BSM  
Objectives:

1. <input type="checkbox" checked/> Calculate value of european or american option using one-step or two-step binomial model
2. <input type="checkbox" checked/> Know the formulas for sizes of upward and downward movements
3. <input type="checkbox" checked/> Risk Neutral Probabilities in both up and down states
4. <input type="checkbox" checked/> Concept of delta and how it applies to hedging
5. <input type="checkbox" checked/> Understand how binomial model can be adjusted to expand beyond just modeling for individual, non-dividend-paying stocks

## One-Step Binomial Model

Objectives:

1. <input type="checkbox" checked/> Calculate value of American and European call or put option using a one-step and two-step binomial model
2. <input type="checkbox" checked/> Describe how volatility is captured in the binomial model

One-Step binomial world is a two-step world where the price of a stock will either go up or down once and the change will occur one step ahead at the end of the holding period

| Variable | Description                | Values |
| -------- | -------------------------- | ------ |
| P        | Current Stock Price        | $100   |
| X        | Option's Exercise Price    | $175   |
| t        | Time to option expiration  | 1      |
| i        | Risk-Free Interest Rate    | 8%     |
| Su       | Stock value in up state    | $200   |
| Sd       | Stock Value in down state  | $50    |
| c        | Value of call option today | ?      |

Imagine a portfolio that's long $\Delta$ number of shares in the stock at P and short a call option on the stock with `X=$125`.

In one step of t, i.e., `t=1`, stock price could be  
`Su = $200` or  
`Sd = $50`.

The value of the call option would then be  
`Cu = max(200-125,0) = $75` or  
`Cd = max(50-125,0) = $0`.

So in `t=1`, value of our portfolio would be either  
$200 * \Delta - 75$ or  
$50 * \Delta - 0$

Setting above two equal, portfolio is certain to equal 25 in this risk-neutral setup.  
$200 * \Delta - 75$ = $50 * \Delta$  
Solving we get $\Delta = 1/2$

### Estimating value of c

So portfolio has a value of $25 one year from today. So value today is $25*exp(-0.08*1) = 23.08$
Our long position today would then be, $100 * \Delta - c = 23.08$. Therefore, $c = \$50 - \$23.08=\$26.92 $

## Risk Neutral Valuation

Law of One Price - if two investments provide same cash flows at same times in the future, they both should sell for exactly the same price.

U = size of up move = $e^{\sigma * \sqrt{t}}$  
D = size of down move = $e^{-\sigma * \sqrt{t}}$  
where $\sigma$ is annual volatility  
t = length of step in binomial model  
$\pi_u$ = probability of up move = $(e^{rt} - D)/(U - D)$  
$\pi_d$ = probability of down move = $1 - \pi_u$

## Using Delta to Develop a Replicating Portfolio

Hedging: elimination of price variation through short sale of an asset exhibiting the same price volatility as the asset to be hedged. A perfect hedge creates a riskless position.

Hedge Ratio: Indicates the number of asset units needed to completely eliminate the price volatility of one call option. Hedge Ratio is also known as Delta, which is a measure of option sensitivity. Constructing a riskless position is sometimes known as delta hedging.

$\Delta$ tells us how many units of stock to hold per call option to be shorted to make the hedge work (i.e., a riskless position)  
$\Delta = (C_u - C_d)/(S_u - S_d)$  
A $\Delta$ of 0.5 says that one option contract is needed for each half-share of stock.  
Reciprocal of delta is the number of option contracts to buy per share of stock that was sold short.
$\Delta$ will not remain constant and change over time.

## Modifying the Binomial Model

1. Pay Dividend Yield, q  
   $\pi_u = ( e^{(r-q)t} -D)/(U-D)$  
   $\pi_d = 1 - \pi_u$

2. Options on currenices  
   Assume foreign currency asset provides a return equal to the foreign risk-free rate of interest, $r_{fc}$. So replace our formula as $\pi_u = (e^{(r_{dc} - r_{fc})t}-D)/(U-D)$,  
   where,  
   $r_dc$ is domestic currency risk-free rate of interest and  
   $r_fc$ is the foreign currency risk-free rate of interest

3. Future contracts - Costless to enter into.  
   So formula is : $\pi_u = (1-D)/(U-D)$
