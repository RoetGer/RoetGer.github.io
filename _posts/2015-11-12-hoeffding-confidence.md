---
layout: post
title: Confidence Intervals based on Hoeffding's inequality
comments: true
category: Math
tags: [Uncertainty, Concentration Inequalities]
---

In this post, we will take a look on how to obtain a confidence interval on the empirical mean of independent, bounded random variables via Hoeffding's inequality (HI).

<!-- more -->

For a set of random variables (RV) $$X_1, X_2, \cdots, X_n$$ with $$X_i \in \left[ a_i, b_i \right]$$, the empirical mean is given by:

$$Y = \frac{1}{n}\sum_i X_i$$

HI, in its general form, tells us now that:

$$
\mathbb{P}(|Y - \mathbb{E}\left[ Y \right]| \geq \epsilon) \leq 2\exp\left\lbrace -\frac{2n^2\epsilon^2}{\sum_i \left( b_i - a_i \right) ^ 2} \right\rbrace
$$

If we want now a confidence interval on our empirical mean, we simply equate the right-hand side with the significance level (significance level = 1 - confidence level) that we require and solve for $$\epsilon$$.

$$
\begin{align}
&\alpha = 2\exp\left\lbrace -\frac{2n^2\epsilon^2}{\sum_i \left( b_i - a_i \right) ^ 2} \right\rbrace \\
&\exp\left\lbrace -\frac{2n^2\epsilon^2}{\sum_i \left( b_i - a_i \right) ^ 2} \right\rbrace = \frac{2}{\alpha} \\
&\frac{2n^2\epsilon^2}{\sum_i \left( b_i - a_i \right) ^ 2} = \log\left( \frac{2}{\alpha} \right) \\
&\epsilon = \sqrt{\frac{\sum_i \left( b_i - a_i \right)}{2n^2} ^ 2 \times \log\left( \frac{2}{\alpha} \right)}
\end{align}
$$

If we pick $$\epsilon$$ accordingly, then the observed sample mean  will deviate from our  true value $$\mathbb{E}[Y]$$ by more than $$\epsilon$$ in less than $$\alpha$$ percent of our experiments (given infinite experiments).
