# Teaching Log & Progress Tracker

## Current Status
- **Current Lesson**: Lesson 4 (Parity and the Alternating Group) **COMPLETE** (2026-06-09); next up Lesson 5 (Homomorphisms and Isomorphisms)
- **Last Session**: 2026-06-09
- **Last Session**: 2026-06-08

## Progress

| Lesson | Title | Status | Date Started | Date Completed | Notes |
|--------|-------|--------|--------------|----------------|-------|
| 1 | What is a Group? | completed | 2026-05-15 | 2026-06-02 | Solid grasp. Asked sharp questions re: binary operation requirement, associativity vs commutativity (grouping vs ordering). All 3 exercises correct; recognized C4 across multiple disguises. |
| 2 | Permutations | completed | 2026-06-04 | 2026-06-04 | Bijection def, $|S_n|=n!$, two-line & cycle notation, disjoint cycles, composition (right-to-left), inverse, cube link ($U=(1234)$). Deep dives: position-vs-label / active-passive; cubing convention clash. All in-chat AND all 5 formal exercises + stretch correct. |
| 3 | Order, Subgroups, Generators | completed | 2026-06-07 | 2026-06-08 | Element order def; proved |τ|=lcm(cycle lengths); group vs element order; $S_n$ degree-vs-order naming; subgroups + subgroup test (+ one-step finite test); cyclic subgroups & generators; all 6 subgroups of $S_3$; coprime-order subgroups intersect trivially. Lagrange hook. All exercises correct. |
| 4 | Parity and Alternating Group | completed | 2026-06-08 | 2026-06-09 | Transpositions ($k$-cycle=$k-1$, bubble-sort insight); parity theorem; sign=Z2(add)≅±1(mult); $A_n$, $|A_n|=n!/2$; $A_3,A_4$. Cube app **corrected**: 三阶 PLL parity (face turn even ⇒ no lone 2-swap); 二阶 has NO position-parity constraint (illegal states = orientation, deferred to L7). Syllabus updated. |
| 5 | Homomorphisms and Isomorphisms | not-started | | | |
| 6 | Direct and Semi-direct Products | not-started | | | |
| 7 | Modeling the 2x2 Cube | not-started | | | |
| 8 | Generators of Pocket Cube Group | not-started | | | |
| 9 | Structure of Pocket Cube Group | not-started | | | |
| 10 | Commutators | not-started | | | |
| 11 | Conjugation | not-started | | | |
| 12 | Building a Solve from Scratch | not-started | | | |
| 13 | Representing States in Code | not-started | | | |
| 14 | Exploring the Group Computationally | not-started | | | |
| 15 | Optimal Solver | not-started | | | |

## Session History

### Session 1 - 2026-05-15
- Assessed learner background: university math, speed cuber, all three goals
- Created syllabus and workspace structure
- Next: begin Lesson 1

### Session 2 - 2026-06-02
- Completed Lesson 1 (What is a Group?)
- Learner Q&A highlights:
  - Clarified group operation must be binary (unary/ternary not group ops, but a unary map like negation can be a group *element* under composition)
  - Deep discussion: associativity = re-grouping (parens) allowed; commutativity = re-ordering, NOT allowed. Corrected an ambiguous phrasing about "which step computed first"
  - Identity is always its own inverse; introduced involutions
- All 3 exercises solved correctly; learner recognized C4 structure across disguises
- Next: Lesson 2 (Permutations)

