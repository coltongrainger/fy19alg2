---
title: Basic Module Isomorphisms
author: Colton Grainger (MATH 6140 Algebra 2)
date: 2019-02-03
bibliography: /home/colton/coltongrainger.bib
nonumbering: true
xy: true
---

## Assignment due 2019-02-03

We assume $R$ is a unital ring.

### [@DF04, number 10.3.1]

\gvn Let $R$ be a unital ring. Consider sets $A$ and $B$ with cardinality $\abs{A} = \abs{B}$.

\wts The free $R$-modules $F(A)$ and $F(B)$ are isomorphic in the category $\text{Rmod}$.

\pf Let $f \colon A \to B$ be a bijection of sets. Now, $F(A)$ is universal in the category of modules $M$ for which each set map $A \xrightarrow{f} M'$ into any module $M'$ induces a short exact sequence (of $R$-linear maps) $$0 \to A \to M \xrightarrow{\Phi} M' \to 0$$ such that the following diagram commutes:
$$
\xymatrix{
A\ar[r] \ar[dr]_f & M \ar[d]^{\Phi}\\
& M'}
$$

Likewise, $F(B)$ is universal for $B$. Since $f^{-1}$ is a well defined set map, the following diagram commutes:
$$
\begin{CD}
A     @>f>>  B    @>f^{-1}>>   A    @>f>>              B\\
@VV\iota_A V      @VV\iota_B V           @VV\iota_A V           @VV\iota_B V\\
F(A) @>{\exists!\Phi}>> F(B) @>{\exists!\Psi}>>  F(A) @>{\exists!\Phi}>> F(B)
\end{CD}
$$

\providecommand{\id}{\operatorname{id}}

Note the inclusion of $A$ into $F(A)$ induces the identity on $F(A)$, e.g.,
$$
\xymatrix{
A\ar[r] \ar[dr]_{\iota_A} & F(A) \ar@{..>}[d]^{\mathrm{id}}\\
& F(A)}
$$
Similarly, the inclusion of $B$ into $F(B)$ induces the identity on $F(B)$. Chasing $f^{-1} \circ f = \id_A$ and $f \circ f^{-1} = \id_B$, uniqueness of the induced maps $F(A) \xrightarrow{\id} F(A)$ and $F(B) \xrightarrow{\id} F(B)$ forces $$\Psi \circ \Phi = \id_{F(A)}\quad \text{ and } \quad \Phi \circ \Psi = \id_{F(B)},$$ which demonstrates that $\Phi$ is a morphism in $\mathrm{Rmod}$ with a left and right inverse. We conclude that $$\Phi \colon F(A) \to F(B)$$ is an isomorphism. \qedsymbol

### [@DF04, number 10.3.3]

\gvn 

a. A linear transformation $T \colon \RR^2 \to \RR^2$ with associated matrix $$A = \begin{bmatrix} 0 & 1 \\ -1 & 0\end{bmatrix}, \quad \text{ w.r.t. the standard basis,}$$ and $V = \RR^2$ as an $\RR[x]$-module where $x$ acts by the linear transformation $x.v = Av$. 

a. A linear transformation $T \colon \RR^2 \to \RR^2$ with associated matrix $$A = \begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}, \quad \text{ w.r.t. the standard basis,}$$ and $W = \RR^2$ as an $\RR[x]$-module where $x$ acts by the linear transformation $x.w = Av$. 

\wts Both the above modules $V$ and $W$ are cyclic.

\pf I claim that $$V = \left\langle\mqty[1 \\ 0]\right\rangle,$$ because $x \in \RR[x]$ acts by $x.\mqty[1\\0] = \mqty[0\\-1]$ to force at least a pair of linearly independent vectors into $\left\langle\mqty[1 \\ 0]\right\rangle$. Since $\RR^2$ as a real vector space has dimension $2$, scalar multiplication takes care of the rest. 

Analogously, I claim $$W = \left\langle\mqty[1\\1]\right\rangle$$ for $x \in \RR[x]$ acts by $x.\mqty[1\\1] = \mqty[0\\1]$ to force two linearly independent vectors into $\left\langle\mqty[1 \\ 1]\right\rangle$. \qedsymbol

### [@DF04, number 10.3.4]

\gvn Let $A$ be a finite abelian group with $\abs{A} = m$.

\wts $A$ is a torsion $\ZZ$-module.

\pf If $a \in A$, the order of the element divides the order of the group, so $ma = 0$. \qedsymbol

*To demonstrate*. The infinite direct sum of cyclic groups $\bigoplus_{k=1}^\infty \ZZ/k\ZZ$ is a torsion $\ZZ$-module.

