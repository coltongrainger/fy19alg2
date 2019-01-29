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

\pf Let $0_R \in R$ and $0_M \in M$ be the respective additive identities. Then for all $m \in M$, by distributivity, $1.m = (1 + 0_R).m = 1.m + 0_R.m$. We have $$m + 0_R.m = m \quad \text{ so by cancellation in $M$ } \quad 0_R.m = 0_M.$$ Knowing $0_R.m = 0_M$ implies $0_M = (1 + (-1))_R.m = 1.m + (-1).m$, so that $$-m = -(1.m) = (-1).m.$$ \qedsymbol

### [@DF04, number 10.1.3]

\gvn Say $rm = 0$ for some $r \in R$ and some $m \in M$ with $m \neq 0$.

\wts There is no $s \in R$ such that $sr =1$.

*Proof by contradiction.* Suppose there's $s \in R$ such that $sr = 1$. Then both
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

\pf First, both $0_R \in \fa$ and $0_M \in M$ so that $0 \in \fa M$. Second, let $x, y \in \fa M$ where $x = \sum_i a_i m_i$ and $y = \sum_j b_j n_j$. This sum of finite sums is finite, so that $x + y$ is in $\fa M$. Lastly, for any $r \in R$, consider $rx = r\left(\sum_i a_i m_i\right) = \sum_i (ra_i) m_i \in \fa M$. \qedsymbol

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

\pf Denote the annihilator of $N$ in $R$ by $\fa$. First note $0 \in \fa$ as $0n = 0$ for all $n \in N$. Next take $\alpha, \beta \in \fa$. Then $(\alpha + \beta)n = \alpha n + \beta n = 0 + 0 = 0$. Then $\alpha + \beta \in \fa$; we see $\fa$ is closed under finite sums. Moreover, each $\alpha \in \fa$ has an additive inverse $-\alpha \in R$. Since $0 = - \alpha n = (- \alpha )n$, $\fa$ is closed under additive inverses. So $\fa$ is an abelian subgroup of $R$. Now say that $r \in R$ and $a \in \fa$. Then $$(ra)n = r(an) = r(0) = 0,$$ so $ra \in \fa$. Consider $ar$. We have $$(ar)n = a(rn) = a(n_0) = 0, \quad \quad \text{ where $rn = n_0 \in N$,}$$ so that $ar  \in \fa$. We conclude $\fa$ is a two-sided ideal. \qedsymbol

### [@DF04, number 10.1.15]

\gvn Say $M$ is a finite abelian group. $M$ is naturally a $\ZZ$-module. 

\wts This action cannot be extended to make $M$ into a $\QQ$-module.

*Proof by contradiction.* Suppose $\QQ$ extends the action of $\ZZ$ on $M$. Pick any nonzero $m \in M$. I claim for each $n \in \
\NN$, $\frac 1 n . m \neq 0$. To wit, by the unital module axiom, $$m = n . \left( \frac 1 n . m \right) \neq n.( 0 ) = 0 \quad \text{ by assumption than $m$ is nonzero.}$$ I claim for each distinct pair $a, b \in \NN$, the image of $m$ under the action of $\frac 1 a$ and $\frac 1 b$ is distinct. Else we could find $$ 0 = \frac 1 a . m - \frac 1 b . m = \left(\frac 1 a - \frac 1 b\right).m = \frac 1 {ab} .m,$$ which is prevented by the previous claim. Since $\NN$ is infinite, the image of $\frac 1 n . m$ in $M$ as $n$ ranges through $\NN$ must be infinite, which is absurd! (By hypothesis, $M$ is a finite group.) \qedsymbol

### [@DF04, number 10.1.18]

\gvn Say we have a linear transformation $T \colon \RR^2 \to \RR^2$ with the associated matrix $$A_T = \begin{bmatrix} 0 & 1 \\ -1 & 0\end{bmatrix}, \quad \text{ with respect to the standard basis.}$$ Consider $V = \RR^2$ as an $\RR[x]$-module where scalar multiplication is obviously defined by constant polynomials and $x$ acts by the linear transformation $x.v = Av$. 

\wts If $M$ is a submodule of $V$, then $M$ is trivial or $V$. 

