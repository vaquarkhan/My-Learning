# Markov Chain
To understand Markov Chain, need some probability theroy background:

## Some Probablity Theory
- **A random variable** is a variable whose value varies based on randomness.
-  A **stochastic process** (random process) represents the evolution of a system of random variables over time. 
-  **Memorylessness** is a property that describes a statistical distribution. It says that the probability of an outcome is independent of its current state. The probability of a customer walking into a store is memoryless, because it does not increase because of elapsing time. Probability of an engine breaking in the next 500 km is NOT memoryless, since an engine that's driven 200000km already is more likely to break than a new one.
-  **The Markov property** is the memoryless property of a stochastic process.
-  A **Markov chain** is the process with the Markov property. Often, a Markov Chain is used to model a series of states, whose next state is soley dependent on the current state and not any previous states.

## A Famous Example
Drunkard's Walk is a Markov Chain, where you randomly walk +1 or -1 on a number line with equal (0.5) probability. It does not depend on how you got to the current number, the probability of +1 or -1 is always equal.

## Markov Chains
Set of states, which transition betweens states based on stochastic probability. For a game of snakes and ladders, you can build a `n x n` transition matrix, for n states. Must my memoryless to create an accurate model.

## Formal Definition
A Markov chain is a sequence of random variables X1, X2, X3 ... with the Markov property (the porbability of moving to the next state depends only on the present state and not previous states):
```
Pr(Xn+1 = x | X1 = x1, X2 = x2, ..., Xn = xn) = Pr(Xn+1 = x | Xn = xn)
In other words, state n+1 is only dependent on state n
```
