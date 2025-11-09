# PART II: PROBABILITY AXIOMS

## ESSENTIALS ONLY - TL;DR (Probability Axioms)

### Core Formulas (Memorize These)

1. **Sample space:** $\Omega$ = set of all possible outcomes

2. **Event:** $A \subseteq \Omega$

3. **Kolmogorov Axioms:**
   - A1: $P(A) \geq 0$ for all events $A$
   - A2: $P(\Omega) = 1$
   - A3: For disjoint events $A_1, A_2, \ldots$: $P(A_1 \cup A_2 \cup \cdots) = P(A_1) + P(A_2) + \cdots$

4. **Complement rule:** $P(A^c) = 1 - P(A)$

5. **Addition rule (general):** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

6. **Monotonicity:** If $A \subseteq B$ then $P(A) \leq P(B)$

7. **Probability of impossible event:** $P(\emptyset) = 0$

8. **Difference rule:** $P(B \setminus A) = P(B) - P(A \cap B)$ if $A \subseteq B$

9. **Union bound (Boole's inequality):** $P(A_1 \cup A_2 \cup \cdots \cup A_n) \leq P(A_1) + P(A_2) + \cdots + P(A_n)$

10. **Bonferroni inequalities:**
    - $P(A \cap B) \geq P(A) + P(B) - 1$
    - $P(A \cup B) \leq \min(1, P(A) + P(B))$

11. **Uniform probability (equally likely):** $P(A) = \frac{|A|}{|\Omega|}$

### 8 Exam Templates

| # | Pattern | Solution Skeleton |
|---|---------|-------------------|
| 1 | "At least one..." | Use complement: $P(\text{at least 1}) = 1 - P(\text{none})$ |
| 2 | "Find $P(A)$ when outcomes equally likely" | Count: $P(A) = \frac{|A|}{|\Omega|}$ |
| 3 | "Given $P(A)$, find $P(A^c)$" | $P(A^c) = 1 - P(A)$ |
| 4 | "$P(A \cup B)$ given $P(A), P(B), P(A \cap B)$" | Addition rule |
| 5 | "Two events $A, B$ where $P(A)=p, P(B)=q$ given" | Draw Venn diagram, use $P(A \cup B) \leq p+q$ |
| 6 | "Show $P(E) \leq$ some bound" | Use union bound or monotonicity |
| 7 | "Card/dice/coin problem with symmetry" | Uniform model: count favorable/total |
| 8 | "Prove probability property from axioms" | Start with axioms, derive step-by-step |

### 5 Mnemonics & Pitfalls

**Mnemonics:**
1. **"Axioms: Non-negative, Total=1, Disjoint=Add"** - The three Kolmogorov axioms
2. **"Complement catches at-least-one"** - $P(\geq 1) = 1 - P(0)$ is almost always easier
3. **"Add then subtract overlap"** - Inclusion-exclusion for unions
4. **"Equally likely = counting"** - Uniform model links probability to combinatorics
5. **"Subset → smaller probability"** - Monotonicity intuition

**Pitfalls:**
1. **$P(A \cup B) \neq P(A) + P(B)$** unless disjoint; must subtract $P(A \cap B)$
2. **$P(A \cap B) \neq P(A) \cdot P(B)$** unless independent (covered later)
3. **Complement of "at least one" is "none"**, not "at most one"
4. **$P(\emptyset) = 0$ but $P(A) = 0$ doesn't mean $A = \emptyset$** (in infinite spaces)
5. **Union bound gives upper bound, not exact value** - equality only if disjoint

---

## 9. SAMPLE SPACES & EVENTS

### Intuition
The sample space is your universe of possibilities. Events are the outcomes you care about. Probability assigns a number between 0 and 1 to each event, measuring "how likely" it is to occur. Think of events as subsets; set operations (union, intersection, complement) correspond to logical operations (OR, AND, NOT).

### Formal Definitions

**Sample Space ($\Omega$):** The set of all possible outcomes of an experiment.

**Outcome:** A single element $\omega \in \Omega$ (also called a sample point).

**Event:** A subset $A \subseteq \Omega$.
- **Simple event:** An event containing exactly one outcome
- **Compound event:** An event containing multiple outcomes

**Event Algebra (Set Operations):**
- **Union** $A \cup B$: "$A$ OR $B$" (at least one occurs)
- **Intersection** $A \cap B$: "$A$ AND $B$" (both occur)
- **Complement** $A^c$: "NOT $A$" (all outcomes not in $A$)
- **Difference** $A \setminus B = A \cap B^c$: "$A$ but not $B$"
- **Disjoint/Mutually Exclusive:** $A \cap B = \emptyset$

**De Morgan's Laws:**
- $(A \cup B)^c = A^c \cap B^c$
- $(A \cap B)^c = A^c \cup B^c$

---

### WORKED EXAMPLE 1 (Easy): Coin Flips

**Problem:** An experiment consists of flipping a coin three times. Define the sample space and the event "exactly two heads."

**Key idea:** List all outcomes systematically; event is a subset.

**Step 1:** List sample space.
Each outcome is a sequence of 3 flips:
$$\Omega = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}$$
$$|\Omega| = 8$$

