# Lesson 4: Parity and the Alternating Group (奇偶性与交错群)

> Archived full content of Lesson 4 (COMPLETE 2026-06-09). Transpositions -> parity theorem -> sign (Z2 / ±1) -> alternating group $A_n$ -> cube application (CORRECTED to 三阶 PLL parity; 二阶 deferred to Lesson 7). Convention (locked): numbers = positions; $\sigma(i)=j$ = destination; composition right-to-left ($ab$ = first $b$ then $a$). Terminology: use **二阶 / 三阶** (not 2x2 / 3x3) for clarity and consistency.

## Cube motivation
Speed cuber knows "illegal" near-solved states: a single 2-piece swap, a single edge flip — unreachable without disassembly. Root cause is the binary invariant **parity**. (Caveat resolved at end: this story is genuinely about 三阶 position parity; 二阶's illegal states are about orientation, Lesson 7.)

## Step 1: Transpositions (对换)
**Transposition** = length-2 cycle $(a\,b)$, swaps two points, fixes the rest.

**Foundational fact:** every permutation is a product of transpositions. A length-$k$ cycle splits into $k-1$ transpositions:
$$(a_1\,a_2\,\dots\,a_k) = (a_1\,a_2)(a_2\,a_3)\cdots(a_{k-1}\,a_k)$$
(right-to-left). Verified $(1\,2\,3)=(1\,2)(2\,3)$.

Learner warm-up (correct): $(1\,2\,3\,4)=(1\,2)(2\,3)(3\,4)$.

**Learner's bubble-sort insight:** executing $(1\,2)(2\,3)(3\,4)$ right-to-left = one bubble-sort pass — the rightmost element travels all the way left while every other element shifts right one slot. Tutor named two payoffs:
1. **adjacent transpositions** $(1\,2),(2\,3),\dots$ alone generate $S_n$ (bubble sort uses only adjacent swaps);
2. **parity = parity of the inversion count** (bubble-sort swap count).

## Step 2: Parity theorem (奇偶性定理)
Transposition decomposition is **not unique** (e.g. $(1\,2\,3)=(1\,2)(2\,3)=(1\,3)(1\,2)=\dots$; can pad with $(a\,b)(a\,b)=e$). The **count** varies, but its **parity is invariant**.

> **Parity theorem:** the parity (even/odd) of the number of transpositions in any decomposition of $\sigma$ is well-defined.
- **even permutation (偶置换):** always an even number of transpositions.
- **odd permutation (奇置换):** always an odd number.

**Speed rule:** a $k$-cycle has parity of $k-1$. So even-length cycles (2-,4-,...) are **odd** permutations; odd-length cycles (3-,5-,...) are **even**. Anchor: a single transposition is odd.

Learner classification (correct): $(1\,2)$ odd; $(1\,2\,3)$ even; $(1\,2\,3\,4)$ odd; $(1\,3)(2\,4)$ even (1+1=2).

## Step 3: Sign — parity is "additive" (sign homomorphism seed)
Parity adds under composition: if $\sigma$ uses $p$ transpositions and $\tau$ uses $q$, then $\tau\sigma$ uses $p+q$.

| | even | odd |
|---|---|---|
| **even** | even | odd |
| **odd** | odd | even |

**Learner's key insight: "this is addition, not multiplication."** Affirmed — sign is fundamentally $\mathbb{Z}_2$ (even→0, odd→1, **add mod 2**). The "multiply ±1" encoding (even→+1, odd→−1, via $\operatorname{sgn}(\sigma)=(-1)^{\#\text{transpositions}}$) gives the *same* table; the two are isomorphic: $(\{0,1\},+\bmod 2)\cong(\{+1,-1\},\times)\cong C_2$ via $n\mapsto(-1)^n$. (Learner initially mis-stated the table as even×odd=even, because he hadn't yet accepted the +1/−1 encoding; corrected by concrete check.)

Facts: $e$ is **even** (0 transpositions); $\sigma$ and $\sigma^{-1}$ have the **same parity**.

This $\operatorname{sgn}:S_n\to\{\pm1\}$ is the first and most important **homomorphism** — leads straight into Lesson 5.

## Step 4: Alternating group $A_n$ (交错群)
Even permutations form a subgroup (closure even×even=even; contains $e$; inverses same parity) — the **alternating group** $A_n$. Odd permutations do **not** form a subgroup (no $e$; odd×odd=even escapes).

$$|A_n| = \frac{n!}{2}\quad(n\ge 2)$$
Reason: multiplying by a fixed transposition is a bijection between even and odd halves ⇒ equal sizes.

