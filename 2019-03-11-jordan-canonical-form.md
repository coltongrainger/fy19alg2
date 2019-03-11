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

\begin{equation}
\mqty(\dmat{a_{11},\ddots,a_{\ell\ell}})
\mqty(\dmat{b_{11},\ddots,b_{\ell\ell}}) 
  = \mqty(\dmat{a_{11}b_{11},\ddots,a_{\ell\ell}b_{\ell\ell}}).
\end{equation}

Therefore, because $J^k_\lambda$ is a finite product of upper triangular matrices, each entry of along the diagonal of $J^k_\lambda$ is $\lambda^k$. Moreover, the matrix $xI - J_\lambda^k$ is upper triangular, and because the determinant of an upper triangular matrix is the product of its diagonal entries, $J_\lambda^k$ has characteristic polynomial $\prod_{i=1}^\ell (x - \lambda^k)$. Therefore $J_\lambda^k$ has eigenvalue $\lambda^k$ with multiplicity $\ell$. Applying this argument to each block of the Jordan canonical form $J = PAP^{-1}$, it is apparent that $J^k = PA^k P^{-1}$ has eigenvalues $\lambda_1^k, \ldots, \lambda_n^k$.  \qedsymbol

[@DF04, number 12.3.17]

\given Let $A^t$ be the transpose of $A \in \sM_n(F)$.

\wts $A$ is similar to $A^t$.

\pf Say $J = PAP^{-1}$ is the JCF of $A$. Because $P \in \gl[n]{F}$, the transpose $P^t \in \gl[n]{F}$. Therefore $A^t$ is similar to the transpose $J^t = (P^{-1})^t A^t P^t$. Because similarity is an equivalence relation, if we argue $J$ is similar to $J^t$, then we may conclude $A$ is similar to $A^t$. 

Because $J$ and $J^t$ are block diagonal matrices, they are similar if and only if their blocks are similar up to some permutation. So to prove $J$ is similar to $J^t$, it suffices to argue that an arbitrary Jordan block $J_\lambda$ is similar to its transpose $J_\lambda^t$, i.e., that $J_\lambda$ and $J_\lambda^t$ have the same *single* elementary divisor.

Because $J_\lambda$ is a Jordan block, its minimal polynomial $m$ is the same as its characteristic polynomial $c$. 









## References

