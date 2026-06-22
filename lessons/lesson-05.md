# Lesson 5: Homomorphisms and Isomorphisms (同态与同构)

> **STATUS: IN PROGRESS** — Sessions 11 & 13 content archived below. Kernel done; image + first isomorphism theorem still to come. This file will be finalized when the lesson completes.

---

## Part 1 — Homomorphism & Isomorphism (Session 11)

### Motivation
From Lesson 4 we have $\operatorname{sgn}(\tau\sigma)=\operatorname{sgn}(\tau)\operatorname{sgn}(\sigma)$. This "the operation is preserved" property is the heart of a **homomorphism** — a map that *translates one group's operation into another's*.

### Definition (Homomorphism / 同态)
A map $\varphi:G\to H$ between groups is a **homomorphism** if
$$\varphi(ab)=\varphi(a)\,\varphi(b)\quad\forall a,b\in G.$$
Note: the operation on the left is $G$'s; on the right is $H$'s. They may be *different* operations (e.g. $+$ on the left, $\times$ on the right) — that's the power of homo.

### Definition (Isomorphism / 同构)
An **isomorphism** is a **bijective** homomorphism. Homomorphism is the looser notion — it allows information loss (e.g. $\operatorname{sgn}$ collapses $n!$ permutations to 2 values).

### Two-level reading of $\cong$
- **(Level 1, about a map)** "$\varphi$ is an isomorphism" = $\varphi$ is a bijective homomorphism.
- **(Level 2, about groups)** "$G\cong H$" = **there exists** an isomorphism map $\varphi:G\to H$.

Analogy: "two cities are connected" (relation, level 2) vs "there exists a road between them" (the map, level 1).

### $\cong$ is an equivalence relation
- **Reflexive:** $G\cong G$ via the identity map.
- **Symmetric:** if $\varphi:G\to H$ is an iso, so is $\varphi^{-1}:H\to G$.
- **Transitive:** if $G\cong H$ and $H\cong I$, compose the two iso maps ($\psi\circ\varphi$ is bijective + preserves the operation by applying the homo property twice).

These three are exactly closure of iso maps under identity / inverse / composition.

### Homomorphism structure as a class invariant
Isomorphism preserves a group's *entire* homomorphism structure: $\operatorname{Hom}(G,K)\leftrightarrow\operatorname{Hom}(H,K)$ when $G\cong H$. So studying any one representative studies the whole isomorphism class. The richest case: $G\to G$ self-maps = **automorphisms** $\operatorname{Aut}(G)$, nontrivial even though $G\cong G$ is trivial.

**Cube link (planted, pays off at Lesson 11):** cube symmetries (R/L mirror, global rotation) are automorphisms; **conjugation $g\mapsto xgx^{-1}$ = inner automorphism = the group-theoretic essence of setup moves**.

### A homomorphism from a cyclic group is determined by its generator's image
For a cyclic group $G=\langle g\rangle$: once you choose $\varphi(g)$, the whole map is forced, because $\varphi(g^k)=\varphi(g)^k$ follows from operation-preservation.
- Example shorthand "$\varphi:U\mapsto U^3$" on $C_4=\langle U\rangle$ really means $e\mapsto e,\ U\mapsto U^3,\ U^2\mapsto U^2,\ U^3\mapsto U$.
- **Caveat:** for non-cyclic groups (e.g. $S_3$, cube $\langle R,U,F\rangle$) you must specify ALL generators' images, and they must respect the relations between generators (matters at Lesson 8).

### Practice set (Session 12)
Worked examples A1–A8 and exercises B1–B6 are in `exercises/lesson-05-exercises.md`. B7 (cube projection homomorphism) deferred to Lesson 7.

---

## Part 2 — Kernel (Session 13)

### Motivating question
$\operatorname{sgn}:S_n\to\{\pm1\}$ "crushes" $n!$ permutations down to 2 values. What is the set crushed to $+1$, and what structure does it have?

**Answer (learner, correct):** the **alternating group $A_n$** — the even permutations (decomposable into an even number of transpositions), a subgroup of $S_n$.

### Definition (Kernel / 核)
Given a homomorphism $\varphi:G\to H$,
$$\ker\varphi=\{g\in G\mid \varphi(g)=e_H\}$$
i.e. all elements of $G$ mapped to the **target group's identity**.

