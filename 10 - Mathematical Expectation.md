# Expectation
Expectation = Average value of a Random Variable!
* For a discrete variblae X with probability function P(x), the expected value E(x) = summation of `xi * P(xi)`.
* P(x): probability of x
## Linear of Expectation
The rule of linearity of the expectation:
> E[x1+x2] = E[x1] + E[x2]

#### Example
A fair coin is thrown N times, what is the expected number of heads.
```
Z = {e1, e2, e3, ..., eN}
E(z) = E(e1 + e2 + e3 + ...eN)
     = E(e1) + E(e2) + E(e3) + E(eN)
     = n*0.5 = n/2
E(ei) = summation xiP(xi)
      = 1(1/2) + 0(1/2)
      = 0.5
```
#### Example
What is the expected number of coin flips to get a head
* Approach:
> x = xiP(xi)
>
>   = 1(1/2) + (1+x)(1/2)
>  
> 2x = 1 + 1 +x 
> 
> x = 2
#### Example
What is the expected number of coin flips to get two consecutive head
> x = xiP(xi)
>
>   = (1/2 * 1/2)(2) + (1/2 * 1/2)(x+2) + (1/2)(x+1) 
>  
> 4x = 2 + x + 2 + 2x + 2 
>  
> x = 6

#### Example
What is the expected number of coin flips to get N consecutive head
> x = 2^(n+1) - 2

## Theorem 1
If the probability of success of a bernaulli trial is p then the expected number of trials to get a success is `1/p`

## Theorem 2
If the probability of success of a bernaulli trial is p then the expected number of successes in n trials in `np`
