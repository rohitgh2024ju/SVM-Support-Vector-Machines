# Derivation of total margin

Let's say, boundary equation is:
$$
w^T x + b = 0
$$

one point will satisfy:
$$
w^T x + b = 1
$$

and the other:
$$
w^T x + b = -1
$$

now, $x_+ on w^T x_+ + b = 1$ and $x_- on w^T x_- + b = -1$

shortest distance between them is $(x_+ - x_-) = \lambda w$, where $\lambda is scalar$

now $w^T (x_+ - x_-) = 2$

therefore $w^T (\lambda w) = 2$
$$
\lambda w^T w = 2
\lambda ||w||^2 = 2
\lambda = \frac{2}{||w||^2}
$$

now,
$$
||(x_+ - x_-)|| = ||\lambda w||
||(x_+ - x_-)|| = ||\frac{2}{||w||^2}|| ||w||
$$

Hence, $\boxed{Total Margin = \frac{2}{||w||}}$