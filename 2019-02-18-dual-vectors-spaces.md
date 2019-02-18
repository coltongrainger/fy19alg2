---
title: Dual Vector Spaces
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-02-17
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

## Assignment due 2019-02-18

### [@DF04, number 11.3.2] part (a)

\newcommand{\hommod}{\Hom_\QQ(V, \QQ)}

\given Let $V$ be the collection of polynomials with coefficients in $\QQ$ in the variable $x$ of degree at most $5$ with $\sB = \{ 1, x, x^2, \ldots, x^5\}$ as a basis. Consider the dual space $V* = \hommod$. Let the dual basis $\sB^*$ for be defined on elements of $\sB$ (letting the indices run over $0 \le  i, j \le 5$) by $$f_j(x^i) = \delta_{ij}.$$

\wts The map $E \colon V \to \QQ$ defined $E(p) = p(3)$ is a linear functional in $\hommod$ expressed in terms of the dual basis $\sB^* = \{f_j\}_{j=0}^5$ as $\sum_{j=0}^5 3^j f_j$.

\renewcommand{\ev}{\operatorname{ev}}

\pf Let $a \in \QQ$. Observe that the function $\ev_a\vert_V \colon  V \to \QQ$ defined by $\ev_a \vert_V (p) = p(a)$ is a restriction of the ring homomorphism $\ev_a \colon \QQ[x] \to \QQ$. In particular, taking $\lambda \in \QQ$ as the constant polynomial and $p, q \in V$, we see 
\begin{align*}
\ev_a(\lambda p) &= \lambda \ev_a(p)\\
\ev_a(p + q) &= \ev_a(p) + \ev_a(q).
\label{eq:2alinearity}
\end{align*}
It follows that the restriction $\ev_a\vert_V$ is a $\QQ$-linear functional in $\hommod$. Specifically, the evaluation at $3 \in \QQ$, 
$$E \colon V \to \QQ \qq{defined} E(p(x)) = p(3)$$
is a $\QQ$-linear functional in $\hommod$. That is, $E$ is a linear functional in the dual space $V^*$.

Now to express $E$ as a linear combination of linear functionals in $\sB^*$. Note for each $p \in V$ that $f_j(p)$ is the rational coefficient of $x^j$. Let $\QQ$ be given the standard basis $\sE = \{1\}$. For an arbitrary $a \in \QQ$, the matrix representation of $\ev_a \vert_V \in \hommod$ with respect to $\sB$ and $\sE$ is
\begin{equation}
M_\sB^\sE (\ev_a\vert_V) = \mqty[a^0 & a^1 & a^2 & a^3 & a^4 & a^5].
\label{eq:2aevalmatrix}
\end{equation}
The matrix representation of $E$ follows from \eqref{eq:2aevalmatrix} as $$M_\sB^\sE (E) = \mqty[3^0 & 3^1 & 3^2 & 3^3 & 3^4 & 3^5].$$ 
To write $E$ in terms of the dual basis:
\begin{align*}
E &= \mqty[3^0 & 3^1 & 3^2 & 3^3 & 3^4 & 3^5] \mqty[f_0 \\ \vdots \\ f_5] & \text{(a linear combination of functionals $f_j$ from the dual basis $\sB^*$)}
\end{align*}
We verify that $E$ and the linear combination $M_\sB^\sE\mqty[f_j]$ agree on basis elements of $\sB$ for $j = 0, \ldots, 5$:
\begin{align*}
\mqty[3^0 & 3^1 & 3^2 & 3^3 & 3^4 & 3^5] \mqty[f_0 \\ \vdots \\ f_5](x_j)  &= \mqty[3^0 & 3^1 & 3^2 & 3^3 & 3^4 & 3^5] \mqty[\delta_{0j} \\\vdots \\ \delta_{5j}]\\
 &= 3^j.
\end{align*}
We have demonstrated that $E$ and $M_\sB^\sE\mqty[f_j]$ agree on all $x^j$ in the basis $\sB$ for $V$. Extending linearly, $E \equiv M_\sB^\sE\mqty[f_j]$. \qedsymbol


### [@DF04, number 11.3.2] part (b)

\given The same setup as [@DF04, number 11.3.2] part (a), but considering  the function $\phi \colon V \to \QQ$ defined by $\phi(p) = \int_0^1 p(t)\, dt$ instead of $E$.

\wts The map $\phi \colon V \to \QQ$ is a linear functional in $\hommod$ expressed in terms of the dual basis $\sB^* = \{f_j\}_{j=0}^5$ as $\sum_{j=0}^5 \frac{f_j}{j+1}.$

