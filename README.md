# hw3
### Theoretical Solution: Proof of Beta Distribution for Order Statistics

Let \( x_1, x_2, \dots, x_n \) be independent and identically distributed (i.i.d.) random variables drawn from the uniform distribution \( U[0, 1] \). The \( k \)-th order statistic, \( x_{(k)} \), is the \( k \)-th smallest value in the sorted sequence.

The cumulative distribution function (CDF) of the \( k \)-th order statistic, \( F_{x_{(k)}}(x) \), is the probability that the \( k \)-th smallest value is less than or equal to \( x \), i.e., the probability that at least \( k \) of the values \( x_1, x_2, \dots, x_n \) are less than or equal to \( x \).

Since the \( x_i \) are i.i.d. uniform random variables, the probability that a particular \( x_i \) is less than or equal to \( x \) is just \( x \) (i.e., \( P(x_i \leq x) = x \)).

We use the **binomial distribution** to calculate the CDF of the \( k \)-th order statistic:

$$ F_{x_{(k)}}(x) = P(\text{at least } k \text{ values are less than or equal to } x) = \sum_{i=k}^{n} \binom{n}{i} x^i (1-x)^{n-i} $$

The probability density function (PDF) of the \( k \)-th order statistic is the derivative of the CDF:

$$ f_{x_{(k)}}(x) = \frac{d}{dx} \left( \sum_{i=k}^{n} \binom{n}{i} x^i (1-x)^{n-i} \right) $$

By differentiating the CDF, we obtain:

$$ f_{x_{(k)}}(x) = \frac{n!}{(k-1)!(n-k)!} x^{k-1} (1-x)^{n-k} $$

This is the PDF of a **Beta** distribution with parameters \( k \) and \( n+1-k \):

$$ x_{(k)} \sim \text{Beta}(k, n+1-k) $$

Thus, we have shown both experimentally and theoretically that the \( k \)-th order statistic of a sample from \( U[0, 1] \) follows a Beta distribution with parameters \( k \) and \( n+1-k \).
