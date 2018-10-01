---
layout: post
title:  "A Trigonometric Recurrence Relation"
tags: [trigonometry, complex numbers, Chebyshev polynomials]
category: high school maths
use_math: true
---

In this blog post we will look at a nice problem given several years ago at the mathematical olympiad. The problem sounds like this: 

>Let $$ n \in \mathbb{N}^* $$. Prove that $ 2 \sqrt{2^n} \cos(n \arccos(\frac{\sqrt{2}}{4})) $ is a natural odd number.
><div style="text-align: right"> Romanian Mathematical Olympiad 2013, District Round, Author: Gheorghe Iurea, Iasi </div>
 
Let's denote by $ S_n $ for simplicity the given expression. First, we observe that the values of $S_1$ and $S_2$ can be easily computed: 
$$ S_1 = 2 \sqrt{2} \cos(\arccos(\frac{\sqrt{2}}{4})) = 2 \sqrt{2} \frac{\sqrt{2}}{4} = 1$$ 
For computing $S_2$ we use the following trigonometric formula: 
$\cos(2x)=2\cos(x)^2 - 1$. We have that: 
$$ S_2 = 2 \sqrt{4} \cos(2 \arccos(\frac{\sqrt{2}}{4})) = 4 (2 \cos(\arccos(\frac{\sqrt{2}}{4})) - 1) = 4 (2 / 8 - 1) = -3$$. 
So both $S_1$ and $S_2$ are odd number. 
Since we have to prove that $S_n$ is odd for all values of $n \in \mathbb{N}$, a possible idea is to find a recurrence relation involving $S_n$ terms.


*First solution:* The official solution derives this recurrence relation using complex numbers. 
Namely, let $\alpha=\frac{\sqrt{2}}{4}$ and $z=\cos\alpha + i \sin\alpha$. Using de Moivre's formula,
we get that $z^n=\cos(n\alpha)+i\sin(n\alpha)$. Further, $\overline{z}^n=\overline{z^n}=\cos(n\alpha)-i\sin(n\alpha)$, so
$z^n+\overline{z}^n=2\cos(n\alpha)$ and, therefore, $S_n=2\sqrt{2^n}\cos(n\alpha)=\sqrt{2^n}(z^n+\overline{z}^n)$.
Why is this useful? Well, we can obtain a recurrence relation involving $z$ using the equality:

$$ z^n+\overline{z}^n=(z+\overline{z})(z^{n-1}+\overline{z}^{n-1}) - z \overline{z}(z^{n-2}+\overline{z}^{n-2}) \tag{1}$$ 

Multiplying relation \(1\) with $\sqrt{2^n}$ we obtain that $S_n=S_{n-1}-2S_{n-2}$ for $\forall n \ge 3$.


*Alternative solution:* The same recurrence relation can be obtained using a slightly different approach.
We may use the following trigonometric formula: $\cos(a)+\cos(b)=2\cos(\frac{a+b}{2})\cos(\frac{a-b}{2}) \forall a, b \in \mathbb{R}$.
We can thus obtain a ["Chebyshev polynomial"](https://brilliant.org/wiki/chebyshev-polynomials-definition-and-properties/)-type of relation:

$$ S_n + 2S_{n-2} = 2 \sqrt{2^n} \cos(n \arccos\alpha) + 2 \sqrt{ 2^2 2^{n-2}} \cos((n-2) \arccos\alpha)=
2 \sqrt{2^n} \cos(\frac{n+n-2}{2}\arccos\alpha) \cos(\frac{n-n+2}{2}\arccos\alpha)=
2 \sqrt{2^n} \cos((n-1)\arccos\alpha) \alpha=S_{n-1}$$

Now that we have that $S_1=1, S_2=-3$ and $S_n=S_{n-1}-2S_{n-2} \forall n \ge 3$ we can easily prove by induction that $S_n$ is odd $\forall n \in \mathbb{N}^*$.
