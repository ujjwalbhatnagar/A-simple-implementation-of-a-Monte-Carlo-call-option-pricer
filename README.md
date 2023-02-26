# A-simple-implementation-of-a-Monte-Carlo-call-option-pricer

The model for stock price evolution is
d St = µStdt + σ StdWt, and a riskless bond, B, grows at a continuously compounding rate r. The Black–Scholes pricing theory then tells us that the price of a vanilla option, with expiry T and pay-off f , is equal to e−rTE( f (ST )), where the expectation is taken under the associated risk-neutral process,
d St = r Stdt + σ StdWt . 

We solve equation (1.2) by passing to the log and using Ito’s lemma; we computed log St = r − 12 σ2dt + σdWt. 
As this process is constant-coefficient, it has the solution log St = log S0 + r − 12σt + σ Wt . 

**A simple Monte Carlo model**
Since Wt is a Brownian motion, WT is distributed as a Gaussian with mean zero
and variance T , so we can write WT = √T N(0, 1), (1.5) and hence log ST = log S0 + r − 12σ2T + σ√T N(0, 1), or equivalently, ST = S0e(r−12 σ2)T+σ√T N(0,1). 


The objective of our Monte Carlo simulation is to approximate this expectation by using the law of large numbers, which tells us that if Yj are a sequence of identically
distributed independent random variables.
So the algorithm to price a call option by Monte Carlo is clear. We draw a random
variable, x, from an N(0, 1) distribution.
