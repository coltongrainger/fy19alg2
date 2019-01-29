---
title: Modules and Homomorphisms
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-01-24
revised: 2019-01-28
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

## Assignment due 2019-01-28

### [@DF04, number 10.2.1]

\providecommand{\im}{\operatorname{im}}

\gvn The definition of a submodule.

\wts Kernels and images of $R$-module homomorphisms are submodules.

\pf Let $f \colon M \to N$ be a homomorphism of modules. From our study of groups, $\ker f$ and $\im f$ are subgroups of $M$ and $N$ respectively [@DF04, ch. 2.2]. To argue both groups are stable under the ring action, consider $m \in M$ and $n \in N$. 

inclusion | justification
--- | ---
$rm \in \ker f$ | $f(rm) = rf(m) = r0 = 0$.
$rn \in \im f$ | Choose $a \in f^{-1}(n)$, then $rn = rf(a) = f(ra)$. \qedsymbol

### [@DF04, number 10.2.2]

\providecommand{\id}{\operatorname{id}}

\wts $R$-module isomorphism classes partition any set of $R$-modules.

\pf Let $M, M', M''$ be $R$-modules.

property | justification
--- | ---
Reflexivity | Because $\id \colon M \to M$ respects addition and intertwines the ring action, $\id$ is a module isomorphism. 
Symmetry | Say $\phi \colon M \to M'$ is a module isomorphism. By definition^[A module isomorphism is a bijective module homomorphism.] $\phi^{-1}$ is a bijective set map. Moreover, take any elements $\phi(m), \phi(n) \in M'$ and $r \in R$. Additivity follows from $\phi^{-1}(\phi(m)) + \phi^{-1}(\phi(n)) = \phi^{-1}(\phi(m +n)) = \phi^{-1}(\phi(m) + \phi(n))$. Closure under the ring action is seen by $r\phi^{-1}(\phi(m)) = rm =  \phi^{-1}(\phi(rm))$.
Transitivity | Let $M \xrightarrow{f} M' \xrightarrow{g} M''$ be module isomorphisms. Then $M \xrightarrow{g \circ f} M''$ is an group isomorphism. Let $r \in R$ and $m \in M$. Consider $r(g\circ f)(m) = rg(f(m)) = g(rf(m)) = g(f(rm)) = (g\circ f)(rm)$. So $g \circ f$ is a module isomorphism. \qedsymbol

### [@DF04, number 10.2.4]

\providecommand{\Hom}{\mathrm{Hom}}

\gvn Let $A \in \mathsf{Ab}$, let $a \in A$, and say $n \in \NN$. 

\wts 

a. $\phi_a \colon \ZZ/(n) \to A$ given by $\phi(k+ (n)) = ka$ is a well defined $\ZZ$-module homomorphism iff $na = 0$.
b. $\Hom_\ZZ(\ZZ/(n), A) \cong A_n$ where $A_n := \{a \in A: na = 0\}$.

\pf 

a. The following are equivalent.

    - The module homomorphism $\phi_a\colon \ZZ/(n) \to A$ such that $\phi(k + (n)) = ka$ is well defined.
    - For each $j$ such that $j - k \in (n)$, $ja = ka$.
    - For the generators $\pm n$ of the ideal $(n)$, $\pm na = 0$.
    - For the integer $n$ and the element $a \in A$, $na = 0$.

b. Let $\psi \colon \Hom_\ZZ(\ZZ/(n), A) \to A_n$ map $\phi \in \Hom(\ZZ/(n), A)$ to $a$ iff $\phi(1 +(n)) = a$. From the argument above, each $\phi \in \Hom(\ZZ/(n), A)$ is determined by $\phi(1 + (n)) = 1a = a$, so $\psi$ is well defined. 

property of $\psi$ | justification
--- | ---
an additive homomorphism? | For arbitrary $\phi_1, \phi_2 \in \Hom(\ZZ/(n), A)$, there's $a_1, a_2 \in A_n$ such that $\phi_1(1+(n)) = a_1$ and $\phi_2(1 + (n)) = a_2$. Then $\psi \colon \phi_1 + \phi_2 \mapsto a_1 + a_2$.
injective? | Consider $\alpha \in \ker \psi$. Then $\alpha(1 + (n)) = 0$. So $\alpha$ is the zero homomorphism, i.e., $\ker \psi =0$. 
surjective? | Note that if $b \in A_n$, then $nb = 0$. Since $\abs{b}$ divides $n$, the homomorphism $\beta(1 + (n)) = b$ is well defined. So $\im \psi = A_n$. 

