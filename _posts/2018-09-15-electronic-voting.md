---
layout: post
title:  "Electronic Voting"
tags: [cryptography, electronic voting, secret sharing]
use_math: true
---

<figure>
    <img src='/assets/voting.png' alt='xkcd joke about voting' width="50%" align="middle"/>
    <figcaption>Taken from <a href="https://xkcd.com/">xkcd</a></figcaption>
</figure>

The idea of being able to vote in an election remotely, without going to the polling place, appeared 
quite a long time ago. It is appealing for a couple of reasons, such as the possibility to increase 
voting turnout. However, e-voting* is not generally viewed as a complete replacement of paper voting, 
but rather as complementary to it.

E-voting is a more complex problem than e-banking or e-commerce because of the compulsory
requirements of assuring both privacy and correctness of the voting process. 
For example, an open problem of e-voting is represented by the possibility of voters to sell their credentials to 
someone else who can vote on their behalf ([1](#1)). This situation can be alleviated by allowing voters to cast 
their vote multiple times, with their last choice being recorded as valid or even permitting to cast a paper vote too,
this last one having priority over the electronic ones ([2](#2)).

People have not yet agreed on a theoretical solid basis for e-voting, so there is still a long way to go 
before reliable practical implementations come out. 

Nonetheless, some countries, among which Estonia, Norway or Switzerland, have made attempts to integrate e-voting
into their electoral systems.
 
The most important developed technologies: secret sharing schemes or other homomorphic techniques [12], [17], [42], 
mix-nets [6], [29], blind signatures [5], [7] or, more recently, blockchain [some links].


Bibliography:
<a name="1">(1) Schneider A., Meter C., Hagemeister P.: Survey on Remote Electronic Voting (2017). arXiv preprint arXiv:1702.02798.</a> 

<a name="2">(2) Madise Ü., Martens T.: E-voting in Estonia 2005. The first practice of country-wide binding Internet voting in the world. Electronic voting (2006), 86.</a>


\* Electronic voting is sometimes used as a broader term, referring also to the use of machines which facilitate
the voting process at the polling place. In this post, however, by electronic voting I mean remote
online voting.