\pf We first argue the following is true:

> Let $[a,b]$ be a closed interval in $\RR$ with rational endpoints, and let $\QQ[x]$ be considered as a rational vector space of polynomials. For each $g \in \QQ[x]$, the function $\phi_g \colon \QQ[x] \to \QQ$ defined by $\phi_g(f) = \int_a^b g(t)f(t)\, dt$ is a linear functional in $\Hom_\QQ(\QQ[x], \QQ)$. 

Why? Say $\phi_g$ is defined as integrating $f \in \QQ[x]$ against $g$. Let $f_1, f_1 \in \QQ[x]$ and $\lambda \in \QQ$. Because $\QQ[x]$ is also a ring under polynomial multiplication, both $\lambda f_i$ and $gf_i$ (for $i = 1,2$) are rational polynomials. The primitive $F$ of a rational polynomial $f$ is again a rational polynomial. It follows definite integral of a ration polynomial $f$ is just the difference $F(b) - F(a)$ of the evaluations of $F$ at $b$ and $a$ (in that order). So much to say that $\phi_g \colon \QQ[x] \to \QQ$ is well defined. Now for $\QQ$-linearity. Observe
\begin{align*}
\phi_g(f_1 + f_2) &= \int_a^b (f_1 + f_2)(t) g(t) \, dt\\
  &= \int_a^b f_1(t) g(t) \, dt + \int_a^b f_2(t) g(t) \, dt\\
  &= \phi_g(f_1) + \phi_g(f_2),  \text{ and }\\
\phi_g(\lambda f_1) &= \int_a^b (\lambda f_1)(t) g(t)\, dt\\
  & = \lambda \int_a^b f_1(t) g(t)\, dt\\
  & = \lambda \phi_g(f_1).
\end{align*}
We have shown $\phi_g$ is a linear functional in $\Hom_\QQ(\QQ[x], \QQ)$.

Onto our specific case. Let $a = 0$ and $b =1$. Notice that $\phi$ as given is the restriction of $\phi_{\mathbf{1}} \in \Hom_\QQ(\QQ[x], \QQ)$ (defined $\phi_\mathbf{1}(f) = \int_0^1 f(t) \, dt$) to the subspace $V$ of $\QQ[x]$. Because the restriction of a morphism to a subobject is a morphism out of the subobject, $\phi$ is a linear functional in $\hommod$.

Lastly, for each $x^i$ in the basis $\sB$ of $V$, we have 
$$\phi(x^i) = \frac{t^{i+1}}{i+1}\Bigg\vert_{t=0}^{t=1} = \frac 1 {i+1}.$$ The matrix representation (using $\sE= \{1\}$ for $\QQ$) is 
\begin{equation*}
M_\sB^\sE (\phi) = \mqty[1 &  \frac 12 & \frac 13 & \frac 14 & \frac 15 & \frac 16 ].
\label{eq:2bmatrix}
\end{equation*}
The expression of $\phi$ is terms of the dual basis $\sB^*$ is 
\begin{align*}
\mqty[1 &  \frac 12 & \frac 13 & \frac 14 & \frac 15 & \frac 16 ]
\mqty[f_0 \\ \vdots \\ f_5] = \sum_{j=0}^5 \frac{f_j}{j+1}.
\end{align*}
\qedsymbol

### [@DF04, number 11.3.2] part (c)

\given The same setup as [@DF04, number 11.3.2] part (b), but considering a new definition of $\phi \colon V \to \QQ$ such that 
\begin{equation}
\phi(p) = \int_0^1 t^2p(t)\, dt.
\label{eq:2cfun}
\end{equation}

\wts The map $\phi \colon V \to \QQ$ is a linear functional in $\hommod$ expressed in terms of the dual basis $\sB^* = \{f_j\}_{j=0}^5$ as $\sum_{j=0}^5 \frac{f_j}{j+3}.$

\pf In part (b) we demonstrated that for each $g \in \QQ[x]$, the function $\phi_g \colon \QQ[x] \to \QQ$ defined by $\phi_g(f) = \int_a^b g(t)f(t)\, dt$ is a linear functional in $\Hom_\QQ(\QQ[x], \QQ)$. 
Let $g(t) = t^2$. We see that $\phi$ in \eqref{eq:2cfun} is the restriction of $\phi_g$ to the subspace $V$. Hence the restriction $\phi_g \vert_V = \phi$ is a linear functional in $\hommod$.

