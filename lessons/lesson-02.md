# Lesson 2: Permutations (置换)

> Archived full content of Lesson 2 (COMPLETE 2026-06-04). Definition → notations → composition → inverse → connection to the cube.

## Motivation (from cubing intuition)

A speed cuber doing a `U` move rearranges the four corner slots. Label them 1,2,3,4; the move sends the piece in each slot to another slot — that "rearrangement of positions" is a **permutation**.

## Definition

A **permutation** of $\{1,2,\dots,n\}$ is a **bijection** $\sigma$ from the set to itself.
- function: each input has a unique output
- bijection = injective + surjective: each position is occupied by exactly one element (no overlaps, no gaps)

**Why bijection?** Cube intuition: after a turn, every slot holds exactly one piece — no two pieces in one slot, no empty slot.

The set of all permutations of $\{1,\dots,n\}$ under **composition** forms the **symmetric group** $S_n$.

### Count
$|S_n| = n!$ (it's just "arrangements" / 排列: $P(n,n) = n!$). Learner connected it immediately to permutation counting.
- $|S_4| = 24$
- $|S_8| = 40320$ = number of position arrangements of the 8 corners of a 2x2 (orientation counted separately, Lesson 7).

## Two notations

### (A) Two-line notation
$$\sigma = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 4 & 3 & 1 \end{pmatrix}$$
Top = input, bottom = output. $\sigma(1)=2,\ \sigma(2)=4,\ \sigma(3)=3$ (fixed point 不动点), $\sigma(4)=1$.

### (B) Cycle notation
Same $\sigma = (1\ 2\ 4)(3) = (1\ 2\ 4)$.
- $(1\ 2\ 4)$: $1\to2\to4\to1$ (a length-3 cycle 轮换)
- length-1 cycles (fixed points) are usually omitted
- every permutation decomposes into **disjoint cycles** (互不相交的轮换)

Exercise done in-lesson: $\begin{pmatrix}1&2&3&4&5\\3&5&1&4&2\end{pmatrix} = (1\ 3)(2\ 5)$, with 4 a fixed point. ✔ (learner correct)

## Key conceptual clarification: "position" vs "label", active vs passive

The learner asked whether the numbers mean **positions** (and "1 goes to 2" means the *content* of slot 1 moves to slot 2, while slots themselves stay fixed). This opened a crucial discussion.

### Two independent switches
The abstract fact $\sigma(1)=2$ is unambiguous as a function. Ambiguity is only in the *physical interpretation*, and there are **two independent switches**:

- **Switch ①: what the numbers denote** — position/slot vs object/label
- **Switch ②: direction of the arrow $\sigma(i)=j$** — destination ("content of $i$ *goes to* $j$") vs source ("slot $i$ *receives from* $j$")

**Course convention (locked):** numbers = **positions/slots**; $\sigma(i)=j$ = **destination**. Slots are fixed in space; turning a face moves pieces between fixed slots. Matches the cube perfectly.

### What actually changes the answer
- Flipping **switch ①** (slot → label) is just **relabeling** — same physical reality, different language. **Answer unchanged.**
- Flipping **switch ②** (destination → source) is a **different operation** — it differs by $\sigma^{-1}$. **Answer changes** (e.g. slot 1's content flips between blue and green).

The folklore "relabeling view gives the inverse result" is really caused by switch ②, often bundled together with ① — separating them dissolves the confusion.

### Active vs passive (learner's own analogy)
The learner independently rediscovered the physics distinction:
- **Interpretation A = active transformation**: reference frame (fixed spatial slots) stays put; objects are physically moved. A real turn.
- **Interpretation B = passive transformation**: objects stay; the coordinate/naming system changes; we describe the *same static reality* differently.

**Correction made:** passive is NOT "moves only some pieces". Active and passive describe the **same** $\sigma$ and must yield **identical physical conclusions** (which pieces move, where) — they differ only in *language*. Passive's real use case: a *global re-coordinatization* with **no physical motion at all** (e.g. CFOP vs Roux numbering the same scramble differently). A `U` turn is genuine physical motion ⇒ **active**. So "cube turns use A" is right, but the reason is "a turn is real motion", not "B only moves some pieces".

One-liner: **Switch ① (slot vs label) = change of words, no physics change. Switch ② (destination vs source) = change of operation, differs by an inverse.**

### Filling-a-slot uses the inverse
To find what ends up in slot 1 under $(1\ 2\ 4)$ acting on {slot1=red, slot2=green, slot4=blue}: find $i$ with $\sigma(i)=1$, i.e. $\sigma^{-1}(1)=4$ → **blue**. (Learner solved correctly.) Remember this "filling a slot needs the inverse" feeling — it returns in composition.

## Terminology
- **scramble** = 打乱: either the act of mixing a solved cube, or the resulting mixed state / the sequence that produces it (competition "scramble sequence" e.g. `R U2 F' R2 ...`). A scramble state = an element of the cube group $G$; solving it = taking the inverse.

## Composition (复合)

Permutations are functions, so they compose. **Convention (locked, mathematician's): right-to-left**, matching $f\circ g$:
$$(\tau\sigma)(i) = \tau(\sigma(i))$$
So "**do $A$ then $B$**" is written $\boxed{BA}$ — the later move on the left.

Worked example: $\sigma=(1\,2),\tau=(2\,3)$ on $\{1,2,3\}$.
- $\tau\sigma$ (first $\sigma$ then $\tau$): trace $(\tau\sigma)(i)=\tau(\sigma(i))$ -> $1\to3,2\to1,3\to2$ = $(1\ 3\ 2)$.
- $\sigma\tau$ (first $\tau$ then $\sigma$) -> $(1\ 2\ 3)$.
- $\tau\sigma \neq \sigma\tau$ => $S_n$ ($n\ge3$) is **non-Abelian** — the $RU\neq UR$ from Lesson 1, now in $S_n$.

### Convention clash with cubing notation
- **Mathematician (this course):** $AB$ means do $B$ first (right-to-left).
- **Many cubing texts:** read `R U R'` left-to-right (R first).
These are opposite. Neither is wrong; we lock the mathematician's convention (consistent with function composition, $(AB)^{-1}=B^{-1}A^{-1}$, conjugation, commutators). In Module 2, move order will be annotated explicitly on every algorithm.

Learner exercise (correct): $\alpha=(1\,2\,3),\beta=(1\,2)$ -> $\beta\alpha=(2\ 3)$. Learner used an efficient "whole-row tracking" notation: `[1,2,3]->[2,3,1]->[1,3,2]`.

## Inverse (逆置换)

$\sigma^{-1}$ undoes $\sigma$: $\sigma^{-1}\sigma=\sigma\sigma^{-1}=e$.

**Method 1 (two-line):** swap the two rows, then re-sort by the top row.
**Method 2 (cycle):** reverse each cycle. $(1\ 2\ 4)^{-1}=(1\ 4\ 2)$. Intuition: reverse the arrows ("filling a slot uses $\sigma^{-1}$" from earlier).

**Order-reversal property** (foreshadowed in Lesson 1): $(\tau\sigma)^{-1}=\sigma^{-1}\tau^{-1}$ (socks-and-shoes). A hallmark of non-commutativity.

Learner exercise (correct): $\gamma=(1\,3\,4\,2)$ -> $\gamma^{-1}=(2\ 4\ 3\ 1)=(1\ 2\ 4\ 3)$, verified $\gamma^{-1}\gamma$ returns `[1,2,3,4]`=$e$.
**Note taught:** a cycle can start from any of its elements; $(2\ 4\ 3\ 1)=(1\ 2\ 4\ 3)$ are the same cycle — don't mistake a different starting point for a wrong answer.

## Connecting back to the cube — a turn IS a permutation

Number the 8 corner **slots** 1–8. A `U` (top clockwise) only moves the 4 top corners. With top slots 1,2,3,4 clockwise:
$$U = (1\ 2\ 3\ 4)$$
(bottom 5,6,7,8 fixed). This captures only **position**, not **orientation** (each slot has 3 twist states, needs an extra $\mathbb{Z}_3$ structure — Lesson 7). Today: position layer only = pure $S_8$.

Learner exercise (correct): $U^2=(1\ 3)(2\ 4)$ — "every corner goes to its diagonal", two disjoint transpositions.

**Structure observation (foreshadows Lesson 3 order):** $U^1=(1234),U^2=(13)(24),U^3=(1432),U^4=e$. The element $U$ has **order 4**; $\{e,U,U^2,U^3\}\cong C_4$ — permutations, cube, and cyclic group fully converge.

## Lesson 2 knowledge map
| Concept | Key point |
|---------|-----------|
| Permutation | bijection on $\{1..n\}$; $\lvert S_n\rvert=n!$ |
| Notation | two-line <-> cycle; disjoint-cycle decomposition |
| Composition | $\tau\sigma$ = first $\sigma$ then $\tau$ (right->left); non-Abelian for $n\ge3$ |
| Inverse | reverse arrows/cycles; $(\tau\sigma)^{-1}=\sigma^{-1}\tau^{-1}$ |
| Cube link | turn = permutation; $U=(1234)$; position layer = $S_8$ (orientation -> Lesson 7) |

## Next lesson
**Lesson 3: Order, Subgroups, Generators.** Formalize $|U|=4$ (order of an element), subgroup test, generators $\langle g_1,\dots\rangle$, Cayley graph — toward $\langle R,U,F\rangle$ generating the cube group.
