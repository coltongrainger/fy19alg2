---
title: "Module Theory: Basic Results"
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-01-14
revised: 2019-01-22
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
---

## Assignment due 2019-01-23

### [@DF04, number 10.1.1]

\gvn $R$ is a unital ring and $M$ is a left $R$-module.

\wts $0m = 0$ and $(-1)m = -m$ for all $m \in M$.

\pf Let $0_R \in R$ and $0_M \in M$ be the respective additive identities. Then For all $m \in M$, by distributivity, $1.m = (1 + 0_R).m = 1.m + 0_R.m$. We have $$m + 0_R.m = m \quad \text{ so by cancellation in $M$ } \quad 0_R.m = 0_M.$$ Knowing $0_R.m = 0_M$ implies $0_M = (1 + (-1))_R.m = 1.m + (-1).m$, so that $$-m = -(1.m) = (-1).m.$$ \qedsymbol

### [@DF04, number 10.1.3]

\gvn Say $rm = 0$ for some $r \in R$ and some $m \in M$ with $m \neq 0$.

\wts There is no $s \in R$ such that $sr =1$.

\pf Suppose for contradiction there's $s \in R$ such that $sr = 1$. Then both
\begin{align*} sr.m &= m\\ r.m &= 0 \end{align*}
Try adding:
\begin{align*} s.m + sr.m &= s.m + s.(r.m) &\text{ by module axioms }\\
    &= s.(m+r.m) &\text{ by distributivity of scalar multiplication }\\
    &= s.(m + 0) &\text{ by hypothesis }\\
    &= s.m,
\end{align*}
so $sr.m$ had better be $0_M$. But it's not, for $sr = 1$ implies $sr.m = m$, which together with the last argument is absurd. \qedsymbol

### [@DF04, number 10.1.4]

\gvn Let $M$ be the modules $R^n$ and let $\fa_1, \fa_2, \ldots, \fa_n$ be left ideals of $R$.

\wts Both of the following are submodules of $M$:
    
a. $P = \{(x_1, x_2, \ldots, x_n) : x_i \in \fa_i\}$,
b. $N = \left\{(x_1, x_2, \ldots, x_n) : x_i \in R \text{ and } \sum_i x_i = 0\right\}$.

\pf 

a. $P$ is nonempty, for $\prod 0_R$ is in each ideal, so in $P$ as well. Now say $x$ and $y$ are in $P$. The $i$th components of $x$ and $y$ are in each $\fa_i$, so the sum $x + y$ has $i$th component in each $\fa_i$ by closure of ideals under addition. Whence $x + y \in P$. Lastly, take a ring element $\alpha \in R$. Then $\alpha x  = \prod \alpha x_i$. By closure of ideals under left multiplication, $\alpha x_i \in \fa_i$. We conclude $\alpha x \in P$. 
b. $N$ is nonempty, as it contains the additive identity of $R^n$. Let $x$, $y$ be in $N$. Then $x+y$ has components summing $$\sum_i (x_i + y_i) = \sum_i x_i + \sum_i y_i = 0.$$ So $x + y \in N$. Consider $\alpha \in R$. Then $\alpha x$ has the sum $$\sum_i \alpha x_i = \alpha\left(\sum_i x_i\right) = \alpha.0 = 0,$$ by distributivity of multiplication over addition and previous argument [@DF04, number 10.1.3]. So $\alpha x \in N$. So $N$ is a submodule of $R^n$. \qedsymbol

### [@DF04, number 10.1.5]

\gvn Consider a left ideal $\fa$ of $R$. Let $$\fa M = \left\{\sum_\text{finite} a_i m_i : a_i \in \fa, m_i \in M\right\}.$$

\wts We have $\fa M$ as a submodule of $M$.

### [@DF04, number 10.1.6]

\gvn Let $M$ be a module over $R$ and $\{N_i\}$ be a nonempty collection of submodules.

\wts The intersection $\bigcap_i N_i$ is a submodule of $M$.

\pf Observe $0_M \in \cap_i N_i \neq \emptyset$. Next, suppose $x, y \in \cap_i N_i$. Then $x+y$ is in each $N_i$, by closure of submodules under addition. If $r \in R$, then so too $rx \in N_i$ for all $i$, by closure of submodules under scalar multiplication. Thence $x + y \in \cap_i N_i$ and $rx \in \cap_i N_i$. \qedsymbol

### [@DF04, number 10.1.8]

\newcommand{\Tor}[1]{\mathrm{Tor}\left( #1 \right)}

\gvn An element $m$ of the $R$-module $M$ is called a *torsion element* if $rm = 0$ for some nonzero element $r \in R$. The set of torsion elements is denoted $$\Tor{M} = \{ m \in M : rm = 0 \text{ for some nonzero } r \in R\}.$$

\wts 

a. If $R$ is an entire ring, then $\Tor M$ is a submodule of $M$ (called the *torsion submodule*).

b. If $R$ has zero divisors, then every nonzero $R$-module has nonzero torsion elements.

\pf

a. $\Tor M$ contains $0$. Now say $x,y \in \Tor M$. Then some $\alpha, \beta \in R$ kill $x$ and $y$ respectively: 
$$ \alpha x = 0, \quad \quad \beta y = 0.$$
Consider $x + y$. Because $R$ is commutative and by module axioms, 
$$ \alpha \beta(x + y) = \beta(\alpha x ) + \alpha(\beta y) = 0 + 0.$$
So the sum $x+y \in \Tor M$. Next say $r \in R$ is nonzero. Consider $rx$. We have $$\alpha r x = r (\alpha x) = 0$$ and because both $r$ and $\alpha$ are nonzero elements in an entire ring, it can't be that $r\alpha = 0$ and it must be that $rx = 0$. So $rx \in \Tor M$. 
b. Let $R$ have at least the pair of zero divisors $\alpha$ and $\beta$ with $\alpha\beta = 0$. Say that $M$ is a non-trivial $R$-module, and take nonzero $m$ in $M$. Either $\alpha m = 0$ or not---in the former case $m \in \Tor M$, and in the later $\beta(\alpha m) = \beta\alpha m = 0m = 0$, so that $\alpha m \in \Tor M$. Both cases force a nontrivial element in $\Tor M$. \qedsymbol

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