**Step 2:** Define the event.
Let $A$ = "exactly two heads"
$$A = \{HHT, HTH, THH\}$$
$$|A| = 3$$

**Answer:** $\Omega$ has 8 outcomes; $A = \{HHT, HTH, THH\}$ with $|A| = 3$.

---

### WORKED EXAMPLE 2 (Exam-Style): Event Algebra

**Problem:** A die is rolled. Let $A$ = "roll is even" = {2,4,6}, $B$ = "roll is at most 3" = {1,2,3}. Find:
(a) $A \cup B$
(b) $A \cap B$
(c) $A^c$
(d) $A \setminus B$

**Key idea:** Use set operations on the event sets.

**Step 1:** Sample space.
$$\Omega = \{1,2,3,4,5,6\}$$

**Step 2:** Find $A \cup B$ (even OR at most 3).
$$A \cup B = \{2,4,6\} \cup \{1,2,3\} = \{1,2,3,4,6\}$$

**Step 3:** Find $A \cap B$ (even AND at most 3).
$$A \cap B = \{2,4,6\} \cap \{1,2,3\} = \{2\}$$

**Step 4:** Find $A^c$ (NOT even = odd).
$$A^c = \{1,3,5\}$$

**Step 5:** Find $A \setminus B$ (even but NOT at most 3).
$$A \setminus B = \{2,4,6\} \setminus \{1,2,3\} = \{4,6\}$$

**Answers:** (a) {1,2,3,4,6}, (b) {2}, (c) {1,3,5}, (d) {4,6}

---

### PRACTICE PROBLEMS

**P9.1** (Easy): Roll two dice. How many outcomes are in the sample space?

**P9.2** (Easy): For the two-dice experiment, let $A$ = "sum is 7". List the outcomes in $A$.

**P9.3** (Medium): Three coins are flipped. Let $A$ = "at least one head" and $B$ = "exactly two heads". Find $|A|$ and $|B|$ and $|A \cap B|$.

**P9.4** (Medium): Verify De Morgan's law $(A \cup B)^c = A^c \cap B^c$ using $A = \{1,2,3\}, B = \{3,4,5\}, \Omega = \{1,2,3,4,5,6\}$.

**P9.5** (Hard): In a sample space with events $A, B, C$, express "exactly one of the three events occurs" using set operations.

### SHORT ANSWERS

**A9.1:** $6 \times 6 = 36$

**A9.2:** $A = \{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\}$, $|A| = 6$

**A9.3:** $|A| = 7$ (all except TTT), $|B| = 3$ (HHT,HTH,THH), $|A \cap B| = 3$ (all of $B$ are in $A$)