> We conclude $\psi \colon \Hom(\ZZ/(n), A) \xrightarrow{\sim} A_n$. \qedsymbol

### [@DF04, number 10.2.5]

*To exhibit.* All $\ZZ$-module homomorphisms from $\ZZ/30\ZZ$ to $\ZZ/12\ZZ$.

*Exhibition.* Take $1 + (30)$ as a generator of $\ZZ/(30)$. All the unique homomorphisms from $\ZZ/(30)$ to $\ZZ/(12)$ are determined by the image of $1+(30)$ in $\ZZ/(12)$, whose order must divide $30$. In particular, there are $6$ possible images.

element | order | determines $\ZZ/(30) \to \ZZ(12)$?
--- | --- | ---
$0  + (12)$ | $1$  | yes
$1  + (12)$ | $12$ | 
$2  + (12)$ | $6$  | yes
$3  + (12)$ | $4$  | 
$4  + (12)$ | $3$  | yes
$5  + (12)$ | $12$  | 
$6  + (12)$ | $2$   | yes
$7  + (12)$ | $12$ | 
$8  + (12)$ | $3$  | yes
$9  + (12)$ | $4$ | 
$10 + (12)$ | $6$ | yes
$11 + (12)$ | $12$ |

So $\Hom$ has cardinality $6$. Moreover, $\Hom$ is isomorphic to a quotient of $\ZZ/(12)$. (Verify.) Thence we conclude $\Hom_\ZZ(\ZZ/(30), \ZZ/(12)) \cong \ZZ/(6)$. \qedsymbol

### [@DF04, number 10.2.6]

\wts $\Hom_\ZZ(\ZZ/(n), \ZZ/(m)) \cong \ZZ/(n,m)\ZZ$.

\pf Fix the base ring $\ZZ$. By [@DF04 10.2.4], the module $\Hom_\ZZ(\ZZ/(n), \ZZ/(m))$ is isomorphic to $\{a + (m) : n(a+(m)) = na + (m) = 0 + (m)\}$ by the 1-1 correspondence $a+ (m) \leftrightarrow \phi$ if and only if $\phi(1 + (m)) = a + (m)$. 

We'll establish a set bijection between $\Hom$ and $\{0,\ldots, d-1\}$ where $d = \gcd(m,n)$. Knowing the cardinality of $\Hom$, and that $\Hom$ is isomorphic to a quotient of $\ZZ/(m)$, we will argue that $\Hom \cong \ZZ/(m,n)$. 

