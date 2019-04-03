---
title: Assignment 10 (\S 13.5)
author: Colton Grainger (MATH 6140 Modern Algebra 2)
date: 2019-04-03
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
---

### [@DF04, number 13.5.3]

\given Suppose $n, d \in \NN$. (If either $n$ or $d$ is $0$, this problem is trivial.) Fix a field $F$ of characteristic $0$.

\wts In $\ZZ$, $d$ divides $n$ if and only if, in $F[x]$, $x^d - 1$ divides $x^n -1$.

\pf Immediately note $d \le n$. For if $x^n -1$ is in the ideal $\langle x^d - 1\rangle$, then $d \le n$ by degree considerations; conversely, if $d \mid n$, then $d \le n$ by assumption that $n, d \in \NN$. In either case, in the Euclidean domain $\ZZ$, there exist unique (here non-negative) $q, r \in \NN\cup\{0\}$ such that 
$$
n = qd + r \qq{where} 0 < r \le d.
$$
And so the proposition is concerned with whether or not the polynomial
\begin{equation}
\label{eq:required}
x^n - 1 = x^{qd + r} - 1 = (x^{qd} - 1)x^r + x^r - 1 \qq{is in the ideal} \langle x^d - 1\rangle.
\end{equation}

Recall the factorization [@Lan02, number VI.3]
$$
x^d - 1 = \prod_{\zeta} (x - \zeta)
$$
where the product is taken over all $d$-th roots of unity. Since these roots are closed under multiplication, they form a *subgroup* of $F^\times$. Because this subgroup (along with any finite subgroup of $F^\times$) is cyclic, we may group together all the terms belonging to the $d$-th roots of unity having the same order. Defining 
$$
\Phi_m(x) = \prod_{\text{order }\zeta = m} (x - \zeta),
$$
we obtain
\begin{equation}
\label{eq:dthcyclotomic}
x^d - 1 = \prod_{m \mid d} \Phi_m(x).
\end{equation}

To finish the proof. ($\Rightarrow$) If $d \mid n$, then \eqref{eq:dthcyclotomic} implies
\begin{equation}
\label{eq:formdivides}
x^d - 1 = \prod_{m \mid d} \Phi_m(x) \qq{divides} \prod_{\ell \mid n} \Phi_\ell(x) = x^n -1
\end{equation}
because

- each divisor $m$ of $d$ corresponds to a factor $\Phi_m(x)$ on the LHS of \eqref{eq:formdivides}, and
- each divisor $m$ of $d$ is also some divisor $\ell$ of $n$, so
- each factor $\Phi_m(x)$ on the LHS of \eqref{eq:formdivides} also appears as a factor $\Phi_\ell(x)$ on the RHS of \eqref{eq:formdivides}.

($\Leftarrow$) Conversely, suppose  $x^n - 1$ is contained in $\langle x^d - 1\rangle$. Consider the form of $x^n -1$ in \eqref{eq:required}. Because $r < d$, by degree considerations, $x^r -1$ cannot be in $\langle x^d -1 \rangle$ unless $r = 0$. But $d \mid qd$ implies
\begin{equation}
\label{finish}
x^{qd} - 1 = \prod_{\ell \mid qd} \Phi_\ell(x) \qq{ is contained in } \left\langle\prod_{m \mid d} \Phi_m(x) \right\rangle = \langle x^d - 1\rangle.
\end{equation}
Then \eqref{finish} with our supposition that $x^n - 1 \in \langle x^d - 1\rangle$ forces the difference
$$
0 = x^r - 1 + (x^{qd} - 1)x^r - \langle x^d - 1\rangle = x^r - 1 - \langle x^d -1 \rangle.
$$
and we conclude the remainder $r$ of the integer division of $n$ by $d$ is $0$. \qedsymbol

### [@DF04, number 13.5.6]

\given Fix a field $F$ of characteristic $0$, a prime $p \ge 2$, and a nonnegative integer $n$. Consider the polynomial $x^{p^n -1} - 1$ over $F$.

\wts 

