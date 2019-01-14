---
title: "Introduction to Module Theory: Basic Definitions and Examples"
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-01-14
bibliography: /home/colton/coltongrainger.bib
macros: true
revised:
---

\setcounter{section}{0}

## Assignment due 2019-01-13

### [@DF04, number 10.1.1]

\gvn $R$ is a unital ring and $M$ is a left $R$-module.

\wts $0m = 0$ and $(-1)m = -m$ for all $m \in M$.

### [@DF04, number 10.1.3]

\gvn Say $rm = 0$ for some $r \in R$ and some $m \in M$ with $m \neq 0$.

\wts There is no $s \in R$ such that $sr =1$.

### [@DF04, number 10.1.4]

\gvn Let $M$ be the modules $R^n$ and let $\fa_1, \fa_2, \ldots, \fa_n$ be left ideals of $R$.

\wts Both of the following are submodules of $M$:
    
a. $P = \{(x_1, x_2, \ldots, x_n) : x_i \in \fa_i\}$,
b. $N = \left\{(x_1, x_2, \ldots, x_n) : x_i \in R \text{ and } \sum_i x_i = 0\right\}$.

### [@DF04, number 10.1.5]

\gvn Consider a left ideal $\fa$ of $R$. Let $$\fa M = \left\{\sum_\text{finite} a_i m_i : a_i \in \fa, m_i \in M\right\}.$$

\wts We have $\fa M$ as a submodule of $M$.

### [@DF04, number 10.1.6]

\gvn Let $M$ be a module over $R$ and $\{N_i\}$ be a nonempty collection of submodules.

\wts The intersection $\bigcap_i N_i$ is a submodule of $M$.

### [@DF04, number 10.1.8]

\newcommand{\Tor}[1]{\mathrm{Tor}\left( #1 \right)}

\gvn An element $m$ of the $R$-module $M$ is called a *torsion element* if $rm = 0$ for some nonzero element $r \in R$. The set of torsion elements is denoted $$\Tor{M} = \{ m \in M : rm = 0 \text{ for some nonzero } r \in R\}.$$

\wts 

a. If $R$ is an integral domain, then $\Tor M$ is a submodule of $M$ (called the *torsion submodule*).

c. If $R$ has zero divisors, then every nonzero $R$-module has nonzero torsion elements.

### [@DF04, number 10.1.9]

\gvn If $N$ is a submodule of $M$, the *annihilator of $N$ in $R$* is defined to be $$\{r \in R : rn = 0 \text{ for all } n \in N\}.$$

\wts The annihilator of $N$ in $R$ is a $2$-sided ideal of $R$.

### [@DF04, number 10.1.15]

\gvn Say $M$ is a finite abelian group. $M$ is naturally a $\ZZ$-module. 

\wts This action cannot be extended to make $M$ into a $\QQ$-module.

### [@DF04, number 10.1.18]

\gvn Let $F = \RR$, let $V = \RR^2$, and let $T$ be the linear transformation from $V$ to $V$ that is rotation clockwise about the origin by $\pi / 2$ radians.

\wts $V$ and $0$ are the only $F[x]$-submodules for this $T$.

### [@DF04, number 10.1.19]

\gvn Let $F = \RR$, let $V = \RR^2$, and let $T$ be the linear transformation from $V$ to $V$ that is projection onto the $y$-axis. 

\wts $V$, $0$, the $x$-axis and the $y$-axis are the only $F[x]$-submodules for this $T$.

### [@DF04, number 10.1.20]

\gvn Let $F = \RR$, let $V = \RR^2$, and let $T$ be the linear transformation from $V$ to $V$ that is rotation clockwise about the origin by $\pi$ radians.

\wts Every subspace of $V$ is an $F[x]$-submodule for this $T$.

### [@DF04, number 10.1.21]

\gvn Let $n \in \ZZ^+$, $n >1$, and $R$ be the ring $\sM_n(F)$ of $n \times n$ matrices from the field $F$. Let $M\subset \sM_n(F)$ be $$M = \left\{(a_i^j) : a_i^j = 0 \text{ if } j > 1\right\},$$ that is, the set of matrices with arbitrary elements of $F$ in the first column and zeros
elsewhere. 

\wts 

- $M$ is a submodule of $R$ when $R$ is considered as a left module over itself.
- $M$ is *not* a submodule of $R$ when $R$ is considered as a right module.

## References