So let $\phi \in \Hom$ such that $\phi(1 + (m)) = a + (m)$. Then $na + (m) = 0+(m)$. So^[My choice of notation due to <https://math.stackexchange.com/questions/381891>.] $na = km$. Let $d = \gcd(m,n)$. Factorize $n$ and $m$ so that $n = \nu d$ and $m = \mu d$. Now the condition on $a$ is $\nu da = k \mu d$. Thence $a = \frac{k\mu}{\nu}$, which we assume is an integer in $\{0, \ldots, m-1\}$. Since $\mu$ and $\nu$ are coprime, $k$ must be $\{0,\nu, \ldots, d(\nu-1)\}$, which establishes the set bijections:
\begin{align*}
\{0,\ldots, d(\nu - 1)\} & \leftrightarrow \{a + (m) : n(a+(m)) = 0 + (m)\}\\
    & \leftrightarrow \Hom_\ZZ(\ZZ/(n), \ZZ/(m)).\end{align*}

Because $\Hom$ is isomorphic to a quotient of the cyclic group $\ZZ/(m)$, and because  $\abs{\Hom} = d= \gcd(m,n)$, we conclude that $\Hom \cong \ZZ/(m,n)$. \qedsymbol

### [@DF04, number 10.2.7]

\gvn Let $z$ be a fixed element in the center of $R$. 

\providecommand{\End}{\mathrm{End}}

\wts 

a. The map $\phi \colon m \mapsto zm$ is an $R$-module endomorphism of $M$. 
b. For a commutative ring $R$ the map from $R$ to $\End_R(M)$ given by $\psi \colon r \mapsto rI$ is a ring homomorphism (where $I$ is the identity endomorphism.)

\pf

a. Let $m,n \in M$, and $r \in R$. For additivity, observe $\phi(m +n) = z(m + n) = zm + zn = \phi(m) + \phi(n)$. For closure under the ring action, consider $r\phi(m) = rzm = zrm = \phi(rm)$.

b. Let $r,s \in R$. Consider $\psi(r + s) = (r + s)I = rI + sI = \psi(r) + \psi(s)$, with also $\psi(rs) = (rs)I = r(sI) = rI(sI) = \psi(r)\psi(s)$. \qedsymbol


### [@DF04, number 10.2.9]

\gvn Let $R$ be a commutative ring. 

\wts $\Hom_R(R, M)$ and $M$ are isomorphic as left $R$-modules.

\pf Let $\phi \in \Hom$ be mapped by $\psi\colon \phi \mapsto \phi(1)$ into $M$. 

property of $\psi$ | justification
--- | ---
an $R$-module homomorphism? | Say $\alpha, \beta \in \Hom$ and $r \in R$. Then $\psi(\alpha + \beta) = ( \alpha + \beta  )(1) = \alpha(1) + \beta(1) = \psi(\alpha) + \psi(\beta)$. 
injective? | Suppose $\alpha \in \ker \psi$. Then $\alpha$ is mapped to $0 \in M$. So $\alpha(1) = 0$ which implies that for each $r \in R$, $\alpha(r) = \alpha(r1) = r\alpha(1) = r0 = 0$. So $\alpha$ is the zero homomorphism. 
surjective? | Pick an arbitrary $m \in M$. Is there $\beta \in \Hom$ such that $\beta(1) = m$? Yes. $R$-linearly extending the provisional definition $\beta(1) = m$, we'd have $\beta(r) = rm$, which does define a module homomorphism $\beta$. \qedsymbol

### [@DF04, number 10.2.10]

\gvn Let $R$ be a commutative unital ring.

\wts $\Hom_R(R, R) =: \End_R(R)$ and $R$ are isomorphic as rings.

\pf Consider the map $\psi \colon R \to \End(R)$ such that $r \mapsto rI$. 

property of $\psi$ | justification
--- | ---
a ring homomorphism? | Special case of [@DF04 number 10.2.7] when considering $R$ as a module over itself.
injective? | Consider $\ker \psi$. Say $r \in R$ and for each $\phi \in \End(R)$, $rI\phi = r\phi = 0$. Then for each $s \in R$, $0 = r\phi(s) = \phi(rs)$. In particular for $\phi = \id \in \End(R)$ and $s = 1 \in R$, we have $0 = \id(r)$. So $r =0$.
surjective? | Say $\phi \in \End(R)$. There's some $r \in R$ such that $\phi(1) = r$. By [@DF04, 10.2.9], that $\phi(1) = r$ determines $\phi$ by extending $R$-linearly. (E.g., for $s \in R$, $\phi(s) = s\phi(1) = sr$.) \qedsymbol

### [@DF04, number 10.2.11]

\gvn Let $A_1, A_2, \ldots, A_n$ be $R$-modules and let the $B_j$ be submodules of the $A_j$, resp.

\wts $(A_1 \times \cdots \times A_n)/(B_1 \times \cdots \times B_n) \cong (A_1/B_1) \times \cdots \times (A_n/B_n)$.

*Proof by universal property.* Suppose that a passerby $R$-module $C$ has homomorphisms $\phi_j$ into the $A_j/ B_j$.

\begin{displaymath}
    \xymatrix{
C \ar@/_/[ddr]_{\phi_1} \ar@/^/[drr]^{\phi_2}
  \ar@{<.}[dr]|-{\psi} \\
  & \prod A_j \big/ \prod B_j \ar[d]^-{\pi_1} \ar[r]_-{\pi_2} & A_2/B_2  \\
  & A_1/B_1 
  }\end{displaymath}

Define
\begin{align*}
\pi_i \colon \left(\prod_j A_j\right)/\left(\prod_j B_j\right) &\to A_i / B_i\\
(a_1, \ldots, a_n) + \prod_j B_j &\mapsto a_i + B_i.
\end{align*}

Observe that the $\pi_i$ are well defined and surjective as $a_i \notin B_j$ for $i \neq j$. To see that $\left(\prod_j A_j\right)/\left(\prod_j B_j\right)$ is the product of the quotients $A_j / B_j$, suppose now that $C = \prod_1^n (A_j/B_j)$ *is the product indeed* (explaining the otherwise ridiculous reversed arrow for $\psi$) with homomorphisms $\phi_j$ as the standard coordinate projections. By the universal property of products, there's a unique homomorphism $\psi \colon \prod A / \prod B \to C$ such that $\phi_j \circ \psi = \pi_j$ for all $j$. Factorization through the $\phi_j$ forces $\ker \psi = \cap_j \ker \pi_j = (0_{A_1}, \ldots, 0_{A_n}) + \prod_j B_j$, which is trivial. So $\psi \colon \prod A / \prod B \xrightarrow{\sim} C$. \qedsymbol

## References