**A9.4:** LHS: $A \cup B = \{1,2,3,4,5\}$, so $(A \cup B)^c = \{6\}$
RHS: $A^c = \{4,5,6\}, B^c = \{1,2,6\}$, so $A^c \cap B^c = \{6\}$ ✓

**A9.5:** $(A \cap B^c \cap C^c) \cup (A^c \cap B \cap C^c) \cup (A^c \cap B^c \cap C)$

### FULL SOLUTIONS (P9.4 and P9.5)

**Full Solution P9.4:**

**Step 1:** Compute left side $(A \cup B)^c$.
$$A \cup B = \{1,2,3\} \cup \{3,4,5\} = \{1,2,3,4,5\}$$
$$(A \cup B)^c = \Omega \setminus (A \cup B) = \{1,2,3,4,5,6\} \setminus \{1,2,3,4,5\} = \{6\}$$

**Step 2:** Compute right side $A^c \cap B^c$.
$$A^c = \{4,5,6\}$$
$$B^c = \{1,2,6\}$$
$$A^c \cap B^c = \{4,5,6\} \cap \{1,2,6\} = \{6\}$$

**Step 3:** Verify equality.
LHS = {6} = RHS ✓

**Answer:** De Morgan's law verified.

---

**Full Solution P9.5:**

**Step 1:** "Exactly one occurs" means one of these three cases:
- $A$ occurs but not $B$ and not $C$
- $B$ occurs but not $A$ and not $C$
- $C$ occurs but not $A$ and not $B$

**Step 2:** Express each case in set notation.
- Case 1: $A \cap B^c \cap C^c$
- Case 2: $A^c \cap B \cap C^c$
- Case 3: $A^c \cap B^c \cap C$

**Step 3:** Union the three disjoint cases.
$$\text{Exactly one} = (A \cap B^c \cap C^c) \cup (A^c \cap B \cap C^c) \cup (A^c \cap B^c \cap C)$$

**Answer:** $(A \cap B^c \cap C^c) \cup (A^c \cap B \cap C^c) \cup (A^c \cap B^c \cap C)$

---

## 10. KOLMOGOROV AXIOMS

### Intuition
Probability is a function that assigns numbers to events. The three axioms are intuitive: probabilities are non-negative, the total probability is 1, and probabilities of disjoint events add up. Everything else in probability theory derives from these three simple rules.

### Formal Definitions

**Probability Function:** A function $P: \mathcal{F} \to [0,1]$ where $\mathcal{F}$ is the collection of all events, satisfying:

**Axiom 1 (Non-negativity):** For any event $A$,
$$P(A) \geq 0$$

**Axiom 2 (Normalization):** The probability of the entire sample space is 1,
$$P(\Omega) = 1$$

**Axiom 3 (Additivity):** For any countable collection of mutually exclusive events $A_1, A_2, A_3, \ldots$ (where $A_i \cap A_j = \emptyset$ for $i \neq j$),
$$P(A_1 \cup A_2 \cup A_3 \cup \cdots) = P(A_1) + P(A_2) + P(A_3) + \cdots$$

**Immediate Consequences:**

1. $P(\emptyset) = 0$
2. $P(A) \leq 1$ for all $A$
3. $P(A^c) = 1 - P(A)$
4. If $A \subseteq B$ then $P(A) \leq P(B)$

---

### WORKED EXAMPLE 1 (Easy): Verify Axioms

**Problem:** A biased coin has $P(H) = 0.6$ and $P(T) = 0.4$. Verify the three axioms.

**Key idea:** Check each axiom directly.

**Step 1:** Verify Axiom 1 (non-negativity).
$$P(H) = 0.6 \geq 0 \quad ✓$$
$$P(T) = 0.4 \geq 0 \quad ✓$$

**Step 2:** Verify Axiom 2 (normalization).
$$P(\Omega) = P(\{H, T\}) = P(H) + P(T) = 0.6 + 0.4 = 1 \quad ✓$$

