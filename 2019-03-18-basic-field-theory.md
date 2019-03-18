---
title: Basic Field Theory
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-03-17
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

### [@DF04, number 13.2.16]

\given Let $K/F$ be an algebraic extension. Let $R$ be a ring such that $K \supset R \supset F$.

\wts $R$ is a subfield of $K$ containing $F$.

\pf We argue first that $R$ is an integral domain, then then $R$ is a field. 

The inclusion $F \hookrightarrow R$ is a nontrivial ring homomorphism, that demonstrates in particular $1 \in F \subset R$. So $R$ is a unital ring. Commutativity and the absence of zero divisors follow from the assumption $R \subset K$. 

- To verify commutativity: Let $a,b  \in R \subset K$. Then $ab = ba$ in $K$. Therefore $ab = ba$ in $R$. 
- To verify that $R$ has no zero divisors: Suppose $a, b \in R$ such that $ab = 0$. Then $a,b \in K$, which is a field, and so $a =0$ or $b=0$. 

We have shown $R$ is a commutative unital ring without zero divisors. By definition, $R$ is an integral domain.

We now show that $R$ is a field. It suffices to prove each nonzero element $\alpha \in R$ is invertible in $R$. So take $\alpha \in R$. Because $K$ is algebraic over $F$, there is a minimal degree nonzero monic polynomial
$$p_\alpha(x) = x^n + \lambda_{n-1} x^{n-1} + \cdots + \lambda_1 x + \lambda_0 \qq{with coefficients $\lambda_k$ in $F$}$$
for which $p_\alpha(\alpha) = 0$. Note $\lambda_0 \neq 0$ by minimality of $p_\alpha$. Whence
$$\lambda_0 = - \alpha^n - \lambda_{n-1}\alpha^{n-1} - \cdots \lambda_1 \alpha.$$
Therefore 
\begin{equation}
\label{eq:inverse}
1 = \alpha\left(\frac{- \alpha^{n-1} - \lambda_{n-1}\alpha^{n-2} - \lambda_{n-2}\alpha^{n-2} - \cdots - \lambda_1}{\lambda_0}\right) =: \alpha(\alpha^{-1}).\end{equation}

(We may divide by $\lambda_0$ because $\lambda_0^{-1} \in F \subset R$.) Note the $\lambda_k$ are in $F \subset R$ and the power $\alpha^k$ are in $R$. Therefore $\alpha^{-1}$ as defined in \eqref{eq:inverse} is an element of $R$. Therefore each nonzero element of $R$ is a unit in $R$.

To summarize: $R$ is an integral domain, $K \supset R \supset F$, and all nonzero elements of $R$ are invertible. We conclude that (by definition of subfield) $R$ is a subfield of $K$ containing $F$. \qedsymbol

### [@DF04, number 13.2.19]

\given Let $K/F$ be a degree $n$ field extension. Let $\sM_n(F)$ be the ring of $n\times n$ matrices with entries from $F$.

\wts

(a) For any $\alpha \in K$, the action of $\alpha$ on $K$ by left multiplication is an $F$-linear transformation of $K$.

(b) $K$ is isomorphic to a subfield of the ring $\sM_n(F)$. 

(c) $\sM_n(F)$ contains an isomorphic copy of every extension $E/F$ of degree at most $n$.

