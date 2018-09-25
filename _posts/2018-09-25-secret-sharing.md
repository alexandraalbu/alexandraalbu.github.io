---
layout: post
title:  "Secret Sharing"
tags: [cryptography, secret sharing]
use_math: true
---

Secret sharing is a very nice cryptographic primitive which appeared a long time ago but still finds 
many applications in various fields.

The main motivation behind the development of secret sharing schemes was cryptographic keys management. 
Otherwise a difficult task, secure storage of cryptographic keys can be easily done using secret sharing. 
Simply encrypting the keys does not solve the problem, as the used encryption key still needs to be managed. The 
difficulty in storing the keys in plaintext comes from the fact that storing them in a single place is unreliable 
as they can be lost, while storing multiple copies of a key increases the risk of it being found by an attacker ([1](#1)). 
Some less straightforward, but very interesting applications of secret sharing are secure multiparty computation protocols. These protocols 
allow users to compute a function over some inputs $x_1, x_2,…, x_n$ where $x_i$ is a secret known only by the $i^{th}$ user ([2](#2)). 
Such secure computations can vary from simple sums over encrypted data \(with applications in electronic voting\) to data mining or even
machine learning algorithms (for more on this, check this [great blog post](https://mortendahl.github.io/2017/04/17/private-deep-learning-with-mpc/)).
This is possible due to the _homomorphic_ properties of secret sharing schemes (we'll come back to this later).

Informally, secret sharing consists in splitting a secret into multiple parts, called _shares_, such that each 
individual share reveals nothing about the secret. The secret can, however, be reconstructed by authorized 
groups (called _access structures_). A scheme in which a secret is reconstructed given a sufficiently large 
group of shares is called a _threshold secret sharing scheme_. In this blog post we will discuss only this 
type of schemes.

## Shamir’s Secret Sharing Scheme
The algorithm was developed by Adi Shamir in 1979 and is based on polynomial interpolation. The central idea 
behind the scheme is that a polynomial of degree $ k-1 $ is uniquely determined by its values at $k$ points, 
while knowledge of at most $ k-1 $  point-value pairs gives no information about the polynomial coefficients. 
Put in an algorithmic/formal way, Shamir's scheme goes like this:

>Let $F$ be a finite field of size $p$ and $S$ be the secret. We assume without loss of generality that 
$S$ can be represented as an element of $F$. Let $k, n$ be natural numbers with  $k \le n$, where $n$ represents the 
number of participants in the scheme (and the number of shares) and $k$ is the threshold value.
Choose $k-1$   elements  $a_1,a_2,..., a_{k-1}$ from $F$ and construct the polynomial
$f(x)=a_0+a_1x+a_2x^2+…+a_{k-1}x^{k-1}$, where $a_0=S$
Compute the value of $f$ at $n$ distinct non-zero elements $x_1,x_2,...,x_n$ and distribute the shares $(x_i, f(x_i))$, 
$1 \le i \le n$ among the participants. $k$ participants can now reconstruct the secret by using polynomial interpolation
Such a scheme is called a $(k, n)$ threshold scheme.

From the security point of view, secret sharing schemes can be classified into:
* Perfect schemes – in which unauthorized groups gain no information about the secret from their shares
* Computationally-secure schemes – in which participants learn some information about the secret, but the problem of actually finding it is intractable



The main idea of Shamir’s secret sharing scheme can be illustrated through Fig. 1. 
(_Disclaimer_: I lied a bit here, as Shamir’s scheme deals with finite fields and not real numbers as in my figure down here. However, 
the main concept can be more easily visualized and understood in $\mathbb{R}$)

<figure>
    <img src="/assets/lagrange_interpolation.png" alt="Visualization of Shamir's scheme" width="50%" align="middle"/>
    <figcaption>Fig. 1: In the left figure: being given 2 points, we can find an infinite number of
                second degree polynomials which pass through these points. In the right: having 3 
                points, one uniquely determines the second degree polynomial.</figcaption>
</figure>

Bibliography:

<a name="1">[1] Shamir A.: How to share a secret, Communications of the ACM 22.11 (1979): 612-613</a> 
<a name="2">[2] Yao A. C.: Protocols for secure computations. Foundations of Computer Science, 1982, SFCS'08. 23rd Annual Symposium on (pp. 160-164).</a>
<a name="3">[3] https://mortendahl.github.io/2017/06/04/secret-sharing-part1/</a>


