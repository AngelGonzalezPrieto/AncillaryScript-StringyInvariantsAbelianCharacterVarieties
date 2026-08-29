# Stringy mixed Hodge polynomials for character varieties of abelian groups

Let $G$ be a connected complex reductive group. Choose a maximal torus $T \subseteq G$ and let $W$ be the associated Weyl group. This script computes the stringy invariants of the variety
$$
    \hat{\mathfrak{X}}_G^r = T^r / W,
$$
for all $r \geq 1$, with respect to the diagonal action of $W$ on $T^r$. The variety $\hat{\mathfrak{X}}_G^r$ is the normalization of the identity component of the $G$-character variety of representations of the abelian group $\mathbb{Z}^r$,

$$
    \mathfrak{X}_G(\mathbb{Z}^r) = \text{Hom}(\mathbb{Z}^r, G) \,//\, G.
$$

Concretely, this script computes the stringy mixed Hodge polynomials of $T^r/W$, given by

$$
    \mu^{\text{str}}(T^r/W)(t, u, v) = \sum_{[w] \in \text{Conj}(W)} \mu((T^r)^w / C(w))\, (t^{2}uv)^{\text{age}(w)},
$$
where
$$
    \text{age}(w) = \frac{r}{2} \text{codim}_{T}(T^w).
$$
Here, $\text{Conj}(W)$ denotes the set of conjugacy classes of $W$, $C(w)$ is the centralizer of $w \in w$, and $(T^r)^w$ denotes the fixed-point locus of $w$ on $T^r$.

In order to do so, we implement the formula established in Theorem A of [FGPZ], which proves that
$$
        \mu^{\text{str}}(T^r/W)(t,u,v)=\sum_{[w] \in \text{Conj}(W)}
        \frac{(t^{2}uv)^{\frac{r}{2}\text{rk}\, \text{Im}(I_\Lambda -w)}}{|C(w)|}\left(\sum_{g \in C(w)} \, n_{w}(g)^r \det\left(I_{\Phi_w} + tuv\,\phi_w(g)\right)^r \right).
$$
In this formula, we consider:
- $\Lambda = X^*(T)$ is the character lattice of $T$.
- For $w \in W$, $\Phi_w$ is the free part of
$$
    \text{coker}(I_\Lambda - w) = \Lambda \,/\, \text{Im}(I_\Lambda - w).
$$
- For $g \in C(w)$, $\phi_w(g): \Phi_w \to \Phi_w$ is the map induced by $g$ on the free part $\Phi_w$ of $\text{coker}(I_\Lambda - w)$.
- For $g \in C(w)$,
$$
    n_{w}(g) = |D_w\,/\,\text{Im}(I_{D_w} - \tau_w(g))|,
$$
where $D_w$ is the torsion part of $\text{coker}(I_\Lambda - w)$ and $\tau_w(g): D_w \to D_w$ is the map induced by $g$ on $D_w$.

### Reference

- [FGPZ] Carlos Florentino, Ángel González-Prieto and Alfonso Zamora, *Stringy invariants for abelian character varieties*, 2026.
