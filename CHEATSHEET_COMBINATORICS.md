# COMBINATORICS CHEAT SHEET (One Page)

## FUNDAMENTAL COUNTING PRINCIPLES

| Principle | When to Use | Formula |
|-----------|-------------|---------|
| **Product Rule** | Sequential independent tasks | $n_1 \times n_2 \times \cdots \times n_k$ |
| **Sum Rule** | Mutually exclusive alternatives | $n_1 + n_2 + \cdots + n_k$ |

---

## PERMUTATIONS (Order Matters)

| Type | Formula | Example |
|------|---------|---------|
| **n objects, all arranged** | $n!$ | 5 books on shelf: $5! = 120$ |
| **r from n, no repeat** | $P(n,r) = \frac{n!}{(n-r)!}$ | Top 3 from 10: $P(10,3) = 720$ |
| **r from n, with repeat** | $n^r$ | 4-digit PIN: $10^4 = 10000$ |
| **Circular (n distinct)** | $(n-1)!$ | 6 people at table: $5! = 120$ |
| **Multiset** | $\frac{n!}{n_1! \cdot n_2! \cdots n_k!}$ | MISSISSIPPI: $\frac{11!}{1! \cdot 4! \cdot 4! \cdot 2!}$ |

**Key:** Permutations count ORDERED arrangements. If rearranging creates a new outcome, use permutation.

---

## COMBINATIONS (Order Doesn't Matter)

| Type | Formula | Example |
|------|---------|---------|
| **Choose r from n** | $\binom{n}{r} = \frac{n!}{r!(n-r)!}$ | 5-card hand: $\binom{52}{5}$ |
| **With repetition** | $\binom{n+r-1}{r}$ | 10 cookies from 4 types: $\binom{13}{10}$ |

**Properties:**
- $\binom{n}{r} = \binom{n}{n-r}$ (symmetry — use this to simplify!)
- $\binom{n}{0} = \binom{n}{n} = 1$
- $\binom{n}{1} = n$

**Key:** Combinations count UNORDERED selections. Choosing a committee? Use combination.

---

## STARS AND BARS

**Problem type:** Distribute $r$ identical objects into $n$ distinct bins.

**Formula:** $\binom{n+r-1}{r} = \binom{n+r-1}{n-1}$

**Visual:** Place $r$ stars and $n-1$ bars: $***|**|*$ = (3,2,1) distribution

**With constraints:**
- **At least 1 per bin:** Give 1 to each first, then distribute remaining $r-n$:
  $$\binom{(n)+(r-n)-1}{r-n} = \binom{r-1}{r-n} = \binom{r-1}{n-1}$$

**Common mistake:** Using $\binom{n+r}{r}$ instead of $\binom{n+r-1}{r}$. The correct formula has $n+r-1$!

---

## BINOMIAL & MULTINOMIAL

**Binomial Theorem:**
$$(x+y)^n = \sum_{k=0}^{n} \binom{n}{k} x^k y^{n-k}$$

**Coefficient of $x^k y^{n-k}$:** $\binom{n}{k}$

**Multinomial Coefficient:**
$$\binom{n}{n_1, n_2, \ldots, n_k} = \frac{n!}{n_1! \cdot n_2! \cdots n_k!}$$

**Use:** Partition $n$ objects into $k$ labeled groups of sizes $n_1, \ldots, n_k$.

**Important identities:**
- $\sum_{k=0}^{n} \binom{n}{k} = 2^n$ (set $(x,y)=(1,1)$ in binomial theorem)
- Pascal's identity: $\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$

---

## INCLUSION-EXCLUSION PRINCIPLE (PIE)

**Two sets:**
$$|A \cup B| = |A| + |B| - |A \cap B|$$

**Three sets:**
$$|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$$

**General (n sets):**
$$\left|\bigcup_{i=1}^{n} A_i\right| = \sum |A_i| - \sum |A_i \cap A_j| + \sum |A_i \cap A_j \cap A_k| - \cdots + (-1)^{n+1}|A_1 \cap \cdots \cap A_n|$$

**Pattern:** Alternating signs: + singles, - pairs, + triples, - quadruples, ...

**Derangements:** Number of permutations with no fixed points:
$$D_n = n! \sum_{i=0}^{n} \frac{(-1)^i}{i!} \approx \frac{n!}{e}$$

For small $n$: $D_0=1, D_1=0, D_2=1, D_3=2, D_4=9, D_5=44$

---

## PIGEONHOLE PRINCIPLE

**Simple form:** If $n+1$ objects are placed in $n$ boxes, at least one box contains $\geq 2$ objects.

**Generalized form:** If $n$ objects are placed in $k$ boxes, at least one box contains $\geq \lceil n/k \rceil$ objects.

**Use:** Proving existence of collisions, duplicates, or patterns.

---

## URN MODELS (Quick Reference)

|  | **Order Matters** | **Order Doesn't** |
|--|-------------------|-------------------|
| **No Replacement** | $P(n,r) = \frac{n!}{(n-r)!}$ | $\binom{n}{r}$ |
| **With Replacement** | $n^r$ | $\binom{n+r-1}{r}$ |

---

## DECISION FLOWCHART

```
START: Counting problem
   │
   ├─ Order matters?
   │  ├─ YES: Repetition allowed?
   │  │  ├─ YES → n^r
   │  │  └─ NO  → P(n,r)
   │  │
   │  └─ NO: Repetition allowed?
   │     ├─ YES → Stars & bars: C(n+r-1,r)
   │     └─ NO  → C(n,r)
   │
   ├─ Multiple cases (OR)?
   │  └─ Use Sum Rule (add)
   │
   ├─ Sequential stages (AND)?
   │  └─ Use Product Rule (multiply)
   │
   ├─ Union of sets?
   │  └─ Use Inclusion-Exclusion
   │
   └─ Complement easier?
      └─ Total - Complement
```

---

## COMMON PATTERNS & TRICKS

**Pattern 1:** "At least one" → Use complement: Total - None

**Pattern 2:** Distributing into groups
- Groups distinguishable → Multinomial
- Groups identical → Divide by symmetry

**Pattern 3:** Circular arrangements → Fix one position, arrange rest: $(n-1)!$

**Pattern 4:** Selecting teams with constraints
- Build: choose constrained positions first
- Or: subtract forbidden configurations

**Pattern 5:** Repeated letters → Multiset permutation: $\frac{n!}{\prod n_i!}$

---

## QUICK REFERENCE VALUES

| $n$ | $n!$ | $D_n$ (derangements) |
|-----|------|----------------------|
| 0 | 1 | 1 |
| 1 | 1 | 0 |
| 2 | 2 | 1 |
| 3 | 6 | 2 |
| 4 | 24 | 9 |
| 5 | 120 | 44 |
| 6 | 720 | 265 |
| 10 | 3,628,800 | 1,334,961 |

**Useful:** $\binom{52}{5} = 2,598,960$ (poker hands)

