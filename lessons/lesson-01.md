# Lesson 1: What is a Group? (群)

> Archived full content of Lesson 1, including the key Q&A clarifications that arose during teaching. This file lets any future session see exactly what was covered.

## Motivation (from cubing intuition)

A speed cuber already uses a group daily: chaining moves like `R U R' U'`, where R followed by R' cancels, and "doing nothing" counts as an operation. Group theory axiomatizes this intuition.

## Definition of a Group

A group $(G, \cdot)$ is a set $G$ with a **binary operation** $\cdot$ satisfying four axioms:

| Axiom | Name | Meaning | Cube intuition |
|-------|------|---------|----------------|
| 1 | Closure (封闭性) | $a,b \in G \Rightarrow a\cdot b \in G$ | composing two moves gives another cube state |
| 2 | Associativity (结合律) | $(a\cdot b)\cdot c = a\cdot(b\cdot c)$ | regrouping parentheses, same result |
| 3 | Identity (单位元) | $\exists e: e\cdot a = a\cdot e = a$ | doing nothing |
| 4 | Inverse (逆元) | $\forall a, \exists a^{-1}: a\cdot a^{-1}=e$ | every move can be undone (R' undoes R) |

**Groups do NOT require commutativity.** Abelian = commutative; the cube group is non-Abelian (`RU` ≠ `UR`).

## Examples

- $(\mathbb{Z}, +)$: Abelian group. Identity 0, inverse of $a$ is $-a$.
- $(\mathbb{Z}^+, \times)$: NOT a group (no integer inverses).
- Rotations of a square $\{r_0, r_1, r_2, r_3\}$ ($0°,90°,180°,270°$) under composition: the cyclic group $C_4$.

## Key Q&A clarifications (raised by the learner)

### Q: Is the group operation restricted to binary?
**Yes.** Group operation is strictly $\cdot: G\times G \to G$. A unary op (e.g. boolean negation) or ternary op (e.g. `?:`) cannot BE a group operation. But a unary map like negation can be a group *element*: $\{\text{id}, \neg\}$ under function composition is a group $\cong C_2$. Key insight for cube: **R is an element; "chaining moves" is the (binary) operation.** N-ary groups exist as generalizations but are out of scope.

### Q: If commutativity fails, what good is associativity?
Associativity = re-grouping (parentheses), commutativity = re-ordering. **Different things.**
- Associativity makes a move *sequence* well-defined: `R U R' U'` means the same regardless of bracketing, so we can write formulas without parentheses. This is the foundation of algorithm notation.
- It lets us split long algorithms into meaningful sub-blocks and analyze them independently — the basis for commutators $[A,B]=ABA^{-1}B^{-1}$ and conjugation $AXA^{-1}$ in Module 3.
- It makes powers ($R^3$) and $(AB)^{-1}=B^{-1}A^{-1}$ well-defined (note the order reversal — that's the non-commutativity showing).

Analogy: socks-then-shoes. You can re-bracket which steps you "package" together, but you cannot swap their order.

> Phrasing correction made during lesson: "which step is computed first" was ambiguous — associativity changes the *parenthesization/parse grouping*, NOT the physical move order. Move order R→U→F is unchanged.

### Q: In example 3, what exactly are the set and the operation?
- Set: the four rotation *operations* $\{r_0, r_1, r_2, r_3\}$ (the operations themselves, not cube states).
- Operation: composition of rotations = angle addition mod 360°.
- This is $C_4$, identical in structure to "only turning the R face" on a 2x2: $\{e, R, R^2, R^3\}$.

### Q: Is the identity always its own inverse?
**Yes**, $e^{-1}=e$, since $e\cdot e = e$. The converse is false: elements with $a^{-1}=a$ are **involutions** (e.g. $r_2$ = 180° rotation, $R^2$ on the cube); the identity is just one special case.

## Exercises (all solved correctly by learner)

- **Q1**: $(\{1,-1\}, \times)$ — Abelian group. Identity 1, each element its own inverse (both involutions). $\cong C_2$.
- **Q2**: $(\{0,1,2,3\}, +_4)$ — group, identity 0, inverses $0,3,2,1$. $\cong C_4$ (same as square rotations).
- **Q3**: 2x2 turning only R face $\{e,R,R^2,R^3\}$ — $\cong C_4$.

## Big takeaway

A group is a **structure**, not a specific set. $C_4$ has many incarnations: mod-4 addition, square rotations, single-face cube turns, powers of $i$. This is *why* group theory solves cubes: the cube's operations and abstract algebraic structures are literally the same objects. Complexity of the cube comes NOT from a single generator (each is a trivial $C_4$) but from the **non-commutativity among generators R, U, F**.
