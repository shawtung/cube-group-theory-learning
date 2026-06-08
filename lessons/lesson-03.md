# Lesson 3: Order, Subgroups, Generators (阶、子群、生成元)

> Archived full content of Lesson 3 (COMPLETE 2026-06-08). Element order -> subgroups + subgroup test -> generators / cyclic subgroups -> all subgroups of $S_3$. Convention (locked): numbers = positions; $\sigma(i)=j$ = destination; composition right-to-left ($ab$ = first $b$ then $a$).

## Step 1: Order of an element (元素的阶)

**Intuition (cuber):** repeat the same move; after how many repetitions back to start?
- $U$: 4 turns of a face restore -> $|U|=4$.
- $U^2$ (diagonal swap): twice -> $|U^2|=2$.
- sexy move $RUR'U'$: cubers know 6 repeats restore -> order 6.

**Definition:** the **order** of $g\in G$, written $|g|$ or $\operatorname{ord}(g)$, is the **least positive integer** $n$ with $g^n=e$. If none exists, order is **infinite**.

Key facts:
- $|e|=1$.
- order-2 elements = **involutions** ($g=g^{-1}$).
- In a **finite** group every element has finite order.

**Universal reason order exists (finite case):** finite state set + invertibility. The sequence $g,g^2,g^3,\dots$ cannot avoid repeating; if $g^a(s)=g^b(s)$ apply $g^{-a}$ to force a return to start. (Same "finite ⇒ must cycle" argument reused later for the one-step subgroup test.) Learner's geometric reason for $U$ specifically ("rotating a square, $4\times90°=360°$") accepted, then generalized.

⚠️ Notation clash: $|g|$ (element order) vs $|G|$ (group order / size) share $|\cdot|$.

## Step 2/3: Order = lcm of disjoint cycle lengths (learner-proved theorem)

Upgraded from a Lesson-2 conjecture to a proved theorem.

**Block A — a length-$k$ cycle has order exactly $k$.** Track element 1 going around the ring; it returns home only after complete loops, so the least $j$ with $c^j=e$ is $k$. (Learner: "all positions have equal status, complete one loop together.")

**Block B — disjoint cycles commute** ⇒ for $\tau=c_1c_2\cdots c_m$ (disjoint), $\tau^j=c_1^j c_2^j\cdots c_m^j$. All cycles home simultaneously ⇔ $j$ is a multiple of every $\ell_i$ ⇒
$$|\tau|=\operatorname{lcm}(\ell_1,\dots,\ell_m).$$
Hidden premise stressed: **disjoint** (needed so $\tau^j$ splits factor-by-factor).

Cubing application: a PLL of shape $(abc)(def)$ has order $\operatorname{lcm}(3,3)=3$ → repeat 3× restores.

## Step 4: Group order vs element order

Two meanings of "order":
- **element order** $|g|$;
- **group order** $|G|$ = number of elements.

Examples: $|S_3|=6$, $|S_4|=24$, $|S_8|=40320$, $|G_{2\times2}|=3{,}674{,}160$.

**Lagrange hook planted:** $|g|$ divides $|G|$ (proved in a later lesson). Caution noted: Lagrange only forces "order divides $|G|$"; it does NOT promise every divisor occurs.

**Terminology — naming $S_n$:** $S_n$ = **symmetric group of degree $n$** (on $n$ letters). The "$n$" is the **degree** (number of points permuted), NOT the size. $S_4$: degree $4$, order $4!=24$. Both "degree-4 symmetric group" and "order-24 group" are correct but refer to different quantities. "Symmetric" = totally symmetric in the $n$ objects (all points equal status).

### Warm-up W1: possible element orders in $S_4$ (learner correct)
Enumerate cycle shapes (integer partitions of 4), apply lcm:

| shape | lcm | order |
|-------|-----|-------|
| $4$ | $\operatorname{lcm}(4)$ | 4 |
| $3+1$ | $\operatorname{lcm}(3,1)$ | 3 |
| $2+2$ | $\operatorname{lcm}(2,2)$ | 2 |
| $2+1+1$ | $\operatorname{lcm}(2,1,1)$ | 2 |
| $1+1+1+1$ | $1$ | 1 |

