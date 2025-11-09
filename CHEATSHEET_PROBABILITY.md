# PROBABILITY CHEAT SHEET (One Page)

## KOLMOGOROV AXIOMS

1. **Non-negativity:** $P(A) \geq 0$ for all events $A$
2. **Normalization:** $P(\Omega) = 1$
3. **Additivity:** For disjoint events $A_1, A_2, \ldots$:
   $$P(A_1 \cup A_2 \cup \cdots) = P(A_1) + P(A_2) + \cdots$$

**All probability theory derives from these three axioms.**

---

## BASIC PROPERTIES

| Property | Formula |
|----------|---------|
| **Complement** | $P(A^c) = 1 - P(A)$ |
| **Impossible event** | $P(\emptyset) = 0$ |
| **Subset monotonicity** | If $A \subseteq B$ then $P(A) \leq P(B)$ |
| **Addition (2 events)** | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ |
| **Addition (3 events)** | $P(A \cup B \cup C) = P(A) + P(B) + P(C)$ <br> $\quad - P(A \cap B) - P(A \cap C) - P(B \cap C)$ <br> $\quad + P(A \cap B \cap C)$ |
| **Difference** | If $A \subseteq B$: $P(B \setminus A) = P(B) - P(A)$ |

---

## BOUNDS & INEQUALITIES

| Inequality | Formula | Use |
|------------|---------|-----|
| **Union Bound (Boole)** | $P(A_1 \cup \cdots \cup A_n) \leq \sum_{i=1}^{n} P(A_i)$ | Upper bound on union |
| **Bonferroni (intersection)** | $P(A \cap B) \geq P(A) + P(B) - 1$ | Lower bound on intersection |
| **Range of intersection** | $\max(0, P(A)+P(B)-1) \leq P(A \cap B)$ <br> $\quad \leq \min(P(A), P(B))$ | Min/max bounds |

---

## UNIFORM PROBABILITY MODEL

**When:** All outcomes equally likely (dice, cards, fair coins, etc.)

