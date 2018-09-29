---
layout: post
title:  "A Misleading Functional Equation"
tags: [mathematical analysis, high school maths]
use_math: true
---

Not long ago, a colleague asked me whether I prefer maths problems with long and detailed requirements
or problems with short ones. His question reminded me of a problem I saw several years ago which
has a very short requirement and a really nice and somehow surprising solution. 

>Determine all differentiable functions $f: \mathbb{R} -> \mathbb{R}$ satisfying $f \circ f = f$.
><div style="text-align: right"> Romanian Mathematical Olympiad 2014, Final Round</div>

It is not hard to see that the constant and the identity functions satisfy the requirements.
Further, we'll prove that these are the only solutions.

As the function $f$ is differentiable, it is very tempting (or at least, I fell into this trap) 
to differentiate the given relation and see then what you can find out about $f$. However, this seems 
to be a dead end. 

Ok, since this doesn't work, what other options do we have? Let's look again at the 
relation in the requirement. One thing you may think of is trying to find something
about the image of $f$, since $f$ composed with itself gives still $f$.
The official solution goes in this direction, noticing that because $f$ is continuous 
(being differentiable), its image is an interval $I$, included in $\mathbb{R}$.
If the interval contains a single value, that the function is constant and we're done.
If it isn't, then denote by $m=\inf{I}$ and $M=\sup{I}$. We have that $m \lt M$ and $m, M \in \overline{\mathbb{R}}$



Source: [official solution](http://ssmr.ro/files/onm2014/faza_nationala/subiecte/solutii_11.pdf) 
 