Set of element orders in $S_4 = \{1,2,3,4\}$.
**Caution issued:** this equals $\{1,\dots,4\}$ only by coincidence. $S_5$ already breaks it ($3+2 \Rightarrow \operatorname{lcm}(3,2)=6 > 5$). General truth: orders in $S_n$ = all lcms of integer partitions of $n$ (max value = **Landau's function** $g(n)$); neither $\{1,\dots,n\}$ nor bounded by $n$. Lagrange double-check: each of $1,2,3,4$ divides 24, but divisors 6,8,12,24 do NOT occur.

## Step 5: Subgroups (子群)

**Intuition:** restricting to only $U$ in the cube reaches $\{e,U,U^2,U^3\}$ — a self-contained group living inside $G$.

**Definition:** non-empty $H\subseteq G$ is a **subgroup** ($H\le G$) if $H$ is itself a group under $G$'s operation.

### Subgroup test
Associativity is inherited from $G$ (free). So only check:
1. **Closure:** $\forall a,b\in H,\ ab\in H$;
2. **Inverses:** $\forall a\in H,\ a^{-1}\in H$.

Identity comes free: pick $a\in H$, get $a^{-1}\in H$ (2), then $aa^{-1}=e\in H$ (1).

**One-step test (finite groups):** a non-empty *finite* subset closed under the operation is automatically a subgroup (closure + finiteness ⇒ $a,a^2,\dots$ cycles back to $e$, so $a^{k-1}=a^{-1}$). Reuse of the "finite ⇒ must cycle" argument.

### Warm-up W2 (learner correct)
- $\{e,(1\,2)\}$: subgroup ($(1\,2)^2=e$, self-inverse) $\cong C_2$. ✓
- $\{e,(1\,2\,3)\}$: NOT a subgroup; closure fails ($(1\,2\,3)^2=(1\,3\,2)\notin$ set). ✓
- **Insight:** to contain an order-$n$ element $g$, a subgroup must contain ALL of $g,g^2,\dots,g^{n-1},e$. $(1\,2)$ works because order 2 → only $g,e$ needed.

## Step 6: Generators & cyclic subgroups (生成元)

**Cyclic subgroup:** $\langle g\rangle = \{\dots,g^{-1},e,g,g^2,\dots\}$ = all integer powers of $g$. In a finite group $\langle g\rangle=\{e,g,\dots,g^{|g|-1\}}$, size $=|g|$. It is the **smallest subgroup containing $g$**.
- $\langle U\rangle=\{e,U,U^2,U^3\}\cong C_4$ — the Lesson-2-finale convergence (permutation / cube / cyclic group are one object), now formally named.

**Multiple generators:** $\langle g_1,\dots,g_k\rangle$ = all finite products of the $g_i$ and their inverses = **smallest subgroup containing all $g_i$**.

**Course endgame:** $G_{2\times2}=\langle R,U,F\rangle$ (even $\langle R,U\rangle$ suffices for 2×2). Solving = writing a target state as a product of these generators. (Formalized in Lesson 8.)

### Warm-up W3 — generators in $S_3$ (learner correct)
$a=(1\,2\,3),\ b=(1\,2)$.
- (a) $\langle a\rangle=\{e,(1\,2\,3),(1\,3\,2)\}$, size $3 = |a|$ (cyclic subgroup size = generator's order).
- (b) $\langle a,b\rangle = S_3$ (all 6 elements). Two seeds (a 3-cycle + a transposition) generate everything.
- **Convention catch (learner self-diagnosed):** learner computed left-to-right, getting $ab=(2\,3),a^2b=(1\,3)$. Right-to-left (course convention) gives $ab=(1\,3),a^2b=(2\,3)$. Changing convention only relabels *which product is which name*; the generated **set** is unchanged ($=S_3$ either way).

## Q1 (formal): all subgroups of $S_3$ (learner correct)

$S_3=\{e,(1\,2),(1\,3),(2\,3),(1\,2\,3),(1\,3\,2)\}$, $|S_3|=6$. There are **6 subgroups**:

| subgroup | elements | size | cyclic? generator |
|----------|----------|------|-------------------|
| $\{e\}$ | $e$ | 1 | trivial |
| $\langle(1\,2)\rangle$ | $e,(1\,2)$ | 2 | yes, $(1\,2)$ |
| $\langle(1\,3)\rangle$ | $e,(1\,3)$ | 2 | yes, $(1\,3)$ |
| $\langle(2\,3)\rangle$ | $e,(2\,3)$ | 2 | yes, $(2\,3)$ |
| $\langle(1\,2\,3)\rangle$ | $e,(1\,2\,3),(1\,3\,2)$ | 3 | yes, $(1\,2\,3)$ |
| $S_3$ | all 6 | 6 | **NO** (not cyclic) |

Note $\langle(1\,2\,3)\rangle=\langle(1\,3\,2)\rangle$ (same 3-subgroup, two generators). 5 non-$e$ elements → only 4 distinct cyclic subgroups. Lagrange check: sizes $\{1,2,2,2,3,6\}$ all divide 6 ✓, only divisors $1,2,3,6$ appear ⇒ list is complete.

### Learner's three insights (named)
1. "Mixing two order-2 generators gives the order-3 subgroup" — refined: the **product** of two distinct transpositions is a 3-cycle (verified $(1\,2)(1\,3)=(1\,3\,2)$ right-to-left), but the **generated subgroup** $\langle(1\,2),(1\,3)\rangle$ is all of $S_3$ (size divisible by both 2 and 3 ⇒ $\ge 6$). "Generate" packs more than a single product.
2. "Order-2 generator + order-3 generator gives $S_3$" — correct; same Lagrange argument (size divisible by 2 and 3 ⇒ $S_3$). Matches W3(b).
3. (Deepest) $S_3$ is **not cyclic** — no single element generates it (largest cyclic subgroup is order 3). Needs ≥2 seeds. Watershed: cyclic (one seed) vs non-cyclic (multiple seeds). $G_{2\times2}$ is highly non-cyclic.

## Closing exercise: containment & intersection (learner correct)

$\langle(1\,2\,3)\rangle\cap\langle(1\,2)\rangle=\{e\}$; mutually non-containing.
- Intersection of two subgroups is itself a subgroup.
- Here $|H|$ divides both 3 and 2 ⇒ divides $\gcd(3,2)=1$ ⇒ $H=\{e\}$.
- **Mini-theorem:** subgroups of **coprime** orders intersect trivially. Recurs in cube analysis (position vs orientation split, Lesson 7).

## Lesson 3 knowledge map
| Concept | Key point |
|---------|-----------|
| Element order | $|g|$ = least $n>0$ with $g^n=e$; finite group ⇒ finite order |
| Order theorem | $|\tau|=\operatorname{lcm}$ of disjoint cycle lengths (single cycle order = length) |
| Group vs element order | $|G|$ = size; $|g|$ = element order; share $|\cdot|$ |
| $S_n$ naming | degree $n$ (points), order $n!$ |
| Subgroup | $H\le G$ self-contained; test = closure + inverses (assoc. inherited) |
| One-step test | finite + closed ⇒ subgroup |
| Cyclic subgroup | $\langle g\rangle$, size $=|g|$, smallest subgroup containing $g$ |
| Generators | $\langle g_1,\dots\rangle$ = all products; smallest subgroup containing them |
| Lagrange (hook) | $|H|\mid|G|$; coprime subgroups ⇒ intersect in $\{e\}$ |
| Cube link | $\langle U\rangle\cong C_4$; $G_{2\times2}=\langle R,U,F\rangle$ |

## Next lesson
**Lesson 4: Parity and the Alternating Group.** Even/odd permutations, the sign homomorphism, $A_n$ (alternating group) as an index-2 subgroup — toward which scrambles are reachable on the cube.
