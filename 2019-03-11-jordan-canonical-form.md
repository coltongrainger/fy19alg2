---
title: Assignment 8
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-03-11
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

## Assignment due 2019-03-11

### Notation


Let $A$ be an $n \times n$ matrix and let $F$ be a field containing the eigenvalues of $A$. Then $A \in \sM_n(F)$. 

<!---
Let $V$ be an $n$-dimensional vector space over $F$, with $T \colon V \to V$ the linear transformation induced by $A$ after choosing a basis. Suppose $P \in \gl[n]{F}$ is a matrix such that $PAP^{-1}$ is in Jordan canonical form.
--->

### [@DF04, number 12.3.3]

\given Let $A \in \sM_n(F)$ have eigenvalues $\lambda_1, \ldots, \lambda_n$.

\wts For each integer $k \ge 1$, the eigenvalues of $A^k$ are $\lambda_1^k, \ldots, \lambda_n^k$.

\pf Similar matrices have the same characteristic polynomial, and therefore the eigenvalues of $A$ are the same as the eigenvalues of the Jordan canonical form $J = PAP^{-1}$. Now because $J$ is a direct sum of its Jordan blocks, it suffices to prove: 

> If an arbitrary Jordan block $J_\lambda$ has eigenvalue $\lambda$ with multiplicity $\ell$, then $J_\lambda^k$ has eigenvalue $\lambda^k$ with multiplicity $\ell$.

Consider such a Jordan block $J_\lambda$, with eigenvalue $\lambda$ of multiplicity $\ell$. It is an upper triangular $\ell \times \ell$ matrix. Recall that the $\ell \times \ell$ upper triangular matrices form a subring of $\sM_\ell(F)$, and that the diagonal of a product of two upper triangular matrices is the entry-wise product of the two diagonals:

$$
\mqty(\dmat{a_{11},\ddots,a_{\ell\ell}})
\mqty(\dmat{b_{11},\ddots,b_{\ell\ell}}) 
  = \mqty(\dmat{a_{11}b_{11},\ddots,a_{\ell\ell}b_{\ell\ell}}).
$$

Therefore, because $J^k_\lambda$ is a finite product of upper triangular matrices, each entry of along the diagonal of $J^k_\lambda$ is $\lambda^k$. Moreover, the matrix $xI - J_\lambda^k$ is upper triangular, and because the determinant of an upper triangular matrix is the product of its diagonal entries, $J_\lambda^k$ has characteristic polynomial $\prod_{i=1}^\ell (x - \lambda^k)$. Therefore $J_\lambda^k$ has eigenvalue $\lambda^k$ with multiplicity $\ell$. Applying this argument to each block of the Jordan canonical form $J = PAP^{-1}$, it is apparent that $J^k = PA^k P^{-1}$ has eigenvalues $\lambda_1^k, \ldots, \lambda_n^k$.  \qedsymbol

### [@DF04, number 12.3.17]

\given Let $A^t$ be the transpose of $A \in \sM_n(F)$.

\wts $A$ is similar to $A^t$.

\pf Say $J = PAP^{-1}$ is the JCF of $A$. Because $P$ is invertible, the transpose $P^t$ is also invertible. Therefore $A^t$ is similar to $J^t = (P^{-1})^t A^t P^t$. Because similarity is an equivalence relation, 
$A$ is similar to $A^t$ if and only if $J$ is similar to $J^t$. 

As $J$ and $J^t$ are block diagonal matrices, they are similar if and only if their blocks are similar up to some permutation. Thus, to show $J$ is similar to $J^t$, it suffices to demonstrate that an arbitrary Jordan block $J_\lambda$ is similar to its transpose $J_\lambda^t$. In particular, appealing to Theorem 12.15 and the Chinese remainder theorem, $J_\lambda$ and $J_\lambda^t$ are similar if they have the same *single* elementary divisor. 

Let $c(x)$, $m(x)$, $c_t(x)$, and $m_t(x)$ be the characteristic and minimal polynomials for $J_\lambda$ and $J_\lambda^t$ respectively. We need to show 
$$c(x) = m(x) = m_t(x) = c_t(x).$$

Because $J_\lambda$ is a Jordan block, it has a single elementary divisor. Therefore
\begin{equation}
\label{eq:mincharequaltranspose}
  m(x) = c(x).
\end{equation}
As the determinant of a matrix is invariant under transposition, the characteristic polynomial $c_t(x)$ of $J_\lambda^t$ is 
\begin{equation}
\label{eq:charpolytranspose}
  c_t(x) = \det(xI - J_\lambda^t)  = \det((xI - J_\lambda)^t) =\det(xI - J_\lambda) = c(x).
\end{equation}
Now suppose $m_t(x) = \sum_k a_k x^k$ is the minimal polynomial of $J_\lambda^t$. Then 
\begin{equation}
\label{eq:minpolytranspose}
  \sum_k a_k ( J_\lambda^t )^k = m_t(J_\lambda^t) = 0.
