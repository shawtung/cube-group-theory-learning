# Lesson 2: Permutations (置换)

> Archived content of Lesson 2. In progress — covers up through the active/passive distinction; Step 3 (composition) still to come.

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

## Next step (to resume)
**Step 3: Composition of permutations** — left-to-right vs right-to-left convention; "do A then B" written as $BA$ vs $AB$. This is the function-composition direction question under the active view.