### Session 3 - 2026-06-02 (evening pause)
- Built **state-externalization system** so any fresh session (after compaction or on another machine) can fully resume: added AGENTS.md (AI bootstrap), README.md, lessons/lesson-01.md archive, .gitignore. Initialized git, pushed to GitHub: git@github.com:shawtung/cube-group-theory-learning.git
- Exercises now archived separately in exercises/ (learner wants to view problems in a standalone tab); going forward, ALWAYS save generated exercises there.
- Lesson 1 deepened via excellent learner questions:
  - **Identity uniqueness** proved (bridge $e\cdot e'$). **Inverse uniqueness** proved by learner ($b = e b = (ca)b = c(ab) = ce = c$), which also shows left inverse = right inverse. Established "algebraic bridging" meta-skill.
  - **associativity vs commutativity** fully resolved: two different "orderings" (operand arrangement A = commutativity; evaluation/time order B = free, guaranteed equal by associativity). "See-through test": copy left-to-right, did sequence change? Multiplication hides the difference (both hold); cube is the clean non-Abelian example. Binary-tree analogy (learner's own).
  - **substitution needs "determinate", not "short name"**: `R·U` is a determinate element, substitutable as $X=R\cdot U$, even without a nice name.
  - **Learner insight**: group elements ↔ cube states are in bijection (simply transitive action), fixing solved as reference. Boundary noted: bijection is element↔state, not sequence↔state.
  - All deep dives archived in lessons/lesson-01.md.
- Status: Lesson 1 fully solid. Paused; will resume Lesson 2 (Permutations) in the evening.

### Session 4 - 2026-06-04 (morning, lunch pause)
- Started **Lesson 2 (Permutations)**. Covered through the active/passive distinction; composition is next.
- Taught: permutation = bijection on $\{1..n\}$; why bijection (cube: each slot exactly one piece); $|S_n|=n!$ (learner linked to $P(4,4)=4!=24$ instantly); two-line & cycle notation; disjoint-cycle decomposition.
- Exercises solved correctly in-chat: two-line→cycle ($(1\,3)(2\,5)$, fixed pt 4); "what's in slot 1 after $(1\,2\,4)$" = blue (learner noted filling a slot reverses the arrow → uses $\sigma^{-1}$).
- **Big conceptual thread (learner-driven):** position-vs-label question led to separating TWO independent switches — ① slot vs label (relabel, no physics change) and ② destination vs source (differs by inverse, changes answer). Learner independently rediscovered **active vs passive transformations**. Correction issued: passive ≠ "moves only some pieces"; active/passive describe the SAME $\sigma$ with identical physical results, differing only in language. Cube turn = active (real motion). All archived in lessons/lesson-02.md.
- Clarified term **scramble** (打乱 / scramble sequence).
- Course convention locked: **numbers = positions; $\sigma(i)=j$ = destination.**
- Next: Lesson 2 Step 3 — composition, left-to-right vs right-to-left convention.

### Session 5 - 2026-06-04 (afternoon)
- **Completed Lesson 2 (Permutations).** Taught composition (right-to-left convention, $\tau\sigma$ = first $\sigma$ then $\tau$; non-Abelian), the cubing-notation convention clash (locked mathematician's right-to-left), inverse (reverse arrows/cycles, $(\tau\sigma)^{-1}=\sigma^{-1}\tau^{-1}$, cycles can start anywhere), and the cube link ($U=(1234)$, position layer = $S_8$, orientation deferred to L7; $U^2=(13)(24)$, $|U|=4$, $\cong C_4$).
- All in-chat exercises correct: $\beta\alpha=(2\,3)$, $\gamma^{-1}=(1\,2\,4\,3)$, $U^2=(13)(24)$ diagonal swap. Learner adopted an efficient whole-row tracking notation.
- Formal exercises archived to exercises/lesson-02-exercises.md (5 Qs + stretch on cycle-length lcm, previewing order).
- **Infra note (carryover):** the agents-lesson-2-start worktree was deleted mid-session (learner merged branch agents/lesson-2-start into master and removed the worktree). Going forward work directly in the MAIN project: /Users/shawn/Study/Group-Cube (branch master). Tooling briefly failed because the session cwd pointed at the deleted worktree; resolved after VS Code restart + switching from the standalone agents window back to the chat plugin.
- Next: Lesson 3 (Order, Subgroups, Generators).

### Session 6 - 2026-06-04 (evening)
- Worked through **all 5 formal Lesson 2 exercises + stretch**, one at a time. Learner answered every part correctly with clean reasoning.
  - Q1: $\pi=(1\,4\,5)(2\,6)$, fixed pt 3. ✓
  - Q2: $ba=(1\,3)(2\,4)$, $ab=(1\,2)(3\,4)$, $\neq$ ⇒ $S_4$ non-Abelian. ✓
  - Q3: $\sigma^{-1}=(3\,5\,2\,4\,1)$; verified $1\to1$. (Noted cycles can start anywhere.) ✓
  - Q4: $(ba)^{-1}=(1\,3)(2\,4)$ both ways. **Learner insight:** reversal $a^{-1}b^{-1}$ is masked here because $ba$ is an involution (=its own inverse).
  - Q5: (a) recognized $M$ moves all 8 corners ⇒ whole-cube rotation ($x$), not a single face turn (which moves only 4). (b) $M^2=(1\,8)(2\,7)(3\,6)(4\,5)$. (c) $|M|=\text{lcm}(4,4)=4$.
  - Stretch: $|(1\,2\,3)(4\,5)|=\text{lcm}(3,2)=6$. Learner already internalized order = lcm of disjoint cycle lengths (previews L3).
- Lesson 2 fully closed. Next: begin Lesson 3 (Order, Subgroups, Generators).

### Session 7 - 2026-06-07/08 (Lesson 3 start)
- Began **Lesson 3 (Order, Subgroups, Generators).**
- **Step 1 — element order:** defined $|g|=$ least $n>0$ with $g^n=e$. Learner confirmed $|U|=4$. Learner's geometric reason ("$U$ rotates a square, $4\times90°=360°$") accepted for $U$; tutor added the *universal* reason: finite state set + invertibility ⇒ the first repeat must return to the start (if $g^a(s)=g^b(s)$ apply $g^{-a}$), so order always exists.
- **Step 2/3 — proved the lcm theorem** (upgraded from L2 conjecture to learner-proved theorem):
  - Block A: a length-$k$ cycle has order exactly $k$ (track element 1 going around the ring; must complete full loops ⇒ min $j=k$). Learner's intuition: "all positions have equal status, complete one loop together."
  - Block B: disjoint cycles commute ⇒ $\tau^j=c_1^j\cdots c_m^j$; all home simultaneously ⇒ $j$ multiple of every $\ell_i$ ⇒ $|\tau|=\operatorname{lcm}(\ell_1,\dots,\ell_m)$. Learner answered $\operatorname{lcm}(3,2)=6$ and wrote the general formula correctly.
  - Stressed the hidden **disjoint** premise (needed for $\tau^j$ to split). Speed-cubing application noted: a PLL = $(abc)(def)$ has order $\operatorname{lcm}(3,3)=3$ → repeat 3× restores.
- **Step 4 — group order vs element order:** clarified two meanings of "order"; $|S_3|=6$, $|S_8|=40320$, $|G_{2x2}|=3{,}674{,}160$. Planted **Lagrange** hook ($|g|\mid|G|$).
- **Pending question (resume here):** asked learner for $|S_4|=24$ and the set of possible element orders in $S_4$ (enumerate disjoint-cycle shapes of 4 points, apply lcm). Learner paused to save progress before answering.
- Next: finish the $S_4$ element-order enumeration, then Step 5 (subgroups + subgroup test) and Step 6 (generators, Cayley graph, Lagrange).

### Session 8 - 2026-06-08 (Lesson 3 complete)
- Synced repo (git pull picked up Session 7 PROGRESS edits from another machine). **Completed Lesson 3.**
- **$S_4$ element orders** (learner correct): partitions $4,3{+}1,2{+}2,2{+}1{+}1,1^4$ → orders $\{1,2,3,4\}$. Tutor caution: equals $\{1..4\}$ only by coincidence; $S_5$ has order-6 element ($3{+}2$); general max = Landau's function. Lagrange double-check (6,8,12,24 don't occur).
- **Subgroups + subgroup test:** definition $H\le G$; two-step test (closure + inverses, assoc inherited, $e$ free); one-step finite test (finite+closed⇒subgroup, reusing "finite⇒cycles" argument). W2 checks correct: $\{e,(1\,2)\}$ yes $\cong C_2$, $\{e,(1\,2\,3)\}$ no (closure fails). Insight: containing order-$n$ element forces all its powers.
- **Generators / cyclic subgroups:** $\langle g\rangle$ size $=|g|$, smallest subgroup containing $g$; $\langle U\rangle\cong C_4$ = the L2-finale convergence now named. $\langle g_1,\dots\rangle$ = smallest subgroup containing all seeds. Endgame: $G_{2\times2}=\langle R,U,F\rangle$.
- **W3** (learner correct): $\langle(1\,2\,3)\rangle$ size 3; $\langle(1\,2\,3),(1\,2)\rangle=S_3$. **Learner self-diagnosed a left-to-right vs right-to-left convention slip** ($ab$ naming) — noted set generated is convention-independent.
- **Q1 (formal, learner correct):** all 6 subgroups of $S_3$ enumerated with sizes/cyclicity; $\langle(1\,2\,3)\rangle=\langle(1\,3\,2)\rangle$; Lagrange completeness check.
- **Learner's 3 insights named:** (1) product of two transpositions = 3-cycle, but they *generate* all $S_3$ (Lagrange: divisible by 2 and 3); (2) order-2 + order-3 seed → $S_3$; (3) deepest — $S_3$ is **not cyclic**, needs ≥2 seeds (cyclic vs non-cyclic watershed; cube highly non-cyclic).
- **Closing (correct):** $\langle(1\,2\,3)\rangle\cap\langle(1\,2)\rangle=\{e\}$; mini-theorem: coprime-order subgroups intersect trivially (recurs at L7 position/orientation split).
- Terminology taught: $\cong$ (isomorphic = same structure, different names; formalized L5); $S_n$ = degree-$n$ symmetric group (degree=points, order=$n!$); trivial subgroups ($\{e\}$ and $G$); proper/nontrivial.
- Archived full content to lessons/lesson-03.md; Q1 solution + closing recorded in exercises/lesson-03-exercises.md.
- Next: **Lesson 4 (Parity and the Alternating Group).**

### Session 9 - 2026-06-08 (Lesson 4 start)
- Began **Lesson 4 (Parity & Alternating Group).** Cube motivation: illegal states (single 2-swap, single edge flip) are unreachable — parity is the invariant.
- **Transpositions:** any perm = product of transpositions; $k$-cycle = $k-1$ transpositions via $(a_1\dots a_k)=(a_1a_2)(a_2a_3)\cdots$. Learner W: $(1\,2\,3\,4)=(1\,2)(2\,3)(3\,4)$ ✓.
  - **Learner's bubble-sort insight:** executing right-to-left = one bubble-sort pass; rightmost element travels left while others shift right one slot. Tutor named two payoffs: (1) adjacent transpositions generate $S_n$; (2) parity = inversion-count parity.
- **Parity theorem:** transposition count's parity is invariant (decomposition not unique, parity is). Even/odd well-defined. Learner classified (a)$(1\,2)$ odd (b)$(1\,2\,3)$ even (c)$(1\,2\,3\,4)$ odd (d)$(1\,3)(2\,4)$ even ✓. Rule: $k$-cycle parity = parity of $k-1$ (even-length cycle = odd perm).
- **Sign / composition rule:** parity adds (count adds). Learner initially mis-stated table (said even×odd=even); corrected via concrete check. **Learner's own insight: "it's addition, not multiplication"** — affirmed: sign = Z2 (even→0, odd→1, add mod 2) $\cong$ ($\{\pm1\},\times)$ via $n\mapsto(-1)^n$. Root cause of slip: hadn't yet accepted the even=+1/odd=−1 encoding. Redid: (a)odd (b)even (c)even (d)$e$=even ✓. Noted $e$ always even; $\sigma,\sigma^{-1}$ same parity.
- **Alternating group $A_n$:** even perms form a subgroup (closure even×even=even, $e$ even, inverses same parity); odd perms do NOT (no $e$, not closed). $|A_n|=n!/2$ (multiply-by-transposition bijection between halves). $A_3=\{e,(123),(132)\}$.
  - **Learner error caught:** first gave $|A_4|=9$, missing the $2+2$ double-transpositions. Corrected to 12 = $1(e)+3(2{+}2)+8(3\text{-cycles})$. Lesson reinforced: use $n!/2$ as anchor + enumerate by cycle shape, cross-check. The 3 double-transpositions $=U^2$-type (even, legal on cube); they + $e$ form Klein $V_4$ (deferred).
  - **Learner found** $(1\,2)(2\,3)=(1\,3)(1\,2)$ (non-unique decomposition, parity preserved ✓). Tutor initially flagged a convention slip but **retracted it** after learner clarified his steps: he rewrote $(1\,2\,3)=(3\,1\,2)$ (same cycle, new start) THEN applied the formula $(a_1a_2a_3)=(a_1a_2)(a_2a_3)$ — fully right-to-left, no error. Confirmed the formula $(abc)=(ab)(bc)$ is itself right-to-left (left-to-right convention would write $(bc)(ab)$).
- **Step 5 (cube interface) STARTED but PAUSED** (learner low on energy). Set up: a face turn on 2x2 corners = 4-cycle = odd permutation; reachable state = product of $k$ face turns. Posed the pending question: **"$k$ odd permutations multiplied — total parity depends on what?"** (answer hinges on parity of $k$). Learner paused before answering.
- **RESUME HERE:** answer the parity-of-$k$ question, then derive why a single 2-swap (odd) is unreachable on the cube / the legal-move parity argument. Then formal exercises + archive lessons/lesson-04.md.

### Session 10 - 2026-06-09 (Lesson 4 complete, with a real correction)
- Resumed Step 5. Learner answered the pending question correctly: **$k$ odd permutations → total parity $=k\bmod 2$.**
- **Tutor made a genuine error and learner caught it.** Tutor's first Step-5 story tried to argue "二阶: a 2-corner swap is illegal" via a vague "conserved quantity" while dodging orientation (untaught). Learner pushed back: the argument was muddled and depended on orientation which isn't learned yet, so it should be deferred. **Tutor conceded — the argument was actually WRONG, not just awkward.**
  - **Correct picture:** 二阶 has NO position-parity constraint (single face turn = one 4-cycle = ODD ⇒ all $8!$ corner arrangements reachable). 二阶's illegal states are **orientation**-based ($\sum o_i\equiv0\bmod3$) → **deferred to Lesson 7**.
  - **The real parity payoff is 三阶 (position only):** face turn = (4-cycle corners)×(4-cycle edges) = odd×odd = EVEN ⇒ every reachable state even ⇒ a lone 2-swap (odd) is unreachable = **PLL parity**; min pure-position move = 3-cycle.
- **Two learner corrections logged:** (1) prefers terminology **二阶/三阶** over 2x2/3x3 (now the course standard). (2) Refuted tutor's claim that corner/edge parity coupling "affects feel" — learner plays 二阶 as the 8 corners of a 三阶 using 三阶 algorithms, so no independent 二阶 feel. Speculation withdrawn.
- **Syllabus updated** (per learner request, to not forget at L7): L4 entry now states the corrected 三阶-PLL-parity payoff + 二阶-no-constraint note; L7 entry carries over "explain 二阶 illegal states via orientation here."
- Archived corrected full content to lessons/lesson-04.md (tutor's wrong argument flagged as corrected); exercises/lesson-04-exercises.md created (Q1 assigned, not yet solved).
- **Meta:** good example of the rigor the learner profile promises — he refuses hand-wavy "conserved quantity" hand-waving and demands the cube application be honest about what's been taught.
- Next: **Lesson 5 (Homomorphisms and Isomorphisms)** — headline example $\operatorname{sgn}:S_n\to\{\pm1\}$ (today's sign), kernel $=A_n$.