\end{equation}
Because $(J^t_\lambda)^k = ( J^k_\lambda )^t$, transposing each term in equation \eqref{eq:minpolytranspose} implies 
\begin{equation}
\label{eq:satisfiestranspose}
\sum_k a_k ( J_\lambda )^k = m_t(J_\lambda) = 0.
\end{equation}
Because $m(x)$ is minimal among monic polynomials that $J_\lambda$ satisfies, equation \eqref{eq:satisfiestranspose} implies 
$$m(x) \mid m_t(x).$$
By Cayley-Hamilton, $m_t(x) \mid c_t(x)$. So by \eqref{eq:charpolytranspose}, 
$$m_t(x) \mid c(x),$$ and this with \eqref{eq:mincharequaltranspose} implies 
$$m_t(x) \mid m(x).$$ 
Therefore, by divisibility considerations, $m(x)= m_t(x)$. (And so by degree considerations, $m_t(x) = c_t(x)$.)

We have demonstrated that $J_\lambda$ and $J_\lambda$ have the same elementary divisor $m(x)$. Repeating this argument for each block of $J$ and $J^t$, one may show $J$ is similar to $J^t$. We conclude $A$ is similar to $A^t$. \qedsymbol

### [@DF04, number 12.3.18]

\given Suppose $T$ is a linear transformation with characteristic polynomial $c(x) = (x-2)^2(x-3)^2$.

*To exhibit*. A Jordan canonical form for each possible similarity class of $T$.

*Exhibition.*  There are $3$ integer partitions of $3$ and $2$ integers partitions of $2$, corresponding to the possible elementary divisors of $c(x)$. The transformation $T$ belongs to one of the following $6$ similarity classes, represented by Jordan canonical form.
$$
\mqty(\dmat{2,2,2,3,3}), 
\mqty(\dmat{2&1\\&2, 2, 3,3}) 
\mqty(\dmat{2&1&\\&2&1\\&&2,3,3}),
$$
$$
\mqty(\dmat{2,2,2,3& 1\\&3}), 
\mqty(\dmat{2&1\\&2, 2, 3& 1\\&3}),
\mqty(\dmat{2&1&\\&2&1\\&&2,3& 1\\&3}).
$$
\qedsymbol



### [@DF04, number 12.3.20]

\given Let $p$ be a prime and consider the following matrices in $\sM_p(\FF_p)$.

$$R = 
\begin{pmatrix}
\mqty{0&&\\1&0&\\&1&\ddots\\&&\ddots} & \mqty{&1\\&\\&\\0&}\\
\mqty{&&} & \mqty{1&0}
\end{pmatrix}
\qq{and} 
J =
\begin{pmatrix}
1 & & & & \\
1 & 1 & & & \\
  & 1 & \ddots & & \\
  & & \ddots & 1 &\\
  & & & 1 & 1
\end{pmatrix}
$$

\wts $R$ and $J$ are similar in $\sM_p(\FF_p)$.

\pf Notice $R$ is in RCF and $J$ is in JCF, each with one block corresponding to a single invariant factor. Computing $\det(xI - R)$ and $\det(xI - J)$, we find

- $R$ has invariant factor $x^p - 1$, and
- $J$ has invariant factor $(x - 1)^p$. 

Because $\FF_p$ is a field of characteristic $p$, the binomial $(x-1)^p$ in $\FF_p[x]$ expands to 
$$\sum_{k=1}^p {p \choose k} x^{p-k}(-1)^k \qq{with} {p \choose k} = 0 \qq{for all} 0 < k < p.$$
Then $x^p - 1 = (x-1)^p$ in $\FF_p[x]$. So $R$ and $J$ have the same invariant factor. Therefore $R$ and $J$ are similar in $\sM_p(\FF_p)$. \qedsymbol

### [@DF04, number 12.3.21]

\given Let $A^2 = A$ be an idempotent $n \times n$ matrix over $F$.

\wts $A$ is diagonalizable and is similar to a matrix with only $1$s and $0$s along the diagonal.

\pf The minimal polynomial $m(x)$ divides $x^2 - x = x(x-1)$, as our hypothesis is that $A^2 - A = 0$. So $m(x)$ is one of the following: $x$, $x-1$, or $x(x-1)$. If $m(x) = x$, then *all* of the elementary divisors of $A$ are $x$. In this case, $A = 0$ is diagonalizable. In the case that $m(x) = x-1$, then *all* of the elementary divisors of $A$ are $x-1$, and $A = I$ is diagonalizable. Lastly, in the case that $m(x) = x(x-1)$, the invariant factors are either 
$$x \mid \ldots \mid x(x-1) \qq{or} x-1 \mid \ldots \mid x(x-1).$$
We deduce the elementary divisors are *all* either $x$ or $x-1$. Thus $A$ has a JCF consisting of $n$ Jordan blocks, each block associated to either the eigenvalue $0$ or the eigenvalue $1$, with multiplicity $1$. \qedsymbol

### [@DF04, number 12.3.22]

\given Let $A \in \sM_n(F)$ and require $A^3 = A$.

\wts If $F$ is any field *not* of characteristic $2$, then it is possible that $A$ is diagonalizable. 

\pf The minimal polynomial $m(x)$ of $A$ divides $x^3 - x = x(x-1)(x+1)$. Suppose the characteristic of $F$ is not $2$. Then $m(x)$ is the product of distinct linear factors. Because $m(x)$ has no repeated roots, by Corollary 25, $A$ is diagonalizable.

Suppose on the other hand that $F$ has characteristic $2$. Then perhaps $m(x)$ has $(x+1)^2$ as a factor. If so, because $m(x)$ has repeated roots, $A$ is *not* diagonalizable. \qedsymbol

## References

