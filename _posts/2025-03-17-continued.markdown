---
layout: post
title:  "Continued fractions"
date:   2025-03-17 10:50:12 +0800
categories: numbers
---
added 22 July 2025: [preprint](/assets/numbers/pi.pdf) about the Legendre duality for these summations of Farey series.



Consider a simple continued fraction

$a_{0}\in \mathbb{Z} , a_{n}\in \mathbb{Z}_{\geq 0}, 
\quad \xi=a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\ddots}}}=\left[a_0, a_1, \dotsc\right].$

Define
\begin{aligned}
& h_{-2}=0 \quad h_{-1}=1 \quad h_n=a_n h_{n-1}+h_{n-2} \\
& k_{-2}=1 \quad k_{-1}=0 \quad k_n=a_n k_{n-1}+k_{n-2}.\\
\end{aligned}



Then $\quad a_0+\cfrac{1}{a_1+\cfrac{1}{a_2+\cfrac{1}{a_3+\dotsb +\cfrac{1}{a_n}}}}=\left[a_0, a_1, \dotsc, a_n\right] =\frac{h_n}{k_n}$ and $\frac{h_n}{k_n} \rightarrow \xi$.

Then the following hold:

$\sum_{n=-1}^{\infty}\left|k_n \xi-h_n\right| \cdot a_{n+1}=\xi+1$ 
for an irrational $\xi$

$\sum_{n=-1}^N\left|k_n \xi-h_n\right| a_{n+1}=\xi+1-\frac{1}{p}$ 
for a rational $\xi=q/p=[a_0,\dots,a_{N+1}]$

$\sum_{n=-1}\limits^{\infty}\left|k_n \xi-h_n\right|^2 \cdot a_{n+1}=\xi$ 
if $\xi$ is irrational and  
$\sum_{n=-1}\limits^{N}\left|k_n \xi-h_n\right|^2 \cdot a_{n+1}=\xi$ 
for $\xi=[a_0,\dots,a_{N+1}]$.
   
I know at least two elementary proofs of these formulae. 
I believe that these formulae were discovered before. 
Have you seen something like that?

[asked here](https://mathoverflow.net/questions/489340/new-summation-formulae-for-continued-fractions-reference-request?noredirect=1#comment1276530_489340)


chatgpt [deepresearch](https://chatgpt.com/s/dr_680c598d7b2881919325ad976b04191d) answers better: 

![image tooltip here](/assets/numbers/26042025.png)