For each $x^i$ in the basis $\sB$ of $V$, we have
$$\phi(x^i) = \frac{t^{i+3}}{i+3}\Bigg\vert_{t=0}^{t=1} = \frac 1 {i+3}.$$ The matrix representation with respect to $\sB$ and $\sE$ is 
\begin{equation*}
M_\sB^\sE (\phi) = \mqty[\frac 13 & \frac 14 & \frac 15 & \frac 16 & \frac 17 & \frac 18 ].
\label{eq:2cmatrix}
\end{equation*}
So the expression of $\phi$ is terms of the dual basis $\sB^*$ is 
\begin{align*}
\mqty[\frac 13 & \frac 14 & \frac 15 & \frac 16 & \frac 17 & \frac 18 ]
\mqty[f_0 \\ \vdots \\ f_5] = \sum_{j=0}^5 \frac{f_j}{j+3}.
\end{align*}
\qedsymbol

### [@DF04, number 11.3.2] part (d)

\given The same setup as [@DF04, number 11.3.2] part (c), but considering $\phi \colon V \to \QQ$ such that 
\begin{equation*}
\phi(p) = p'(5). \qq{(polynomial derivation)}
\label{eq:2dfun}
\end{equation*}

\wts The map $\phi \colon V \to \QQ$ is a linear functional in $\hommod$ expressed in terms of the dual basis $\sB^* = \{f_j\}_{j=0}^5$ as $\sum_{j=0}^5 j 5^{j-1} f_j$.

\pf In part (a) we demonstrated that for any $a \in \QQ$ and $\QQ$-subspace $W$ of $\QQ[x]$, the map $\ev_a\vert_W$ was a linear functional in $\Hom_\QQ(W, \QQ)$. Now let $W$ be the subspace of $\QQ[x]$ of polynomials with degree at most $4$. Let $D \colon V \to W$ be defined $D(p(x)) = p'(x)$ for all $p \in V$. Observe that $D$ is linear. For $\lambda \in \QQ$, $p,q \in V$, 
\begin{align*}
\lambda D(p(x)) &= \lambda p'(x) = D(\lambda p(x)), \qq{(scalar multiplication)}\\
D(p(x) + q(x)) &= (p + q)'(x) = p'(x) + q'(x) = D(p(x)) + D(q(x)), \qq{(addition).}
\end{align*}
So $D$ is in $\Hom_\QQ(V, W)$. 

By the argument in part (a), $\ev_5\vert_W$ is a linear functional in $\Hom_\QQ(W, \QQ)$. Whence the composition $\ev_5\vert_W \circ D$ is in $\Hom_\QQ(V, \QQ)$. But in fact $\ev_5\vert_W \circ D \equiv \phi$. We conclude that $\phi$ is a linear functional in $\hommod$.

For each $x^i$ in the basis $\sB$ of $V$, we have
$$\phi(x^i) = i5^{i-1}.$$ 
The matrix representation with respect to $\sB$ and $\sE$ is 
\begin{equation*}
M_\sB^\sE (\phi) = \mqty[0 & 1 & 10 & 75 & 500 & 3125]
\label{eq:2dmatrix}
\end{equation*}
So the expression of $\phi$ is terms of the dual basis $\sB^*$ is 
\begin{align*}
\mqty[0 & 1 & 10 & 75 & 500 & 3125]
\mqty[f_0 \\ \vdots \\ f_5] = \sum_{j=0}^5 j 5^{j-1} f_j.
\end{align*}
\qedsymbol

### [@DF04, number 11.3.3] part (a)