**Step 3:** Verify Axiom 3 (additivity).
$H$ and $T$ are disjoint (mutually exclusive), and:
$$P(\{H\} \cup \{T\}) = P(\{H\}) + P(\{T\}) = 0.6 + 0.4 = 1 \quad ✓$$

**Answer:** All three axioms satisfied.

---

### WORKED EXAMPLE 2 (Exam-Style): Derive Complement Rule

**Problem:** Using only the three axioms, prove that $P(A^c) = 1 - P(A)$.

**Key idea:** Use the fact that $A$ and $A^c$ partition the sample space.

**Step 1:** Note that $A$ and $A^c$ are disjoint.
$$A \cap A^c = \emptyset$$

**Step 2:** Note that $A$ and $A^c$ cover the entire sample space.
$$A \cup A^c = \Omega$$

**Step 3:** Apply Axiom 3 (additivity) since $A$ and $A^c$ are disjoint.
$$P(A \cup A^c) = P(A) + P(A^c)$$

**Step 4:** Apply Axiom 2 (normalization).
$$P(\Omega) = 1$$
So:
$$P(A) + P(A^c) = 1$$

**Step 5:** Solve for $P(A^c)$.
$$P(A^c) = 1 - P(A)$$

**Answer:** Proven from axioms.

---

### PRACTICE PROBLEMS

**P10.1** (Easy): If $P(A) = 0.3$, find $P(A^c)$.

**P10.2** (Easy): Can $P(A) = 1.2$? Why or why not?

**P10.3** (Medium): Prove that $P(\emptyset) = 0$ using the axioms.

**P10.4** (Medium): If $A \subseteq B$, prove that $P(A) \leq P(B)$.

**P10.5** (Hard): Events $A_1, A_2, \ldots, A_n$ are mutually exclusive and exhaustive (they partition $\Omega$). Prove that $\sum_{i=1}^{n} P(A_i) = 1$.

### SHORT ANSWERS

**A10.1:** $P(A^c) = 1 - 0.3 = 0.7$

**A10.2:** No. Violates $P(A) \leq 1$ (consequence of axioms).

**A10.3:** Note $\emptyset \cup \emptyset = \emptyset$ and they're disjoint. By Axiom 3: $P(\emptyset) = P(\emptyset) + P(\emptyset)$, so $P(\emptyset) = 0$.

**A10.4:** Write $B = A \cup (B \setminus A)$ (disjoint). Then $P(B) = P(A) + P(B \setminus A) \geq P(A)$ by Axiom 1.

**A10.5:** $A_1 \cup A_2 \cup \cdots \cup A_n = \Omega$ (exhaustive). They're disjoint, so by Axiom 3: $P(\Omega) = \sum P(A_i)$. By Axiom 2: $P(\Omega) = 1$.

### FULL SOLUTIONS (P10.3 and P10.4)

**Full Solution P10.3:**

**Step 1:** Use the property that $\emptyset$ is disjoint from itself.
$$\emptyset \cap \emptyset = \emptyset$$

**Step 2:** Note that $\emptyset \cup \emptyset = \emptyset$.

**Step 3:** Apply Axiom 3 (additivity for disjoint events).
$$P(\emptyset \cup \emptyset) = P(\emptyset) + P(\emptyset)$$
$$P(\emptyset) = 2 \cdot P(\emptyset)$$

**Step 4:** Solve.
$$P(\emptyset) = 2 \cdot P(\emptyset)$$
$$0 = P(\emptyset)$$

**Answer:** $P(\emptyset) = 0$

---

**Full Solution P10.4:**

**Step 1:** Given $A \subseteq B$, partition $B$.
$$B = A \cup (B \setminus A)$$
where $B \setminus A = B \cap A^c$ is the part of $B$ not in $A$.

**Step 2:** Verify disjointness.
$$A \cap (B \setminus A) = A \cap (B \cap A^c) = (A \cap A^c) \cap B = \emptyset \cap B = \emptyset$$

**Step 3:** Apply Axiom 3 (additivity).
$$P(B) = P(A \cup (B \setminus A)) = P(A) + P(B \setminus A)$$