**Formula:**
$$P(A) = \frac{|A|}{|\Omega|} = \frac{\text{\# favorable outcomes}}{\text{\# total outcomes}}$$

**Key:** This converts probability to counting! Use combinatorics.

---

## CONDITIONAL PROBABILITY

**Definition:**
$$P(A|B) = \frac{P(A \cap B)}{P(B)} \quad \text{for } P(B) > 0$$

**Interpretation:** Probability of $A$ given that $B$ occurred (restrict to $B$'s universe).

**Multiplication Rule (Product Rule):**
$$P(A \cap B) = P(B) \cdot P(A|B) = P(A) \cdot P(B|A)$$

**Chain Rule (n events):**
$$P(A_1 \cap A_2 \cap \cdots \cap A_n) = P(A_1) \cdot P(A_2|A_1) \cdot P(A_3|A_1 \cap A_2) \cdots$$

**WARNING:** $P(A|B) \neq P(B|A)$ in general! Use Bayes to swap.

---

## LAW OF TOTAL PROBABILITY (LOTP)

**Setup:** Events $B_1, B_2, \ldots, B_n$ partition $\Omega$ (disjoint and exhaustive).

**Formula:**
$$P(A) = \sum_{i=1}^{n} P(A|B_i) \cdot P(B_i)$$

**Most common (2 cases):**
$$P(A) = P(A|B) \cdot P(B) + P(A|B^c) \cdot P(B^c)$$

**Use:** When you can't compute $P(A)$ directly, break into scenarios.

**Visualization:** Weighted average over partition.

---

## BAYES' THEOREM

**Formula (2 events):**
$$P(B|A) = \frac{P(A|B) \cdot P(B)}{P(A)}$$

**Expanded form:**
$$P(B|A) = \frac{P(A|B) \cdot P(B)}{P(A|B) \cdot P(B) + P(A|B^c) \cdot P(B^c)}$$

**General form (partition $B_1, \ldots, B_n$):**
$$P(B_i|A) = \frac{P(A|B_i) \cdot P(B_i)}{\sum_{j=1}^{n} P(A|B_j) \cdot P(B_j)}$$

**Terminology:**
- $P(B)$ = **prior** (before seeing evidence)
- $P(A|B)$ = **likelihood** (probability of evidence given hypothesis)
- $P(B|A)$ = **posterior** (updated belief after evidence)

**Use:** Flipping conditionals, diagnostic reasoning, updating beliefs.

---

## INDEPENDENCE

**Definition (2 events):**
Events $A$ and $B$ are independent if:
$$P(A \cap B) = P(A) \cdot P(B)$$

**Equivalent conditions (when $P(B) > 0$):**
- $P(A|B) = P(A)$
- $P(B|A) = P(B)$

**Complement properties:** If $A$ and $B$ independent, then so are:
- $A$ and $B^c$
- $A^c$ and $B$
- $A^c$ and $B^c$

**Mutual Independence (n events):**
Events $A_1, \ldots, A_n$ are mutually independent if for EVERY subset $I \subseteq \{1, \ldots, n\}$:
$$P\left(\bigcap_{i \in I} A_i\right) = \prod_{i \in I} P(A_i)$$

**For n=3:** Requires 4 conditions (3 pairwise + 1 triple).

**Pairwise ≠ Mutual:** Pairwise independence doesn't imply mutual independence!

**KEY DISTINCTION:**
- **Disjoint** (mutually exclusive): $A \cap B = \emptyset$
  - If $P(A), P(B) > 0$: these are DEPENDENT
  - Knowing $A$ occurred means $B$ cannot: $P(B|A) = 0$
- **Independent**: $P(A \cap B) = P(A) P(B)$
  - Knowing $A$ occurred doesn't affect $B$: $P(B|A) = P(B)$

---

## PROBABILITY TREES

**Structure:**
- Nodes = states/events
- Branches = transitions with conditional probabilities
- Probabilities on branches sum to 1 from each node

**Reading the tree:**
- **Path probability:** Multiply along branches
- **Total probability of event:** Add probabilities of all paths leading to that event

**Example:**
```
         Start
         /    \
     [0.6]    [0.4]
       A        B
      / \      / \
  [0.7][0.3][0.9][0.1]
    C   C^c  C  C^c
```
$P(C) = 0.6 \times 0.7 + 0.4 \times 0.9 = 0.42 + 0.36 = 0.78$

---

## COMMON EXAM TEMPLATES

### Template 1: At Least One (Independent Trials)
**Problem:** Probability of at least one success in $n$ independent trials, each with probability $p$.

**Solution:**
$$P(\text{at least one}) = 1 - P(\text{none}) = 1 - (1-p)^n$$

---

### Template 2: Birthday Problem
**Problem:** $n$ people, 365 days. Probability at least 2 share birthday?

**Solution:**
$$P(\text{collision}) = 1 - \frac{365 \times 364 \times \cdots \times (365-n+1)}{365^n} = 1 - \frac{P(365,n)}{365^n}$$

**For n=23:** $P \approx 0.507$ (over 50%!)

---

### Template 3: Disease Testing
**Given:** Prevalence $P(D)$, sensitivity $P(+|D)$, specificity $P(-|D^c)$

**Want:** $P(D|+)$ (posterior if positive)

**Solution (Bayes):**
$$P(D|+) = \frac{P(+|D) P(D)}{P(+|D) P(D) + P(+|D^c) P(D^c)}$$

where $P(+|D^c) = 1 - P(-|D^c)$ (false positive rate).

---

### Template 4: System Reliability

**Series (all must work):**
$$P(\text{system works}) = \prod_{i=1}^{n} P(C_i \text{ works})$$

**Parallel (at least one must work):**
$$P(\text{system works}) = 1 - \prod_{i=1}^{n} P(C_i \text{ fails}) = 1 - \prod_{i=1}^{n} (1 - p_i)$$

---

### Template 5: Urn Problems
**Without replacement:** Use conditional probabilities; each draw changes the composition.

**With replacement:** Independence; probabilities stay constant.

---

## QUICK DECISION TREE

```
Given a probability problem:
│
├─ Are all outcomes equally likely?
│  ├─ YES → Uniform model: P(A) = |A|/|Ω| (use counting!)
│  └─ NO  → Use axioms/formulas below
│
├─ Does it say "given" or "if"?
│  └─ YES → Conditional probability: P(A|B) = P(A∩B)/P(B)
│
├─ Want P(cause|effect) but have P(effect|cause)?
│  └─ YES → Use Bayes' theorem
│
├─ Can't compute P(A) directly but can partition?
│  └─ YES → Use Law of Total Probability
│
├─ Events independent?
│  ├─ Check: Does P(A∩B) = P(A)·P(B)?
│  └─ If YES → Can multiply probabilities
│
├─ "At least one" in problem?
│  └─ YES → Use complement: 1 - P(none)
│
└─ Multiple stages/sequential?
   └─ YES → Draw probability tree, use chain rule
```

---

## CRITICAL WARNINGS

⚠️ **$P(A|B) \neq P(B|A)$** — Don't confuse these!

⚠️ **Disjoint ≠ Independent** — These are opposite concepts (usually)

⚠️ **Independence must be verified** — Don't assume; check the definition

⚠️ **LOTP denominator in Bayes** — Don't forget to compute $P(A)$ properly

⚠️ **Complement of "at least 1" is "0"** — Not "at most 1"

⚠️ **Without replacement ≠ with replacement** — Probabilities change!

---

## USEFUL FORMULAS

**Expected coverage:** For finite sample space with $n$ equally likely outcomes:
$$P(A) = \frac{\text{count favorable}}{\text{count total}}$$

**Quick probability check:** Always verify $0 \leq P(A) \leq 1$

**Number of subsets:** A set with $n$ elements has $2^n$ subsets (including $\emptyset$ and itself)