\providecommand{\Ann}[1]{\operatorname{Ann}\left( #1 \right)}

\given For any subset $S$ of $V^*$ for some finite dimensional space $V$, we define the *annihilator of $S$ in $V$* as $$\Ann{S} := \{v \in V: f(v) = 0 \text{ for all } f \in S\}.$$ Let $V$ be such a finite dimensional vector space and $S$ such a subset.

\wts $\Ann{S}$ is a *subspace* of $V$.

\pf Notice $0 \in \Ann{S}$, because ranging through all $f \in V^*$, it's always the case that $f(0) = 0$. Now suppose $u, v \in \Ann{S}$ and $\lambda \in F$. Then, for all $f \in S$, 
\begin{align*}
f( u + v ) &= f(u ) + f(v) = 0 + 0 = 0\\
\lambda f(u) &= \lambda 0 = 0.
\end{align*}
So $\Ann{S}$ is a subspace of $V$. \qedsymbol

### [@DF04, number 11.3.3] part (c)

\given Let $V$ be a finite dimensional vector space. Let $W_1, W_2 \subset V^*$ be subspaces of the dual space.

\wts $W_1 = W_2$ if and only if $\Ann{ W_1 } = \Ann{ W_2 }$.

\pf ($\Rightarrow$) Suppose $W_1 = W_2$. Then 
\begin{align*}
\Ann{W_1} & = \{v \in V : f(v) = 0 \qq{for all} f \in W_1\}\\
& = \{v \in V : f(v) = 0 \qq{for all} f \in W_2\}\\
&= \Ann{ W_2 }.\end{align*}

($\Leftarrow$) Suppose $\Ann{W_1} = \Ann{W_2}$. From the forwards argument, it's apparent
\begin{equation}
\Ann{\Ann{W_1}} = \Ann{\Ann{W_2}}.
\label{eq:3cdoubleann}
\end{equation}

We desire that $W_1 = W_2$, so we will argue:

> For each subspace $U \subset V^*$, the annihilator of the annihilator $\Ann{\Ann{U}}$ is naturally isomorphic (via the natural embedding of $W$ into $V^*$, where $W^* = V$) to $U$ itself.

Supposing the statement above has been proven, \eqref{eq:3cdoubleann} implies that $W_1$ and $W_2$ in $V^* = W^{**}$ are natural images of the same subspace $\Ann{\Ann{W_1}} = \Ann{\Ann{W_2}}$ in $W$. Naturality then implies $W_1 =W_2$.

Onto the argument. Say $V^*$ be a finite dimensional vector space with $U \subset V^*$ a subspace of the dual. We might as well find a vector space $W$ such that $W^* = V$ (certainly $V^*$ is a candidate, but for notation's sake we'll write $W$). Here's a schematic (which is *not to imply* there are morphisms along the arrows):

\begin{equation}
\xymatrix{
& V^* \ar@{<-} [rr] 
& & V & & 
\\
W^{**} \ar@{-}[ur]^\id \ar@{<-}[rr]
& & W^* \ar@{-}[ur]^\id \ar@{<-}[rr] & & W 
\\
& U \ar@{->}[rr]
& & \Ann{U} & & 
\\
U \ar@{->}[rr] \ar@{-}[ur]^\id
& & \Ann{U} \ar@{-}[ur]^\id \ar@{->}[rr] & & \Ann{\Ann{U}}\\
}\end{equation}

Choose $\tilde{U} \subset W$ as the preimage of $U$ under the natural injection $W \to W^{**}$ given by $u \mapsto (\ev_u \colon W^* \to W)$. Because $V$ is finite dimensional, $V^* = W^{**}$ is too. Whence $\tilde{U}$ naturally surjects onto $U$, which implies each linear functional in $U$ is of the form $\ev_u \colon W^* \to F$ for a unique $u \in \tilde{U}$. 

We can compute $\Ann{U}$ either thinking of $U  \subset W^{**}$ or as $U \subset V^*$. That is, 
\begin{align*}
\Ann{U} &=\{v \in V : f(v) = 0 \qq{ for all } f \in U \subset V^*\}\\
    &=\{f \in W^* : \ev_u(f) = 0 \qq{ for all } \ev_u \in U \subset W^{**}\}.\\
\end{align*}

Proceeding in the $U \subset W^{**}$ style of thought,
\begin{align*}
\Ann{\Ann{U}} &=\Ann{\{f \in W^* : \ev_u(f) = 0 \qq{ for all } \ev_u \in U \subset W^{**}\}}\\
   &= \{w \in W : f(w) = 0 \qq{for all} f \in W^* \qq{s.th.} \ev_u(f) = 0 \qq{for all} \ev_u \in U \subset W^{**}\}\\
   &= \{w \in W : f(w) = 0 \qq{for all} f \in W^* \qq{s.th.}      f(u) = 0 \qq{for all} u \in \tilde{U} \subset W\}\\
   & = \tilde{U}.
\end{align*}

Because $\Ann{\Ann{U}} = \tilde{U}$ of each subspace $U \subset V^*$ is naturally isomorphic to $U$ by way of including $W$ into $W^{**}$, we conclude:

> Given subspaces $W_1$ and $W_2$ in $V^*$ with identical annihilators $\Ann{W_1} = \Ann{W_2}$, it follows that $\Ann{\Ann{W_1}} = \Ann{\Ann{W_2}}$, so the natural preimages $W_1$ and $W_2$ are in fact the same. \qedsymbol

### [@DF04, number 11.3.3] part (d)

\gvn Let $S \subset V^*$ for $V^*$ a finite dimensional vector space.

\renewcommand{\span}[1]{\operatorname{span}\left( #1 \right)}

\wts $\Ann{\span S} = \Ann S$. 

\pf We show both inclusions. Let $v \in \Ann{\span S}$. Then for all $f \in \span S$, $f(v) = 0$. So clearly for all $f \in S$, $f(v) = 0$. Thus $v \in \Ann{\span{S}}$. 

On the other hand, let $v \in \Ann S$. For all $f \in S$, $f(v) = 0$. Because $S$ is a generating set for $\span S$, there's a surjection \begin{equation}\label{eq:3dsurject}\bigoplus_{f \in S} F \to \span S \qq{such that} \sum_{f \in S} \lambda_f \mapsto \sum_{f \in S} \lambda_f f.\end{equation}
Take an arbitrary functional in the image (e.g., the left hand side) of \eqref{eq:3dsurject}. Evaluating at $v$, it follows that $\sum_{f \in S} \lambda_f f(v) = 0$. So $v$ annihilates all functionals in $\span S$. Thence $v \in \Ann { \span S}$. \qedsymbol

### [@DF04, number 11.3.3] part (e)

\given Assume $V$ is finite dimensional with basis $v_1, \ldots, v_n$. 

\wts If $S = \{v_1^*, \ldots, v_k^*\}$ for some $k \le n$, then $\Ann{S}$ is the subspace spanned by $\{v_{k+1}, \ldots, v_n\}$.

\pf We show both inclusions for $\Ann{S} = \span{v_{k+1}, \ldots, v_n}$. Let $$u = \lambda_{k+1}v_{k+1} + \cdots + \lambda_n v_n$$ be in $\span{v_{k+1}, \ldots, v_n}$. Consider the image of $u$ under each dual basis functional $v^*_1, \ldots, v_k^*$. Because the indices $1, \ldots, k$ in the dual basis are disjoint from $k+1, \ldots, n$ of the (possibly) nonzero components of $u$, it's visible that $u$ is a vector in $\Ann S$. 

For the other inclusion, say $v \in \Ann S$. Then $$v = \lambda_1v_1 + \ldots + \lambda_k v_k + \lambda_{k+1}v_{k+1} + \cdots + \lambda_n v_n.$$ Evaluating each dual basis functional $v_1^*, \ldots, v_k^*$ at $v$, the condition $v^*_i(v) = 0$ implies $\lambda_i = 0$ for $i = 1, \ldots, k$. Whence $v \in \span{v_{k+1}, \ldots, v_n}$. \qedsymbol

### [@DF04, number 11.3.3] part (f)

\given Assume $V$ is a finite dimensional vector space. 

\wts If $W^*$ is any subspace of $V^*$, then $\dim \Ann{W^*} = \dim V = \dim W^*$.

\pf In part (e), we argued when $k \le \dim V$, if $S = \{v_1^*, \ldots, v_k^*\}$ is a subset of the dual basis, then $\Ann{S}$ is spanned by $\dim V - k$ linearly independent vectors. In part (d), we proved that $\Ann{S} = \Ann{\span{S}}$. Given $W^* \subset V^*$, both parts (d) and (e) imply: for a basis $\sB$ of $W^*$, $\dim{\Ann{S}} = \dim V - \abs{\sB}$, whence $\dim \Ann{W^*} = \dim V - \dim W^*$. \qedsymbol

### [@DF04, number 11.3.4]

\given Let $V$ be an infinite dimensional with basis $\sA$.

\wts $\sA^* = \{v^* : v \in \sA\}$ does *not* span $V^*$.

\pf Suppose for contradiction that $\span{\sA} = V^*$. Then for each $f \in V^*$, we would have a unique linear combination $$f = \sum_{a \in \sA} a^* f(a) \qq{such that all but finitely many of the $f(a) = 0$.}$$
Let $u \in F$ be a nonzero element of the base field. Then let $f \in \Hom_F(V, F)$ be defined on generators $a \in \sA$ by $f(a) = u$. Extending linearly, $f$ is a well defined homomorphism from $V$ to $F$. Yet $f$ cannot be expressed as a *finitary* linear combination $\sum_{a \in \sA} a^* f(a)$, which is absurd. We conclude that $\sA^*$ does *not* span $V^*$. \qedsymbol

## References

