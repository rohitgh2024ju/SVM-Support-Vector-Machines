# Derivation of total margin

Let's say the boundary equation is:

$$
w^T x + b = 0
$$

One point will satisfy:

$$
w^T x + b = 1
$$

And the other:

$$
w^T x + b = -1
$$

Now, $x_+$ is on $w^T x_+ + b = 1$ and $x_-$ is on $w^T x_- + b = -1$.

The shortest distance between them is $(x_+ - x_-) = \lambda w$, where $\lambda$ is a scalar.

Now:

$$
w^T (x_+ - x_-) = 2
$$

Therefore:

$$
w^T (\lambda w) = 2
$$

$$
\lambda w^T w = 2
$$

$$
\lambda \|w\|^2 = 2
$$

$$
\lambda = \frac{2}{\|w\|^2}
$$

Now:

$$
\|(x_+ - x_-)\| = \|\lambda w\| = | \lambda | \cdot \|w\| = \left| \frac{2}{\|w\|^2} \right| \cdot \|w\|
$$

Hence, 

$$
\text{TotalMargin} = \frac{2}{\|w\|}
$$