### Three examples, restated in kernel language
| homomorphism | $\ker$ | intuition |
|---|---|---|
| $\operatorname{sgn}:S_n\to\{\pm1\}$ | $A_n$ (even perms) | "those crushed to $+1$" |
| $\det:GL_n(\mathbb R)\to\mathbb R^\times$ | $SL_n$ (det = 1 matrices) | "volume-preserving linear maps" |
| $\mathbb Z\to\mathbb Z_n,\ k\mapsto k\bmod n$ | $n\mathbb Z=\{0,\pm n,\pm2n,\ldots\}$ | "multiples of $n$ all map to $0$" |

### Theorem: $\ker\varphi\le G$
**Proof (learner, via the two-step subgroup test).** Suppose $a,b\in\ker\varphi$, i.e. $\varphi(a)=\varphi(b)=e_H$.

**Closure.** $\varphi(ab)=\varphi(a)*\varphi(b)=e_H*e_H=e_H$, so $ab\in\ker\varphi$. ✓

**Inverses.** The naive chain "$\varphi(a^{-1})=\varphi(e_G)$, and $\varphi$ maps all of $G$ to $e_H$, so $\varphi(a^{-1})=e_H$" has a **gap**: the middle claim is false (it would describe the trivial homomorphism). The missing piece is a lemma.

> **Lemma.** Every homomorphism satisfies $\varphi(e_G)=e_H$.
>
> *Proof.* $e_G\cdot e_G=e_G$, so applying $\varphi$ and using the homomorphism property:
> $$\varphi(e_G)=\varphi(e_G\cdot e_G)=\varphi(e_G)*\varphi(e_G).$$
> Cancelling one $\varphi(e_G)$ on both sides (i.e. multiplying by its inverse in $H$) gives $e_H=\varphi(e_G)$. $\square$

Now finish inverses: with $a\in\ker\varphi$,
$$e_H=\varphi(e_G)=\varphi(a\cdot a^{-1})=\varphi(a)*\varphi(a^{-1})=e_H*\varphi(a^{-1}),$$
and cancelling $e_H$ gives $\varphi(a^{-1})=e_H$, so $a^{-1}\in\ker\varphi$. ✓

Hence $\ker\varphi$ is a subgroup of $G$. $\square$

### Meta-lesson
The subtle distinction between **definition** (homo $\Leftrightarrow$ $\varphi(ab)=\varphi(a)\varphi(b)$) and **theorem** ($\varphi(e_G)=e_H$ is a *consequence*, derived by cancellation). Treating the theorem as part of the definition is the classic foundational slip.

### Kernel 的判据作用（PROBLEM OPEN — learner answer not yet submitted）

Kernel 不只是"一个子群"，它还**刻画了 $\varphi$ 是否单射**:

> **Criterion.** $\varphi\text{ 是单射 (injective)}\ \iff\ \ker\varphi=\{e_G\}$

- **($\Rightarrow$) 单射 $\Rightarrow$ 核只有 $e$:** 显然。单射下只有 $e_G$ 一个元素能映到 $e_H$(否则有两个元素映到同一个 $e_H$,违反单射)。

- **($\Leftarrow$) 核只有 $e$ $\Rightarrow$ 单射: ⚠️ 待证。**
  Tutor 的提示:假设 $\varphi(a)=\varphi(b)$,试着构造一个 kernel 的元素。

  *(预期路径,learner 尚未提交:从 $\varphi(a)=\varphi(b)$ 两边作用 $\varphi(b)^{-1}$ 得 $\varphi(a)\varphi(b)^{-1}=e_H$;若能用同态性把 $\varphi(a)\varphi(b)^{-1}$ 写成 $\varphi(ab^{-1})$,则 $ab^{-1}\in\ker\varphi=\{e_G\}$,故 $ab^{-1}=e_G\Rightarrow a=b$。关键卡点:需要先证 $\varphi(b)^{-1}=\varphi(b^{-1})$,即同态保持逆元。)*

---

## Part 3 — Image & First Isomorphism Theorem (NOT YET TAUGHT)

**Next session:** define $\operatorname{im}\varphi=\varphi(G)\subseteq H$, prove $\operatorname{im}\varphi\le H$, then the **first isomorphism theorem** (intuition only for now):
$$G/\ker\varphi\ \cong\ \operatorname{im}\varphi.$$
This recovers, as a theorem, the "crushing" picture: $G$ modulo the part crushed to the identity is exactly the image. The $\operatorname{sgn}$ example gives $S_n/A_n\cong\{\pm1\}$.
