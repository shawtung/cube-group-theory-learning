# Group Theory & the 2x2 Rubik's Cube - Syllabus

## Learner Profile
- **Math**: university-level (linear algebra, probability); no abstract algebra
- **Cube**: speed cuber (CFOP/Roux etc.), fluent in notation
- **Goals**: intuitive understanding + manual derivation + programming implementation
- **Language**: bilingual (Chinese + English terms)

---

## Module 1: Group Theory Foundations (from scratch)

### Lesson 1: What is a Group? (group / 群)
- Motivate from symmetry of a square
- Four axioms: closure, associativity, identity, inverse
- Verify: integers under addition vs multiplication
- **Exercise**: prove (or disprove) whether a given set+operation forms a group

### Lesson 2: Permutations (permutation / 置换)
- Symmetric group $S_n$: all bijections on $\{1,...,n\}$
- Two-line notation, cycle notation (轮换记法)
- Composing permutations (left-to-right vs right-to-left convention)
- **Exercise**: compute products and inverses in $S_4$

### Lesson 3: Order, Subgroups, Generators
- Order of an element / order of a group (元素的阶 / 群的阶)
- Subgroup (子群) and the subgroup test
- Generators (生成元): $\langle g_1, g_2, ... \rangle$
- Cayley graph intuition
- **Exercise**: find all subgroups of $S_3$; find generators

### Lesson 4: Parity and the Alternating Group
- Even vs odd permutations (奇置换 / 偶置换)
- Sign homomorphism $\text{sgn}: S_n \to \{+1, -1\}$
- Alternating group $A_n$
- **Cube application (corrected):** the parity payoff is the **三阶 (3x3) PLL parity** — a face turn = 4-cycle on corners × 4-cycle on edges = even, so no single 2-swap is reachable (minimum pure-position move = 3-cycle). This uses position only, no orientation.
- **NOTE:** 二阶 (2x2) has NO position-parity constraint (single face turn = one 4-cycle = odd ⇒ all $8!$ corner arrangements reachable). 二阶's illegal states come from **orientation** → deferred to Lesson 7.
- **Exercise**: classify permutations by parity

### Lesson 5: Homomorphisms and Isomorphisms
- Structure-preserving maps (同态 / 同构)
- Kernel and image
- First isomorphism theorem (intuition only)
- **Exercise**: find a homomorphism between two familiar groups

### Lesson 6: Direct and Semi-direct Products
- Direct product $G \times H$ (直积)
- Semi-direct product (半直积) - intuition via "twist"
- Wreath product (圈积) - preview for cube group structure
- **Exercise**: identify product structure in small groups

---

## Module 2: The 2x2 Cube as a Group

### Lesson 7: Modeling the 2x2 Cube
- Label corners: position + orientation (位置 + 朝向)
- State space: $(p, o) \in S_8 \times \mathbb{Z}_3^8$
- Constraint: $\sum o_i \equiv 0 \pmod{3}$
- **Carryover from Lesson 4:** explain 二阶's illegal states here — they come from the orientation constraint $\sum o_i \equiv 0 \pmod 3$, NOT from position parity (二阶 has no position-parity constraint). This is the deferred "why some 二阶 states are unsolvable" discussion.
- Fix a reference corner -> effective group
- **Exercise**: represent a specific scramble as $(p, o)$

### Lesson 8: Generators of the Pocket Cube Group
- Generators $\langle R, U, F \rangle$ (fixing one corner)
- Write R, U, F as explicit permutations + orientation changes
- Verify $R^4 = e$, compute $|RU|$
- **Exercise**: express a given state as a word in $R, U, F$

### Lesson 9: Structure of the Pocket Cube Group
- $G \cong (A_8 \times \mathbb{Z}_3^7) \rtimes \mathbb{Z}_2$ ... actually
- Correct structure: subgroup of $S_8 \ltimes \mathbb{Z}_3^8$
- Group order: $|G| = 3{,}674{,}160$
- Why not all of $S_8 \times \mathbb{Z}_3^8$ is reachable
- **Exercise**: verify the order calculation

---

## Module 3: Deriving Algorithms via Group Theory

### Lesson 10: Commutators (交换子)
- $[A, B] = ABA^{-1}B^{-1}$
- Why commutators affect fewer pieces
- "Support" of a permutation (支撑集)
- **Exercise**: compute $[R, U]$ on the 2x2 and analyze which pieces move

### Lesson 11: Conjugation (共轭)
- $gxg^{-1}$: "setup move" in cubing language
- Conjugacy classes (共轭类)
- Transporting an algorithm to a different position
- **Exercise**: given a 3-cycle algorithm, use conjugation to target different corners

### Lesson 12: Building a Layer-by-Layer Solve from Scratch
- Step 1: permutation fix via 3-cycles (constructed from commutators)
- Step 2: orientation fix via twist commutators
- Verify: each step is a valid group element that composes to the solution
- **Exercise**: solve a specific scramble using only derived algorithms

---

## Module 4: Programming the Pocket Cube Group

### Lesson 13: Representing States in Code
- Data structure: array of (position, orientation)
- Implementing the group operation (composition)
- Implementing inverse
- **Exercise**: code the state representation and verify $R^4 = e$

### Lesson 14: Exploring the Group Computationally
- BFS to enumerate all states (God's number = 11 for 2x2)
- Verify group order
- Find the distribution of states by distance from solved
- **Exercise**: compute and display the distance distribution

### Lesson 15: Optimal Solver
- BFS / IDA* from both ends
- Using symmetry to reduce search space (cosets)
- **Exercise**: implement a solver that finds optimal solutions

---

## Capstone
- Write up: explain to a friend how group theory makes cube algorithms "obvious"
- Stretch: generalize the framework to 3x3 (preview)
