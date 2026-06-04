# Teaching Log & Progress Tracker

## Current Status
- **Current Lesson**: Lesson 2 (Permutations) **COMPLETE**; next up Lesson 3 (Order, Subgroups, Generators)
- **Last Session**: 2026-06-04 (afternoon)

## Progress

| Lesson | Title | Status | Date Started | Date Completed | Notes |
|--------|-------|--------|--------------|----------------|-------|
| 1 | What is a Group? | completed | 2026-05-15 | 2026-06-02 | Solid grasp. Asked sharp questions re: binary operation requirement, associativity vs commutativity (grouping vs ordering). All 3 exercises correct; recognized C4 across multiple disguises. |
| 2 | Permutations | completed | 2026-06-04 | 2026-06-04 | Bijection def, $|S_n|=n!$, two-line & cycle notation, disjoint cycles, composition (right-to-left), inverse, cube link ($U=(1234)$). Deep dives: position-vs-label / active-passive; cubing convention clash. All in-chat exercises correct. |
| 3 | Order, Subgroups, Generators | not-started | | | |
| 4 | Parity and Alternating Group | not-started | | | |
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
- **Infra note:** the agents-lesson-2-start worktree was deleted mid-session (learner merged branch agents/lesson-2-start into master and removed the worktree). Going forward work directly in the MAIN project: /Users/shawn/Study/Group-Cube (branch master). Tooling briefly failed because the session cwd pointed at the deleted worktree; resolved after VS Code restart + switching from the standalone agents window back to the chat plugin.
- Next: Lesson 3 (Order, Subgroups, Generators).
