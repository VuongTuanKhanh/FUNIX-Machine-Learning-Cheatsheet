# Probability & Probability Distribution

Created: Jan 18, 2021 1:40 PM
Created By: Khanh Vương
Last Edited By: Khanh Vương
Last Edited Time: Feb 8, 2021 5:33 PM
Module: Introduction to Machine Learning
Type: Introduction to Machine Learning

# Probability

- A **Sample Space** is a space that contains all the possible outcome
- An **Event** is a subset of the **Sample Space**, is the outcome or a combination of outcomes
- **Intersection of two probability:**

                                  $P(A \cap B) = P(A).P(B)$

- **The union of two probability:**

                    $P(A \cup B) = P(A) + P(B) - P(AB)$ 

- **Conditional Event probability**:

                                    $P(A|B) = \frac{P(A \cup B)}{P(B)}$

- Two events are called independence when:
    - $P(A|B)=P(A) or P(B|A)=P(B)$
    - $P(A∩B)=P(A).P(B)$
- If two events are `disjoint`, it means they are `dependent` to each other (if one event is happened, the other event cannot be occurred)
- If two events are `independent`, one event happens doesn't tell anything about the others, meaning that they are not `disjoint`

# Probability Distribution

- **Probability Distribution** is a list of probabilities associate with each of the value that the random variable can take
    - The **Probability Distribution** of a `discrete` random variable is called **Probability Mass Function**
    - The **Probability Distribution** of a `continuous` random variable is called **Probability Density Function**

- We can calculate the $\mu$ of a random variable:
    - **Discrete**:

                                         $E(x)=μ_x=∑[xP(x)]$

    - **Continous**:

                                                   $\intop\nolimits_{-∞}^{∞}xf(x)dx$

    - If we change $x$  to $ax + b$, then $\mu$ become $\mu_{a+bX} = a + b\mu_x$
    - Sum of the $\mu$ of two random variables is: $μx+y=μx+μy$

- **Variance** of a random variable:
    - **Discrete**:

                         $var(X)=E[(X−μ)^2]=∑(xi−μ)^2.Pi(xi)$

    - **Continuous**:

                         $var(X)=E[(X−μ)^2]=∫(x−μ)^2.f(x)dx$

    - **Variance** will change as follow:
        - $var(aX+bY)=a^2var(X)+b^2var(Y)$
        - $var(aX−bY)=a^2var(X)+b^2var(Y)$
        - $σ(X+Y)<σ(X)+σ(Y)$

# Normal Distribution (Gaussian Distribution)

- **Normal Distribution** is a symmetric, bell-shaped graph, and can be describe with $\mu$ and $\sigma$.
    - $μ$ - The center of the distribution, where we can find the highest point
    - $σ$ - The width of the distribution, also show the slop of the curve

                                                        $X$~$N(\mu, \sigma^2)$

                                    $f(x) = \frac{\mathrm{1} }{\mathrm{\sigma \sqrt{2\pi}} }  \epsilon ^{-0.5( \frac{\mathrm{x - \mu} }{\mathrm{\sigma} } )^2}$

- A somewhat counterintuitive property of the normal probability density is that it approaches zero for very large positive or negative values of $x$, but will never actually be zero. This leads to the fact that the values a random variable can take will stretch from minus infinity to plus infinity. All these values are possible outcomes albeit very small probability but still the sum of all probabilities will be one
- **Sigma Rule**
    - $μ−σ<0.68<μ+σ$
    - $μ−2σ<0.95<μ+2σ$
    - $μ−3σ<0.997<μ+3σ$
- **Standard Normal Distribution** or **Z-distribution** is the probability of the values that $ασ$ from the $μ$

                                               $N(0, 1) \Rightarrow \mu = 0, \sigma = 1$

                                               $x = \mu - z\sigma \Rightarrow z= \frac{\mathrm{x - \mu} }{\mathrm{} \sigma}$

- **Binomial Distribution** gives the probabilities for accounts with binary data.
    - The **Bernoulli Trial**:
        - Have only two output distribution
        - The successful probability of each trial is a constant

                                                        $X$ ~ $B(N,P)$

                       $P(x) =  \frac{\mathrm{n!}}{\mathrm{x!(n - x)!}}p^x(1 - p)^{n-x}; x = 1, 2, 3, ..., n$ 

        - For cumulative probability distribution:

                    $F(x) = P(X <= x) = \sum_{k = 0}^{x} \frac{\mathrm{n!}}{\mathrm{k!(n - x)!}}p^k(1 - p)^{n-k}$

    - A **Binomial Distribution** with a low probability of success is right skewed, and the probability close to $0$
    - While that with a high probability of success is left skewed and the probability close to $1$
    - Symmetric when the probability is around $0.5$
    - Variance and Mean of **Binomial Distribution:**

                                                               $\mu = nP$

                                                    $\sigma = \sqrt{n.P(1-P)}$