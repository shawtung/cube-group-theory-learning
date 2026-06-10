# Lesson 5 Practice — Homomorphisms & Isomorphisms (同态与同构)

> For digesting the jump in abstraction. Part A = worked examples (read & verify). Part B = exercises (try yourself). Convention reminder: a homomorphism $\varphi:(G,\cdot)\to(H,*)$ satisfies $\varphi(a\cdot b)=\varphi(a)*\varphi(b)$. Isomorphism = bijective homomorphism. $G\cong H$ means "there exists an isomorphism map between them."

Core checklist for "is $\varphi$ a homomorphism?":
1. Identify the operation in **each** group (they can differ: $+$, $\times$, composition, mod-add...).
2. Check $\varphi(a \cdot_G b) = \varphi(a) \cdot_H \varphi(b)$ for all $a,b$.
3. For isomorphism, additionally check **bijective** (injective + surjective).

---

## Part A — Worked examples (read, then verify each yourself)

### A1. Doubling: $\varphi:\mathbb{Z}\to\mathbb{Z}$, $\varphi(n)=2n$  (the in-chat warm-up)
- Both groups under $+$.
- Homo? $\varphi(a+b)=2(a+b)=2a+2b=\varphi(a)+\varphi(b)$ ✓.
- Injective (different $n$ → different $2n$) but NOT surjective (never hits odd numbers).
- **Verdict:** homomorphism, not an isomorphism. *Lesson: homo is weaker than iso.*

### A2. Exponential: $\exp:(\mathbb{R},+)\to(\mathbb{R}_{>0},\times)$, $x\mapsto e^x$
- Domain operation $+$, codomain operation $\times$ — **different operations** (this is the point).
- Homo? $e^{x+y}=e^x\cdot e^y$ ✓ — the classic "turns addition into multiplication."
- Bijective onto positive reals; inverse is $\ln$.
- **Verdict:** isomorphism. $(\mathbb{R},+)\cong(\mathbb{R}_{>0},\times)$. *This is literally why log tables / slide rules work: multiplication becomes addition.*

### A3. Sign: $\operatorname{sgn}:S_n\to(\{+1,-1\},\times)$  (Lesson 4's star)
- Homo? $\operatorname{sgn}(\tau\sigma)=\operatorname{sgn}(\tau)\operatorname{sgn}(\sigma)$ ✓ (parity adds → sign multiplies).
- Surjective (for $n\ge2$: $e\mapsto+1$, any transposition $\mapsto-1$); NOT injective (collapses $n!$ perms to 2 values).
- **Verdict:** homomorphism, not iso. Its "fiber over $+1$" = even permutations = $A_n$ (this is the **kernel**, next lesson).

### A4. Determinant: $\det:GL_2(\mathbb{R})\to(\mathbb{R}^{\times},\times)$
- $GL_2$ = invertible $2\times2$ matrices under matrix multiplication; codomain = nonzero reals under $\times$.
- Homo? $\det(AB)=\det(A)\det(B)$ ✓ — a theorem you already know from linear algebra, now reread as "det is a homomorphism."
- Not injective (many matrices share a determinant).
- **Verdict:** homomorphism. *Familiar linear-algebra fact = a group homomorphism in disguise.*

### A5. Reduction mod n: $\varphi:(\mathbb{Z},+)\to(\mathbb{Z}_n,+)$, $k\mapsto k \bmod n$
- Homo? $(a+b)\bmod n = (a\bmod n)+(b\bmod n)$ in $\mathbb{Z}_n$ ✓.
- Surjective, not injective (all multiples of $n$ map to $0$).
- **Verdict:** homomorphism. *Clock arithmetic: collapsing $\mathbb{Z}$ onto a finite cycle. The set mapping to $0$ = multiples of $n$ = kernel.*