\pf Say $M$ is a nontrivial submodule of $V$. Take some nonzero $m \in M$. By closure under the ring action, $x.m \in M$. I claim both $m$ and $x.m$ are nonzero and orthogonal, in the sense that $$x.m = \begin{bmatrix} 0 & 1 \\ -1 & 0\end{bmatrix} \begin{bmatrix} m_1 \\ m_2 \end{bmatrix} = \begin{bmatrix} m_2 \\ -m_1\end{bmatrix} \text{ and } (x.m)^T m = \begin{bmatrix} m_1 & m_2\end{bmatrix} \begin{bmatrix} m_2 \\ -m_1\end{bmatrix} = 0.$$ So $x.m$ and $m$ span $\RR^2$, which gives $M \supset \RR^2$. \qedsymbol

### [@DF04, number 10.1.19]

\gvn Say we have a linear transformation $T \colon \RR^2 \to \RR^2$ with associated matrix $$A_T = \begin{bmatrix} 0 & 0 \\ 0 & 1\end{bmatrix}, \quad \text{ with respect to the standard basis.}$$ As before, consider $V = \RR^2$ as an $\RR[x]$-module where $x$ acts by the linear transformation $x.v = Av$.

\wts If $M$ is a submodule of $V$, then $M$ is trivial, all of $V$, the $x$-axis, or the $y$-axis.

\pf Let $M$ be a nontrivial proper submodule of $V$. In particular, $M$ is an $\RR$-linear proper subspace, and as an $\RR$-vector space, $M$ has dimension exactly $1$. It follows that $M$ is of the form $\{\alpha v : \alpha \in \RR\}$ for some nonzero $v \in M$. Consider $Av$, which has exactly one nonzero component. Because $v$ is an eigenvector of the matrix $A$, it must be that $v$ has exactly one nonzero component. So $M$ is either the $x$- or $y$-axis. \qedsymbol

### [@DF04, number 10.1.20]

\gvn Let $F = \RR$, let $V = \RR^2$, and let $T$ be the linear transformation from $V$ to $V$ that is rotation clockwise about the origin by $\pi$ radians.

\wts Every subspace of $V$ is an $F[x]$-submodule for this $T$.

\pf Say $\RR^2$ is an $\RR[x]$-module with the action of $x \in \RR[x]$ given by $$x.v = Av \quad \text{ where } \quad A = \begin{bmatrix} -1 & 0 \\ 0 & -1\end{bmatrix} \quad \text{ w.r.t. the standard basis.}$$ The property of being an $\RR[x]$-submodule is stronger than that of being an $\RR$-linear subspace, so the submodules of $\RR^2$ are all subspaces. Conversely, if $V \subset \RR^2$ is a subspace, then $V$ is an abelian group. For any $v \in V$, the image of $v$ under the action of $x$ is $x.v = -v$. So $V$ is stable under the linear transformation; whence $V$ is an $\RR[x]$-submodule. \qedsymbol

### [@DF04, number 10.1.21]

\gvn Let $n \in \ZZ^+$, $n >1$, and $R$ be the ring $\sM_n(F)$ of $n \times n$ matrices from the field $F$. Let $M\subset \sM_n(F)$ be $$M = \left\{(a_i^j) : a_i^j = 0 \text{ if } j > 1\right\},$$ that is, the set of matrices with arbitrary elements of $F$ in the first column and zeros
elsewhere. 

\wts 

- $M$ is a submodule of $R$ when $R$ is considered as a left module over itself.
- $M$ is *not* a submodule of $R$ when $R$ is considered as a right module.

\pf In either case (of $\sM_n(F)$ being a left or right module over itself), the set $M$ is an abelian subgroup of the ring $\sM_n(F)$. 

- Now consider $\sM_n(F)$ as a left module. Let $[a_{ij}] \in \sM_n(F)$ and $[m_{jk}] \in M$ (with respect to the standard unit basis for $F^n$). Then $$[a_{ij}][m_{jk}] = \left[\sum_{j=1}^n a_{ij} m_{jk}\right] \in M,$$ as $m_{jk} = 0$ whenever the index $k > 0$. So $M$ is closed under scalar multiplication. So $M$ is a left submodule.
- On the other hand, consider $\sM_n(F)$ as a right module. Then it's not necessarily true that for $[a_{jk}] \in \sM_n(F)$ and $[m_{ij}] \in M$ that $$[m_{ij}][a_{jk}] = \left[\sum_{j=1}^n m_{ij} a_{jk}\right]$$ will be in $N$, e.g., when $a_{12} \neq 0$. Because $M$ is not closed under scalar multiplication, $M$ is *not* (right) submodule. \qedsymbol

## References
