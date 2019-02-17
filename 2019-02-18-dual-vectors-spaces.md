---
title: Dual Vector Spaces
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-02-17
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

## Assignment due 2019-02-18

### [@DF04, number 11.3.2.a]

Let $V$ be the collection of polynomials with coefficients in $\QQ$ in the variable $x$ of degree at most $5$ with $1, x, x^2, \ldots, x^5$ as basis. Prove that the following are elements of the dual space of $V$ and express them as linear combinations of the dual basis:

(a) $E \colon V \to \QQ$ defined by $E(p(x)) = p(3)$.
(a) $\phi \colon V \to \QQ$ defined by $\phi(p(x)) = \int_0^1 p(t)\, dt$.
(a) $\phi \colon V \to \QQ$ defined by $\phi(p(x)) = \int_0^1 t^2p(t)\, dt$.
(a) $\phi \colon V \to \QQ$ defined by $\phi(p(x)) = p'(5)$.

### [@DF04, number 11.3.3]

\providecommand{\Ann}[1]{\operatorname{Ann}\left( #1 \right)}

Let $S$ be any subset of $V^*$ for some finite dimensional space $V$. Define the *annihilator of $S$ in $V$* as $$\Ann{S} := \{v \in V: f(v) = 0 \text{ for all } f \in S\}.$$ 

(a) Prove that $\Ann{S}$ is a subspace of $V$.
(a) Omitted.
(a) Let $W_1$ and $W_2$ be subspaces of $V^*$. Prove that $W_1 = W_2$ if and only if $\Ann{W_1} = \Ann{W_2}$.
(a) Prove that the annihilator of $S$ in $V$ is the same as the annihilator of the subspace of $V^*$ spanned by $S$.
(a) Assume $V$ is finite dimensional with basis $v_1, \ldots, v_n$. Prove that if $S = \{v_1^*, \ldots, v_k^*\}$ for some $k \le n$, then $\Ann{S}$ is the subspace spanned by $\{v_{k+1}, \ldots, v_n\}$.
(a) Assume $V$ is finite dimensional. Prove that if $W^*$ is any subspace of $V^*$ then $\dim \Ann{W^*} = \dim V = \dim W^*$.

### [@DF04, number 11.3.4]

If $V$ is infinite dimensional with basis $\sA$, prove that $\sA^* = \{v^* : v \in \sA\}$ does *not* space $V^*$.

## References