*Demo.* Let $(a_k)$ be an element of the direct sum $\bigoplus_{k=1}^\infty \ZZ/k\ZZ$. Now, all but finitely many coordinates of $(a_k)$ are zero. So the annihilating integer $$m = \operatorname{lcm}\{k \colon a_k = 0 \text{ in } (a_k)\}$$ is well defined. In each coordinate, the order of the element divides the order of the group, whence $$m(a_k) = (ma_k) = 0.$$ We've shown $\bigoplus_{k=1}^\infty \ZZ/k\ZZ$ is an infinite abelian torsion module. \qedsymbol


### [@DF04, number 10.3.5]

\gvn Let $R$ be an entire ring. Say $M$ is a finitely generated torsion $R$-module. Let $G$ be a finite generating set for $M$.

\wts There's an $r \in R$ such that for all $m \in M$, $rm =0$.

\pf We construct such an annihilating element $r$. Note first $G$ is a finite subset of an $R$-torsion module. So there's a finite collection of nonzero ring elements $$\{r_g \in R\setminus \{0\}: r_gg =0, g \in G\}.$$ Now form the (nonzero, as $R$ is entire) product $$r = \prod_{g \in G} r_g \in R,$$ which I claim will kill each $m \in M$. 

So say $m \in M$. Because $G$ generates $M$, there's a surjection $$\bigoplus_{g \in G} R \to M \quad \text{ such that } \quad s_g \mapsto s_g g.$$ Thence $m = \sum_{k \in G}  s_g g$; this with commutativity sets up the right action by $r$: $$rm = r \left(\sum_g s_g g\right) = \sum_g s_g r g = \sum_g s_g(0) = 0.$$ We conclude there's a nonzero element $r$ in the entire ring $R$ that kills every element of the finitely generated module $M$. \qedsymbol

### [@DF04, number 10.3.6]

\gvn Let $M$ be a finitely generated $R$-module, with finite generating set $G$. Say $\phi \colon M \to N$ is an epimorphism. 

\wts Quotients of $M$ may be finitely generated by a set with $\abs{G}$ (or fewer) elements. 

\pf Because there's a bijective correspondence between quotients of $M$ and isomorphism classes of $R$-linear images of $M$, it suffices to argue that $N \cong M /\ker \phi$ is generated finitely generated by $\phi(G)$. 

By assumption $\phi$ is surjective. If $n \in N$, there's $m \in M$ such that $\phi(m) = n$. Moreover, because $G$ is a generating set for $M$, there's *another* surjection $$\bigoplus_{g \in G} R \to M, \quad \text{ defined by } \quad r_g \mapsto r_g g.$$ We may choose an $R$-linear combination $\sum_{g \in G} r_g g$ that's equal to $m$, then map it through $\phi$ to find $$n = \sum_{g \in G} r_g \phi(g).$$ We have demonstrated that $\phi(G)$ is a generating set for $N$. Because $\phi$ is a well defined function, $\abs{\phi(G)} \le \abs{G}$. We conclude that $N$ may be finitely generated by $\abs{G}$ elements or less. \qedsymbol

### [@DF04, number 10.3.7]

\gvn Let $M$ and $N$ be $R$-modules, with $M/N$ and $N$ finitely generated. Say $G$ and $H$ are finite subsets of $M$ for which $$N = R\{G\} \quad \text{ and } \quad M/N = R\{h + N : h \in H\}.$$

\wts $M$ is finitely generated. 

\pf I claim $M = R\{G \cup H\}$. We proceed to express an arbitrary $m \in M$ as an $R$-linear combinations of $G \cup H$. It's convenient to work with the natural projection $\pi \colon M \to M/N$. By hypothesis, $$\pi(m) = \sum_{h \in H} r_h (h + N).$$ Then, in the fiber, we find
\begin{align*}
m &= \sum_{h \in H}\left( h + \sum_{g \in G} r_g g\right)\\
  &= \sum_h r_h h + \sum_h \sum_g r_h r_g g.
  \end{align*}
We conclude $m \in R\{G \cup H\}$. \qedsymbol

### [@DF04, number 10.3.8]

\gvn The direct sum of countably many copies of the integers, $\bigoplus_1^\infty \ZZ$.

\wts $\bigoplus_1^\infty \ZZ$ is *not* a finitely generated $\ZZ$-module.

*Proof by contradiction*. Suppose $G$ is a finite generating set such that $$\ZZ\{G\} = \bigoplus_1^\infty \ZZ.$$ Find the (well-defined) maximum, taken over finite $G$ and finite nonzero coordinates of each element of $G$, $$k := \max\{i \colon g_i \neq 0, (g_i) \in G\}.$$ Now consider $(h_i) \in \bigoplus_1^\infty \ZZ$ where $h_k = 1$ and $h_i = 0$ for all other indices $i \neq k$. It is visible that $(h_i) \notin \ZZ\{G\}$, which is absurd. Our supposition that $\bigoplus_1^\infty \ZZ$ could be finitely generated must have been false. \qedsymbol