**Step 4:** Apply Axiom 1 (non-negativity).
$$P(B \setminus A) \geq 0$$

**Step 5:** Conclude.
$$P(B) = P(A) + P(B \setminus A) \geq P(A)$$

**Answer:** Proven.

---

## 11. PROBABILITY PROPERTIES

### Intuition
From the three axioms flow many useful formulas. The complement rule handles "NOT," the addition rule handles "OR," and monotonicity ensures larger sets have larger (or equal) probability. Union bounds give quick (though sometimes loose) estimates.

### Formal Definitions & Properties

**Complement Rule:**
$$P(A^c) = 1 - P(A)$$

**Addition Rule (Two Events):**
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Addition Rule (Three Events):**
$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)$$

**Monotonicity:** If $A \subseteq B$, then $P(A) \leq P(B)$.

**Difference Rule:** If $A \subseteq B$, then
$$P(B \setminus A) = P(B) - P(A)$$

**Union Bound (Boole's Inequality):**
$$P(A_1 \cup A_2 \cup \cdots \cup A_n) \leq P(A_1) + P(A_2) + \cdots + P(A_n)$$
Equality holds iff events are mutually exclusive.

**Bonferroni Inequality (lower bound on intersection):**
$$P(A \cap B) \geq P(A) + P(B) - 1$$

---

### WORKED EXAMPLE 1 (Easy): Addition Rule

**Problem:** In a class, 60% of students like math, 50% like science, and 30% like both. What percentage like math or science?

**Key idea:** Use addition rule for $P(A \cup B)$.

**Step 1:** Define events and probabilities.
- $M$ = likes math, $P(M) = 0.6$
- $S$ = likes science, $P(S) = 0.5$
- $M \cap S$ = likes both, $P(M \cap S) = 0.3$

**Step 2:** Apply addition rule.
$$P(M \cup S) = P(M) + P(S) - P(M \cap S)$$

**Step 3:** Compute.
$$P(M \cup S) = 0.6 + 0.5 - 0.3 = 0.8$$

**Answer:** 80% like math or science.

---

### WORKED EXAMPLE 2 (Exam-Style): Union Bound Application

**Problem:** A system has 5 components. Each component fails independently with probability 0.01. Use the union bound to estimate the probability that at least one component fails.

**Key idea:** "At least one" = union of failure events; use union bound for quick upper estimate.

**Step 1:** Define events.
Let $F_i$ = "component $i$ fails", $P(F_i) = 0.01$ for $i=1,2,3,4,5$.

**Step 2:** We want $P(F_1 \cup F_2 \cup F_3 \cup F_4 \cup F_5)$.

**Step 3:** Apply union bound.
$$P(F_1 \cup \cdots \cup F_5) \leq P(F_1) + P(F_2) + P(F_3) + P(F_4) + P(F_5)$$
$$= 0.01 + 0.01 + 0.01 + 0.01 + 0.01 = 0.05$$

**Answer:** The probability is at most 5%.

**Note:** The exact answer (using complement and independence) is $1 - 0.99^5 \approx 0.049$, so the bound is quite tight here.

---

### PRACTICE PROBLEMS

**P11.1** (Easy): If $P(A) = 0.4$ and $P(B) = 0.5$ and $P(A \cap B) = 0.2$, find $P(A \cup B)$.

**P11.2** (Easy): Use complement rule: If $P(\text{rain}) = 0.3$, what is $P(\text{no rain})$?

**P11.3** (Medium): Events $A$ and $B$ satisfy $P(A) = 0.6, P(B) = 0.7$. What are the minimum and maximum possible values of $P(A \cap B)$?

**P11.4** (Medium): Three events have $P(A)=0.5, P(B)=0.4, P(C)=0.3$. Use union bound to estimate $P(A \cup B \cup C)$.

**P11.5** (Hard): Prove the Bonferroni inequality: $P(A \cap B) \geq P(A) + P(B) - 1$.

### SHORT ANSWERS

**A11.1:** $P(A \cup B) = 0.4 + 0.5 - 0.2 = 0.7$

**A11.2:** $P(\text{no rain}) = 1 - 0.3 = 0.7$

**A11.3:** Min: $\max(0, 0.6+0.7-1) = 0.3$ (by Bonferroni). Max: $\min(0.6, 0.7) = 0.6$ (by monotonicity).

**A11.4:** $P(A \cup B \cup C) \leq 0.5 + 0.4 + 0.3 = 1.2$, but probability $\leq 1$, so $P(A \cup B \cup C) \leq 1$.

**A11.5:** From $P(A \cup B) = P(A) + P(B) - P(A \cap B) \leq 1$, rearrange to get $P(A \cap B) \geq P(A) + P(B) - 1$.

### FULL SOLUTIONS (P11.3 and P11.5)

**Full Solution P11.3:**

**Step 1:** Find minimum using Bonferroni inequality.
$$P(A \cap B) \geq P(A) + P(B) - 1 = 0.6 + 0.7 - 1 = 0.3$$

**Step 2:** Find maximum using monotonicity.
Since $A \cap B \subseteq A$ and $A \cap B \subseteq B$:
$$P(A \cap B) \leq \min(P(A), P(B)) = \min(0.6, 0.7) = 0.6$$

**Answer:** Minimum = 0.3, Maximum = 0.6.

---

**Full Solution P11.5:**

**Step 1:** Start with addition rule.
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Step 2:** Use the fact that $P(A \cup B) \leq 1$.
$$P(A) + P(B) - P(A \cap B) \leq 1$$

**Step 3:** Rearrange to isolate $P(A \cap B)$.
$$P(A) + P(B) - 1 \leq P(A \cap B)$$

**Answer:** Proven.

---

## 12. UNIFORM PROBABILITY MODELS

### Intuition
When all outcomes are equally likely, probability becomes pure counting: divide favorable outcomes by total outcomes. This connects probability directly to combinatorics. Most dice, card, and lottery problems use this model.

### Formal Definition

**Uniform Probability Model:** If $\Omega$ is finite and all outcomes are equally likely, then for any event $A \subseteq \Omega$:
$$P(A) = \frac{|A|}{|\Omega|} = \frac{\text{number of favorable outcomes}}{\text{total number of outcomes}}$$

**Requirements:**
1. Sample space $\Omega$ must be finite
2. All outcomes must be equally likely
3. Must count correctly (use combinatorics)

---

### WORKED EXAMPLE 1 (Easy): Fair Die

**Problem:** Roll a fair six-sided die. What is the probability of rolling a number greater than 4?

**Key idea:** Equally likely outcomes → count.

**Step 1:** Identify sample space.
$$\Omega = \{1,2,3,4,5,6\}, \quad |\Omega| = 6$$

**Step 2:** Identify favorable outcomes.
$$A = \{5, 6\}, \quad |A| = 2$$

**Step 3:** Apply uniform model.
$$P(A) = \frac{|A|}{|\Omega|} = \frac{2}{6} = \frac{1}{3}$$

**Answer:** $\frac{1}{3}$

---

### WORKED EXAMPLE 2 (Exam-Style): Poker Hand

**Problem:** A 5-card hand is dealt from a standard 52-card deck. What is the probability of getting exactly 2 aces?

**Key idea:** Use combinations to count hands; uniform model for probability.

**Step 1:** Count total number of 5-card hands.
$$|\Omega| = \binom{52}{5} = \frac{52!}{5! \cdot 47!} = 2,598,960$$

**Step 2:** Count favorable hands (exactly 2 aces).
- Choose 2 aces from 4: $\binom{4}{2} = 6$
- Choose 3 non-aces from 48: $\binom{48}{3} = 17,296$
- Total: $6 \times 17,296 = 103,776$

**Step 3:** Apply uniform model.
$$P(\text{exactly 2 aces}) = \frac{103,776}{2,598,960} = \frac{103,776}{2,598,960}$$

**Step 4:** Simplify (optional).
$$= \frac{6 \times 17,296}{2,598,960} = \frac{103,776}{2,598,960} \approx 0.0399$$

**Answer:** $\frac{103,776}{2,598,960} \approx 4\%$

---

### PRACTICE PROBLEMS

**P12.1** (Easy): Flip three fair coins. What is $P(\text{exactly 2 heads})$?

**P12.2** (Easy): Roll two fair dice. What is $P(\text{sum} = 7)$?

**P12.3** (Medium): A committee of 3 is chosen randomly from 5 men and 4 women. What is $P(\text{exactly 2 women})$?

**P12.4** (Medium): Five cards are drawn from a deck. What is $P(\text{all same suit})$?

**P12.5** (Hard): Ten people sit randomly in a row. What is the probability that two specific people sit next to each other?

### SHORT ANSWERS

**A12.1:** $|\Omega| = 8, |A| = 3$ (HHT, HTH, THH), $P(A) = 3/8$

**A12.2:** $|\Omega| = 36, |A| = 6$ (see earlier), $P(A) = 6/36 = 1/6$

**A12.3:** Total: $\binom{9}{3} = 84$. Favorable: $\binom{4}{2} \times \binom{5}{1} = 6 \times 5 = 30$. $P = 30/84 = 5/14$

**A12.4:** $P = \frac{4 \times \binom{13}{5}}{\binom{52}{5}} = \frac{4 \times 1287}{2598960} = \frac{5148}{2598960} \approx 0.00198$

**A12.5:** Treat the two as a "block": $2 \times 9!$ arrangements (block can be ordered 2 ways). Total: $10!$. $P = \frac{2 \times 9!}{10!} = \frac{2}{10} = 1/5$

### FULL SOLUTIONS (P12.3 and P12.5)

**Full Solution P12.3:**

**Step 1:** Count total committees.
$$|\Omega| = \binom{9}{3} = \frac{9 \times 8 \times 7}{3 \times 2 \times 1} = \frac{504}{6} = 84$$

**Step 2:** Count favorable committees (exactly 2 women, 1 man).
- Choose 2 women from 4: $\binom{4}{2} = 6$
- Choose 1 man from 5: $\binom{5}{1} = 5$
- Total: $6 \times 5 = 30$

**Step 3:** Apply uniform model.
$$P = \frac{30}{84} = \frac{5}{14}$$

**Answer:** $\frac{5}{14} \approx 0.357$

---

**Full Solution P12.5:**

**Step 1:** Count total arrangements.
$$|\Omega| = 10!$$

**Step 2:** Count favorable arrangements.
Treat the two specific people as a single "block."
- Arrangements of 9 objects (the block + 8 others): $9!$
- Within the block, 2 people can be ordered in $2!$ ways
- Total: $9! \times 2 = 2 \times 9!$

**Step 3:** Apply uniform model.
$$P = \frac{2 \times 9!}{10!} = \frac{2 \times 9!}{10 \times 9!} = \frac{2}{10} = \frac{1}{5}$$

**Answer:** $\frac{1}{5} = 0.2$

---

## IF YOU ONLY HAVE 10 MINUTES (Probability Axioms)

**Memorize these 3 things:**
1. **Three axioms:** (1) $P(A) \geq 0$, (2) $P(\Omega) = 1$, (3) Disjoint events add: $P(A \cup B) = P(A) + P(B)$
2. **Complement:** $P(A^c) = 1 - P(A)$ — use for "at least one" problems
3. **Addition rule:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ — for non-disjoint events

**Do these 2 practice problems:**
1. If $P(A) = 0.6, P(B) = 0.7, P(A \cap B) = 0.4$, find $P(A \cup B)$. Answer: $0.6 + 0.7 - 0.4 = 0.9$
2. Roll a die; find $P(\text{even})$. Answer: $3/6 = 1/2$

