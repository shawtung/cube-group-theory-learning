# Lesson 2 Exercises — Permutations (置换)

> Conventions: numbers = positions/slots; $\sigma(i)=j$ means "content of slot $i$ goes to slot $j$" (destination). Composition is **right-to-left**: $\tau\sigma$ means do $\sigma$ first, then $\tau$.

**Q1 (notation conversion).** Convert to disjoint-cycle notation and name any fixed points:
$$\pi = \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 4 & 6 & 3 & 5 & 1 & 2 \end{pmatrix}$$

**Q2 (composition).** In $S_4$, let $a=(1\ 2\ 3)$ and $b=(2\ 3\ 4)$. Using the right-to-left convention, compute:
- (a) $ba$ (first $a$, then $b$)
- (b) $ab$ (first $b$, then $a$)
- (c) Are they equal? What does that tell you about $S_4$?

**Q3 (inverse).** Let $\sigma=(1\ 4\ 2\ 5\ 3)\in S_5$. Write $\sigma^{-1}$ in cycle notation, then verify $\sigma^{-1}\sigma$ sends 1 back to 1.

**Q4 (order-reversal).** Using $a,b$ from Q2, compute $(ba)^{-1}$ two ways: (i) directly invert your answer to Q2(a); (ii) via $a^{-1}b^{-1}$. Confirm they match.

**Q5 (cube link).** On the 2x2, number the top corner slots 1,2,3,4 clockwise and the bottom slots 5,6,7,8. Suppose a move $M$ acts as $M=(1\ 5\ 8\ 4)(2\ 6\ 7\ 3)$ (ignoring orientation).
- (a) Which physical move on a real 2x2 could this be (describe in words)? 
- (b) Compute $M^2$ in cycle notation.
- (c) What is the order $|M|$ (smallest $k>0$ with $M^k=e$)?

**Stretch.** A permutation's order equals the **lcm of its disjoint cycle lengths**. Using this rule, what is the order of $(1\ 2\ 3)(4\ 5)\in S_5$? (Preview of Lesson 3.)

---

## Solutions (completed 2026-06-04)

**Q1.** $\pi=(1\ 4\ 5)(2\ 6)$; fixed point $3$.

**Q2.** (a) $ba=(1\ 3)(2\ 4)$. (b) $ab=(1\ 2)(3\ 4)$. (c) $ba\neq ab$ \u21d2 $S_4$ is **non-Abelian** (not commutative).

**Q3.** $\sigma^{-1}=(3\ 5\ 2\ 4\ 1)$ (reverse the cycle; may start anywhere, e.g. $(1\ 3\ 5\ 2\ 4)$). Check: $1\xrightarrow{\sigma}4\xrightarrow{\sigma^{-1}}1$. \u2713

**Q4.** (i) $(ba)^{-1}$: $ba=(1\ 3)(2\ 4)$ is a product of involutions, so its inverse is itself $=(1\ 3)(2\ 4)$. (ii) $a^{-1}b^{-1}=(1\ 3\ 2)(2\ 4\ 3)=(1\ 3)(2\ 4)$. Match. **Note:** the reversal in $(ba)^{-1}=a^{-1}b^{-1}$ is *visually masked* here only because $ba$ is an involution.

**Q5.** (a) $M$ moves all 8 corners (two 4-cycles cover every slot), whereas a single 2x2 face turn moves only 4 corners \u2014 so $M$ is a **whole-cube rotation** (e.g. $x$), not a face turn. (b) $M^2=(1\ 8)(2\ 7)(3\ 6)(4\ 5)$. (c) $|M|=\operatorname{lcm}(4,4)=4$.

**Stretch.** $|(1\ 2\ 3)(4\ 5)|=\operatorname{lcm}(3,2)=6$.