(i) $x^{p^n -1} - 1 = \prod_{\zeta\in \FF_{p^n}^\times}(x - \zeta)$.

(ii) $\prod_{\zeta\in \FF_{p^n}^\times} \zeta = (-1)^{p^n}$.

(iii) $(p-1)! \equiv -1 \pmod{p}$.

\pf

First to establish $x^{p^n -1} - 1$ is separable. The derivative
$$
D\qty( x^{p^n -1} - 1 ) = (p^n -1)x^{p^n-2} \qq{has root $0$ of multiplicity $p^n -2$}
$$
but no roots in common with $x^{p^n -1} - 1$. Thus $x^{p^n -1} - 1$ is separable, with $p^n -1$ distinct roots of unity. Recall [@DF04, number 13.5.3] the factorization
\begin{equation}
\label{factorrootsofunity}
x^{p^n -1} - 1 = \prod_{\zeta} (x - \zeta)
\end{equation}
where the product is taken over all $p^n-1$-th roots of unity. In particular, the $p^n-1$-th roots of unity form a cyclic group of order $p^n-1$ that's (non-canonically) isomorphic to the cyclic group $\FF_{p^n}^\times$ of the same order. Embedding $\FF_{p^n}^\times$ in $F$, with \eqref{factorrootsofunity} we have proved (i).

\renewcommand{\ev}[2]{\mathrm{ev}_{#1}\qty(#2)}

The evaluation map $\mathrm{ev}_0 \colon F[x] \to F$ produces
$$
-1 = \ev 0 {x^{p^n -1} - 1} = \ev 0 {\prod_{\zeta \in \FF_{p^n}^\times} (x - \zeta)} = (-1)^{p^n-1}\qty( \prod_{\zeta \in \FF_{p^n}^\times} \zeta ),
$$
which proves (ii).

Lastly, fix $n = 1$ and identify $\FF_{p^1}$ with $\ZZ/(p)$ (against geometric intuition). Then the result of part (ii) forces
$$
(p-1)! \pmod{p} = \prod_{\zeta \in (\ZZ/(p))^\times} \zeta = (-1)^p = -1
$$
for any odd prime $p$. If $p=2$, then $1 = 1! = -1 \pmod{2}$ trivially. We've proven (iii), *Wilson's theorem*. \qedsymbol

\newpage

### [@DF04, number 13.6.9]

\given $1,x$ in the polynomial ring $F[x]$ over the field $F$. 

\wts 

(i) ${pn \choose pi}$ is the coefficient of $x^{pi}$ in the binomial expansion $(1+x)^{pn} = \sum_{k=0}^{pn} {pn \choose k} 1^{k}x^{pn-k}$. 

(ii) ${pn \choose pi} = {n \choose i} \pmod{p}$

\pf For (i), observe that the coefficient of $x^{pi}$ in the binomial expansion 
$$(1+x)^{pn} = \sum_{k=0}^{pn} {pn \choose k} x^{k}$$
is found to be 
$${pn \choose k} \qq{such that $k=pi$}$$
because $k$ is strictly increasing as an index on $\{0, \ldots, pn\}$. 

For (ii), suppose $\mathrm{char}(F) =p$. Because 
$$p \qq{divides} \frac{p!}{\ell!(p-\ell)!} \qq{for $0 < \ell < p$}$$
and $${p \choose \ell} = \frac{p!}{\ell!(p-\ell)!}$$
we have that
$$(1+x)^{p} = \sum_{\ell=0}^{p} {p \choose \ell} x^{\ell} = 1 + \underbrace{0 + \cdots + 0}_\text{$p-1$ terms} + x^p.$$
From one perspective, 
$$(1+x^p)^n = \sum_{\ell=0}^{n} {n \choose \ell} (x^p)^{\ell}.$$
Yet from another
$$(1+x^p)^n = (1+x)^{pn} = \sum_{k=0}^{pn} {pn \choose k} x^{k}.$$
Therefore whenever $k = p \ell$, we have ${pn \choose pi} = {n \choose i} \pmod{p}$. \qedsymbol

## References