- $A_3=\{e,(1\,2\,3),(1\,3\,2)\}$ — the order-3 cyclic subgroup from Lesson 3.
- $A_4$ has $12$ elements: $1$ identity + $3$ double-transpositions ($2{+}2$) + $8$ three-cycles. **Learner error caught:** first said 9, missing the $2+2$ double-transpositions. Method reinforced: use $n!/2$ as an anchor, enumerate by cycle shape, cross-check. The 3 double-transpositions $\{(1\,2)(3\,4),(1\,3)(2\,4),(1\,4)(2\,3)\}$ are $U^2$-type (even); they + $e$ form the **Klein four-group $V_4$** (deferred).

Learner's discovery: $(1\,2)(2\,3)=(1\,3)(1\,2)$ — non-unique decomposition, parity preserved (both 2 transpositions). His derivation: rewrote $(1\,2\,3)=(3\,1\,2)$ (same cycle, new start point) THEN applied the formula $(a_1a_2a_3)=(a_1a_2)(a_2a_3)$ — fully right-to-left, correct. (Tutor first mis-flagged a convention slip, then RETRACTED after learner clarified. Confirmed: the formula $(abc)=(ab)(bc)$ is itself right-to-left; left-to-right convention would write $(bc)(ab)$.)

## Step 5: Cube application — CORRECTED

> **Honest correction (learner pushed back, tutor's first version was wrong).** The initial attempt tried to argue "二阶: a 2-corner swap is illegal" using a vague "conserved quantity" while avoiding orientation (not yet taught). That argument was muddled AND wrong. The clean, position-only payoff lives on **三阶**, not 二阶.

### Setup (correct part)
$k$ odd permutations composed ⇒ total parity $= k \bmod 2$ (learner answered correctly: total parity matches parity of $k$).

### 二阶 (2x2): NO position-parity constraint
- 二阶 has only 8 corners. A face turn = **one 4-cycle** on corners = **odd** permutation.
- A single move already produces an odd permutation ⇒ odd permutations are reachable.
- ⇒ **All $8!$ corner position arrangements are reachable** (fixing one corner as frame, the other 7 realize all $7!$, including odd ones). 二阶 has no position-parity obstruction.
- 二阶's genuine illegal states come from **orientation**: $\sum o_i \equiv 0 \pmod 3$ — **deferred to Lesson 7**.

### 三阶 (3x3): the real parity payoff (position only, no orientation)
- A 三阶 face turn = (4-cycle on 4 corners) × (4-cycle on 4 edges) = odd × odd = **even**.
- So every face turn's total permutation on movable pieces is **even** ⇒ every reachable state is even.
- A single 2-swap (one transposition) is **odd** ⇒ **unreachable**. This is the well-known **PLL parity**: you can never swap just two pieces; the minimum pure-position change is a **3-cycle** (even).

### Contrast (memorize)
- **三阶:** corner+edge total permutation is even ⇒ no lone 2-swap. ← today's parity payoff.
- **二阶:** single face turn = one 4-cycle = odd ⇒ any corner arrangement reachable; illegal states are **orientation**-based (Lesson 7).

**Learner correction logged:** tutor speculated the corner/edge parity coupling "affects feel"; learner refuted — he plays 二阶 by treating it as the 8 corners of a 三阶 and uses 三阶 algorithms, so there is no independent 二阶 "feel". Speculation withdrawn.

## Lesson 4 knowledge map
| Concept | Key point |
|---------|-----------|
| Transposition | $(a\,b)$; $k$-cycle = $k-1$ transpositions; any perm = product of transpositions |
| Parity theorem | even/odd well-defined (count's parity invariant) |
| Speed rule | $k$-cycle parity = parity of $k-1$ (even-length cycle = odd perm) |
| Sign | parity adds mod 2; $\mathbb{Z}_2\cong(\{\pm1\},\times)$; $\operatorname{sgn}(\sigma)=(-1)^{\#}$; $e$ even; $\sigma,\sigma^{-1}$ same parity |
| $A_n$ | even perms; subgroup; $|A_n|=n!/2$; odd perms not a subgroup |
| 三阶 payoff | face turn = even ⇒ no lone 2-swap; min pure-position move = 3-cycle (PLL parity) |
| 二阶 | no position-parity constraint; illegal states = orientation ($\sum o_i\equiv0\bmod3$, Lesson 7) |

## Next lesson
**Lesson 5: Homomorphisms and Isomorphisms.** Structure-preserving maps; $\operatorname{sgn}:S_n\to\{\pm1\}$ as the headline example (today's sign); kernel ($=A_n$) and image; first isomorphism theorem (intuition).
