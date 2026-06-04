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