### [@DF04, number 10.3.9]

\gvn An $R$-module $M$ and the definition of *irreducibility* in the category $\mathrm{Rmod}$.

\wts $M$ is irreducible if and only if $M \neq 0$ and $M$ is a cyclic module with any nonzero element as a generator. 

\pf ($\Rightarrow$) Let $M$ be irreducible. Then $M \neq 0$. If $m$ is a nonzero element of $M$, then the nontrivial submodule $R\{m\}$ must be $M$. 

($\Leftarrow$) Let $M \neq 0$ and say any nonzero $m \in M$ does generate $M$. Let $N \subset M$ be a submodule. Either $N$ is trivial or not. If not, then the nonzero element $n \in N$ generates $M$. In particular, $M = R\{n\} \subset N \subset M$. Because a nontrivial submodule $N$ of $M$ must be $M$ itself, we conclude $M$ is irreducible. \qedsymbol

*To exhibit*. We exhaustively list all irreducible $\ZZ$-modules.

*Exhibition.*

kind of $\ZZ$-module | isomorphism class rep | parameter
--- | --- | ---
cyclic | $\ZZ/(k)$ | $k \in \ZZ_{\ge 0}$
nontrivial cyclic  | $\ZZ/(n)$ | $n \in \ZZ_{\ge 0} \setminus\{1\}$
irreducible | $\ZZ/(p)$ | $p$ is a prime integer

### [@DF04, number 10.3.10]

\gvn Let $R$ be a commutative unital ring. Let $M$ be an $R$-module. 

\wts $M$ is irreducible if and only if $M \cong R/\fm$ where $\fm$ is a maximal ideal of $R$.

\pf ($\Rightarrow$) Let $M$ be irreducible. By [@DF04, number 10.3.9], there's a unique surjective $R$-linear map $$\phi \colon R \to M$$ such that $\phi(r) = rm$, where $m$ is any nonzero element. (If $m$ is zero, then $\phi \colon R \to 0$ is trivial.) In particular $R/\ker \phi \cong M$. By the lattice isomorphism theorem for modules, $R/\ker \phi$ has no nontrivial proper submodules. 

Motivated by the fact that $R$ is an object in both $\mathrm{Rmod}$ and $\mathrm{CRing}$, we set out the following thesaurus.

description | in $\mathrm{CRing}$ | in $\mathrm{Rmod}$
--- | --- | ---
"normal" subobjects | ideals | submodules 
"simple" objects | fields | irreducible modules

Because $R/\ker \phi$ has no nontrivial proper submodules, it is a field. Thence $\ker \phi$ is a maximal ideal. 

($\Leftarrow$) Say that $\phi \colon R \to M$ and $\ker \phi$ is a maximal ideal of $R$. Then $R /\ker \phi$ is a field. In particular, $R /\ker \phi$ is nonempty and has no nontrivial proper submodules. So $M \cong R / \ker \phi$ is irreducible. \qedsymbol

\newpage

### [@DF04, number 10.3.10]

\gvn Let $M$ and $N$ be irreducible $R$-modules. 

\wts Any nontrivial $R$-linear map from $M \to N$ is an isomorphism of $R$-modules.

\pf Say $\phi \colon M \to N$ is a nontrivial $R$-linear map. Then $\ker \phi \neq M$. Since $M$ is irreducible, the submodule $\ker \phi = 0$. So $$0 \to M \xrightarrow{\phi} N \quad \text{ is exact.}$$
Now nontrivial $M$ embeds as $\phi(M) \subset N$. Because $N$ is irreducible, $\phi(M) = N$. So $$0 \to M \xrightarrow{\phi} N \to 0 \quad \text{ is exact.}$$

\gvn Say $M$ is irreducible.

\wts (*Shur's Lemma*) $\End_R(M)$ is a division ring. 

*Proof by contrapositive.* We take the ring structure on $\End_R(M)$ for granted. Here we'll focus on (the lack of) zero divisors. So suppose $\alpha$ and $\beta$ are nontrivial $R$-endomorphisms of $M$. The composition $\beta \circ \alpha$ is a nontrivial endomorphism. Because $M$ is irreducible $\beta \circ \alpha$ is an isomorphism. Because $M \neq 0$, $\beta \circ \alpha$ is not the zero homomorphism. So $\End_R(M)$ has no zero divisors, and thence is a division ring. \qedsymbol

## References