\pf (Remark: It's best to make as little reference to the basis for $K$ over $F$ as possible.)

(a) Let $\alpha \in K$ act by left multiplication on $K$, i.e., $\alpha.\delta = \alpha\delta$ for all $\delta \in K$. To verify that the action is an $F$-linear transformation, consider $\beta, \gamma \in K$ and $\lambda \in F$. First note $\alpha$ respects scalar multiplication:
\begin{align*}
\alpha.(\lambda \beta) &= \alpha\lambda\beta & \text{by definition of the action}\\
    &= \lambda\alpha \beta & \text{by commutativity of $K$}\\
    & = \lambda (\alpha.\beta).
\end{align*}
Next observe $\alpha$ respects vector addition:
\begin{align*}
\alpha.(\beta + \gamma) &= \alpha(\beta + \gamma) & \text{by definition of the action}\\
    &= \alpha \beta  + \alpha \gamma & \text{by distributivity in $K$}\\
    & = (\alpha.\beta) + (\gamma.\beta).
\end{align*}
Therefore the action of $\alpha$ on $K$ is an $F$-linear transformation of $K$. 

(b) Because $K$ is a degree $n$ extension of $F$, we may choose a basis $\sE$ for $K$ as an $n$-dimensional vector space over $F$. Define a ring homomorphism $\phi \colon K \to \sM_n(F)$ by $\phi(\alpha) = [\alpha]$, where $[\alpha]$ is the matrix representation of the linear transformation $\alpha \colon K \to K$ with respect to the basis $\sE$ for $K$ [@DF04, number 11.10]. To verify that $\phi$ is a ring homomorphism, take $\alpha, \beta \in K$. Note for any $\delta \in K$, the actions of $\alpha$ and $\beta$
satisfy
\begin{equation}
\label{eq:add}
(\alpha+ \beta).\delta = \alpha\delta + \beta\delta = \alpha.\delta + \beta.\delta,
\end{equation}
and
\begin{equation}
(\alpha\beta).\delta = \alpha\beta\delta = \alpha.(\beta.\delta).
\label{eq:comp}
\end{equation}
By inspection of the definition of matrix addition along with the observations in \eqref{eq:add},
$$\phi(\alpha + \beta) = [\alpha + \beta] = [\alpha] + [\beta] = \phi(\alpha) \phi(\beta).$$
Because the product of matrices representing linear transformations is the matrix representing the composite of these linear transformations, the observations in \eqref{eq:comp} imply that
$$\phi(\alpha\beta) = [\alpha\beta] = [\alpha][\beta] = \phi(\alpha) \phi(\beta).$$
Therefore $\phi \colon K \to \sM_n(F)$ is a homomorphism of rings. 

    We now argue $\phi$ is a monomorphism. It is not too hard to see that the image of $F$ under $\phi$ is the subring of scalar matrices in $\sM_n(F)$, i.e., $\phi(F) = Z(\sM_n(F))$. Whence, knowing $K$ is a field with $\phi \colon K \to \sM_n(F)$ a nontrivial ring homomorphism, it must be that $\phi$ is injective. Therefore $\phi$ algebraically embeds $\phi \colon K \xrightarrow{\cong} \phi(K)$ as a subfield in the ring $\sM_n(F)$. 

(c) Suppose $E$ is an extension of $F$ of degree $m \le n$. After choosing a basis $\sB$ for $E$, we may define an algebraic
embedding $\phi_E \colon E \to \sM_m(F)$ (in the same fashion as we constructed the homomorphism $\phi \colon K \to \sM_n(F)$ in part b). If one identifies $\sM_m(F) \hookrightarrow \sM_n(F)$, for example, by way of the inclusion 
$$\mqty[\dmat{\sM_m(F), I_{n-m}}] \subset \mqty[\sM_n(F)],$$
then $\phi_E(E) \subset \sM_n(F)$ is an isomorphic image of the field $E$. \qedsymbol

<!---
$$\mqty[ e_1 & \cdots & e_n ] \in \sM_{1\times n}(K)$$
for $K$ as a vector space over $F$.
To represent a vector $\beta \in K$, for example, in terms of the above basis:
$$\beta = \mqty[e_1 & \cdots & e_n]\mqty[b_1 \\ \vdots \\ b_n] \qq{where} \mqty[b_1 \\ \vdots \\ b_n] \in \sM_{n\times 1}(F).$$
From part (a) we know for each $\alpha \in K$, there's an $F$-linear transformation of $K$ defined by the left multiplication of $\alpha$. Let $[\alpha] \in \sM_n(F)$ be the matrix representation of the 

Suppose that $\alpha$ has the basis representation
$$\alpha = \mqty[e_1 & \cdots & e_n]\mqty[a_1 \\ \vdots \\ a_n] \qq{where} \mqty[a_1 \\ \vdots \\ a_n] \in \sM_{n\times 1}(F).$$
We apply distributivity and commutativity to write
\begin{equation}\alpha\beta = 
\alpha\mqty[e_1 & \cdots & e_n]\mqty[b_1 \\ \vdots \\ b_n] = 
\mqty[e_1 & \cdots & e_n]\mqty[\alpha b_1 \\ \vdots \\ \alpha b_n] = 
\mqty[e_1 & \cdots & e_n]\mqty[ \mqty[e_1 & \cdots & e_n]\mqty[b_1a_1 \\ \vdots \\ b_1a_n] \\ \vdots \\ \mqty[e_1 & \cdots & e_n]\mqty[a_1b_n \\ \vdots \\ a_nb_n]].\label{eq:mess}\end{equation}
What a mess! Because $\mqty[\alpha b_1 \\ \vdots \\ \alpha b_n]$ is not necessarily an element in $\sM_{n\times 1}(F)$, one needs to know how basis elements $e_ie_j$ multiply in order to write \eqref{eq:mess} as an $F$-linear combination of the original basis vectors.
--->

## References