### A6. A $C_4$ automorphism: $\varphi:C_4\to C_4$, $U\mapsto U^3$  (in-chat)
- Shorthand for $U^k\mapsto U^{3k}$: $e\mapsto e,\ U\mapsto U^3,\ U^2\mapsto U^2,\ U^3\mapsto U$.
- Homo (determined by generator image) + bijective → **automorphism** (iso to itself, not the identity).
- *Even though $C_4\cong C_4$ trivially, $C_4$ has a nontrivial self-symmetry. Seeds $\operatorname{Aut}(G)$.*

### A7. A NON-example: $\varphi:(\mathbb{Z},+)\to(\mathbb{Z},+)$, $\varphi(n)=n+1$
- Homo? $\varphi(a+b)=a+b+1$, but $\varphi(a)+\varphi(b)=(a+1)+(b+1)=a+b+2$. $a+b+1\ne a+b+2$. ✗
- **Verdict:** NOT a homomorphism. *Key tell: a homomorphism must send identity to identity, $\varphi(0)=0$; here $\varphi(0)=1$. Any map with $\varphi(e_G)\ne e_H$ is automatically not a homo — a fast rejection test.*

### A8. A NON-example: $\varphi:(\mathbb{R},+)\to(\mathbb{R},+)$, $\varphi(x)=x^2$
- $\varphi(a+b)=(a+b)^2=a^2+2ab+b^2$ vs $\varphi(a)+\varphi(b)=a^2+b^2$. Differ by $2ab$. ✗
- **Verdict:** not a homo. *Squaring doesn't respect additive structure.*

---

## Part B — Exercises (try these; we'll review tomorrow)

**B1.** Is $\varphi:(\mathbb{Z},+)\to(\mathbb{Z},+)$, $\varphi(n)=3n$ a homomorphism? Injective? Surjective? Iso?

**B2.** Is $\varphi:(\mathbb{Z},+)\to(\mathbb{Z},+)$, $\varphi(n)=0$ (everything to 0) a homomorphism? (The "trivial homomorphism".) What does it lose?

**B3.** Fast-reject test: which of these *cannot* be homomorphisms just by checking where the identity goes?
  (a) $\varphi:(\mathbb{Z},+)\to(\mathbb{Z},+),\ \varphi(n)=n+5$
  (b) $\varphi:(\mathbb{R}_{>0},\times)\to(\mathbb{R},+),\ \varphi(x)=\ln x$
  (c) $\varphi:(\mathbb{Z},+)\to(\mathbb{Z}_5,+),\ \varphi(k)=(k+1)\bmod 5$

**B4.** Define $\varphi:C_4\to C_4$ by the generator image $U\mapsto U^2$. Write out all four values $\varphi(e),\varphi(U),\varphi(U^2),\varphi(U^3)$. Is $\varphi$ injective? Is it an isomorphism? (Compare with A6 where $U\mapsto U^3$.)

**B5.** Consider $C_4=\{e,U,U^2,U^3\}$ and the Klein four-group $V_4=\{e,a,b,c\}$ where every non-identity element has order 2 ($a^2=b^2=c^2=e$). Both have 4 elements. Are they isomorphic? (Hint: compare element orders — does $V_4$ have an element of order 4? Can an isomorphism send an order-4 element to something of different order?)

**B6.** (Stretch) How many isomorphisms are there from $C_4$ to itself (automorphisms)? List each by where it sends the generator $U$, and check which generator-images actually give a bijection. (Hint: $U\mapsto U^k$ is an automorphism iff $U^k$ is itself a generator of $C_4$.)

**B7.** (Cube preview) The map "take only the corner **position** permutation, ignore orientation" sends a cube move to an element of $S_8$. Argue informally why this is a homomorphism from the cube group to $S_8$. (What does "do move $A$ then move $B$, then read off positions" equal?)

---

### Answers / discussion: bring your attempts tomorrow; we'll go through B1–B7, then move on to **kernel & image** (where $\ker(\operatorname{sgn}) = A_n$ reappears).
