# Teaching Log & Progress Tracker

## Current Status
- **Current Lesson**: Lesson 1 complete (deepened); next up Lesson 2 (Permutations)
- **Last Session**: 2026-06-02 (evening pause)

## Progress

| Lesson | Title | Status | Date Started | Date Completed | Notes |
|--------|-------|--------|--------------|----------------|-------|
| 1 | What is a Group? | completed | 2026-05-15 | 2026-06-02 | Solid grasp. Asked sharp questions re: binary operation requirement, associativity vs commutativity (grouping vs ordering). All 3 exercises correct; recognized C4 across multiple disguises. |
| 2 | Permutations | not-started | | | |
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
