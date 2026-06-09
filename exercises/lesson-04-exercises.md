# Lesson 4 Exercises — Parity and the Alternating Group

> Convention: numbers = positions; $\sigma(i)=j$ = destination; composition right-to-left. Terminology: 二阶 / 三阶 (not 2x2 / 3x3).

---

## Warm-ups (done in-chat, learner correct)

- **W1.** $(1\,2\,3\,4)=(1\,2)(2\,3)(3\,4)$ — a $k$-cycle = $k-1$ transpositions. (Learner's bubble-sort insight.)
- **W2.** Parity by transposition count: $(1\,2)$ odd; $(1\,2\,3)$ even; $(1\,2\,3\,4)$ odd; $(1\,3)(2\,4)$ even.
- **W3.** Parity composition (add mod 2): $(1\,2\,3)(1\,2)$ odd; $(1\,2)(1\,3)$ even; $(1\,2\,3)(1\,3\,2)=e$ even; $e$ even.
- **W4 — $A_3$:** $\{e,(1\,2\,3),(1\,3\,2)\}$, all even. ✓
- **W5 — $A_4$:** $12$ elements $= 1\,(e) + 3\,(2{+}2\text{ double-transpositions}) + 8\,(3\text{-cycles})$. Anchor $4!/2=12$. (Learner first said 9, missing the $2+2$ type; corrected.)

## Cube application (in-chat)

- $k$ odd permutations composed ⇒ total parity $= k \bmod 2$.
- **三阶:** face turn = (4-cycle corners)×(4-cycle edges) = even ⇒ no lone 2-swap; min pure-position move = 3-cycle (**PLL parity**).
- **二阶:** face turn = one 4-cycle = odd ⇒ all $8!$ corner arrangements reachable; illegal states come from orientation (Lesson 7).

---

## Q1 — Classify by parity (formal)

For each permutation, give a transposition decomposition (or use the $k$-cycle rule), state even/odd, and say whether it lies in $A_n$:

1. $(1\,3\,5)$
2. $(1\,2)(3\,4)(5\,6)$
3. $(1\,2\,3\,4\,5)$
4. $(1\,2\,3\,4\,5\,6)$
5. $(1\,2\,3)(4\,5)$

## Q2 — (to be assigned after Q1)
