# PART III (CONTINUED): INDEPENDENCE & EXAM TEMPLATES

## 16. PROBABILITY TREES

### Intuition
Trees organize multi-stage experiments visually. Each branch represents an outcome at one stage, labeled with its conditional probability. To find the probability of a path, multiply along branches. To find total probability of an event spread across multiple paths, add the relevant path probabilities.

### Tree Structure

```
Start
  ├─[P(B₁)]─→ B₁
  │           ├─[P(A|B₁)]─→ A ∩ B₁   (prob = P(B₁)P(A|B₁))
  │           └─[P(Aᶜ|B₁)]─→ Aᶜ ∩ B₁
  │
  └─[P(B₂)]─→ B₂
              ├─[P(A|B₂)]─→ A ∩ B₂   (prob = P(B₂)P(A|B₂))
              └─[P(Aᶜ|B₂)]─→ Aᶜ ∩ B₂
```

**Rules:**
- **Multiply along branches** to get path probability
- **Add across branches** for total probability of an event
- Branch probabilities from same node must sum to 1

---

### WORKED EXAMPLE: Medical Test Tree

**Problem:** Disease prevalence: 2%. Test sensitivity: 90%, specificity: 95%. Draw a tree and find $P(+)$.

**Step 1:** Draw tree.

```
         Start
         /    \
    [0.02]    [0.98]
      D         Dᶜ
     / \       / \
 [0.9][0.1][0.05][0.95]
   +    -    +     -
```

**Step 2:** Calculate path probabilities.
- $P(+ \cap D) = 0.02 \times 0.9 = 0.018$
- $P(- \cap D) = 0.02 \times 0.1 = 0.002$
- $P(+ \cap D^c) = 0.98 \times 0.05 = 0.049$
- $P(- \cap D^c) = 0.98 \times 0.95 = 0.931$

**Step 3:** Find $P(+)$ by adding relevant paths.
$$P(+) = P(+ \cap D) + P(+ \cap D^c) = 0.018 + 0.049 = 0.067$$

**Answer:** 6.7% test positive.

---

## 17. INDEPENDENCE

### Intuition
Events are independent if knowing one occurred doesn't change the probability of the other. Flipping two coins: the first flip doesn't affect the second. Independence means "no information transfer" and allows you to multiply probabilities. **Key:** Disjoint events are NOT independent (except trivial cases) — if $A$ and $B$ are disjoint and both have positive probability, then $P(A|B) = 0 \neq P(A)$.

### Formal Definitions

**Independence of Two Events:** Events $A$ and $B$ are independent if:
$$P(A \cap B) = P(A) \cdot P(B)$$

**Equivalent conditions (when $P(B) > 0$):**
- $P(A|B) = P(A)$
- $P(B|A) = P(B)$ (when $P(A) > 0$)

**Independence of Complements:** If $A$ and $B$ are independent, then:
- $A$ and $B^c$ are independent
- $A^c$ and $B$ are independent
- $A^c$ and $B^c$ are independent

**Mutual Independence (Multiple Events):** Events $A_1, A_2, \ldots, A_n$ are mutually independent if for every subset $\{i_1, i_2, \ldots, i_k\} \subseteq \{1, 2, \ldots, n\}$:
$$P(A_{i_1} \cap A_{i_2} \cap \cdots \cap A_{i_k}) = P(A_{i_1}) \cdot P(A_{i_2}) \cdots P(A_{i_k})$$

For $n=3$, this requires **4 conditions**:
- $P(A \cap B) = P(A)P(B)$ (pairwise)
- $P(A \cap C) = P(A)P(C)$ (pairwise)
- $P(B \cap C) = P(B)P(C)$ (pairwise)
- $P(A \cap B \cap C) = P(A)P(B)P(C)$ (mutual)

**Pairwise vs Mutual:**
- **Pairwise independent:** Every pair is independent (3 conditions for 3 events)
- **Mutually independent:** All subsets satisfy independence (4 conditions for 3 events)
- Mutual $\Rightarrow$ pairwise, but pairwise $\not\Rightarrow$ mutual

**Conditional Independence:** $A$ and $B$ are conditionally independent given $C$ if:
$$P(A \cap B | C) = P(A|C) \cdot P(B|C)$$

**Warning:** Conditional independence ≠ unconditional independence

---

### WORKED EXAMPLE 1 (Easy): Check Independence

**Problem:** Roll a fair die. Let $A$ = "roll is even" = {2,4,6}, $B$ = "roll is at most 3" = {1,2,3}. Are $A$ and $B$ independent?

**Key idea:** Check if $P(A \cap B) = P(A) \cdot P(B)$.

**Step 1:** Find probabilities.
$$P(A) = \frac{3}{6} = \frac{1}{2}$$
$$P(B) = \frac{3}{6} = \frac{1}{2}$$

**Step 2:** Find intersection.
$$A \cap B = \{2\}$$
$$P(A \cap B) = \frac{1}{6}$$

**Step 3:** Check independence condition.
$$P(A) \cdot P(B) = \frac{1}{2} \times \frac{1}{2} = \frac{1}{4}$$
$$P(A \cap B) = \frac{1}{6} \neq \frac{1}{4}$$

**Answer:** NOT independent.

---

### WORKED EXAMPLE 2 (Exam-Style): At Least One Success

**Problem:** A basketball player makes free throws independently with 70% success rate. She shoots 5 free throws. What is the probability she makes at least one?

**Key idea:** Use complement and independence.

**Step 1:** Identify complementary event.
"At least one" = complement of "none"

**Step 2:** Find $P(\text{none})$.
Each shot misses with probability $0.3$. By independence:
$$P(\text{all 5 miss}) = 0.3^5 = 0.00243$$

**Step 3:** Use complement rule.
$$P(\text{at least 1}) = 1 - P(\text{none}) = 1 - 0.00243 = 0.99757$$

**Answer:** 99.757%

---

### WORKED EXAMPLE 3 (Hard): Pairwise but Not Mutually Independent

**Problem:** A fair coin is flipped twice. Let:
- $A$ = first flip is H
- $B$ = second flip is H
- $C$ = exactly one H

Show that $A, B, C$ are pairwise independent but not mutually independent.

**Step 1:** Sample space and probabilities.
$$\Omega = \{HH, HT, TH, TT\}$$
$$A = \{HH, HT\}, \quad P(A) = \frac{1}{2}$$
$$B = \{HH, TH\}, \quad P(B) = \frac{1}{2}$$
$$C = \{HT, TH\}, \quad P(C) = \frac{1}{2}$$

**Step 2:** Check pairwise independence.

$A \cap B = \{HH\}, P(A \cap B) = \frac{1}{4} = \frac{1}{2} \times \frac{1}{2} = P(A)P(B)$ ✓

$A \cap C = \{HT\}, P(A \cap C) = \frac{1}{4} = \frac{1}{2} \times \frac{1}{2} = P(A)P(C)$ ✓

$B \cap C = \{TH\}, P(B \cap C) = \frac{1}{4} = \frac{1}{2} \times \frac{1}{2} = P(B)P(C)$ ✓

Pairwise independent ✓

**Step 3:** Check mutual independence.
$$A \cap B \cap C = \emptyset, \quad P(A \cap B \cap C) = 0$$
$$P(A)P(B)P(C) = \frac{1}{2} \times \frac{1}{2} \times \frac{1}{2} = \frac{1}{8}$$
$$0 \neq \frac{1}{8}$$

**Answer:** Pairwise independent but NOT mutually independent.

---

### PRACTICE PROBLEMS

**P17.1** (Easy): Events $A$ and $B$ have $P(A) = 0.5, P(B) = 0.4, P(A \cap B) = 0.2$. Are they independent?

**P17.2** (Easy): Roll two fair dice independently. What is $P(\text{both show 6})$?

**P17.3** (Medium): A coin is flipped 4 times independently. What is $P(\text{all heads})$?

**P17.4** (Medium): A system has 3 independent components, each working with probability 0.9. What is $P(\text{all work})$?

**P17.5** (Hard): 10 fair coins are flipped independently. What is the probability of at least one head?

### SHORT ANSWERS

**A17.1:** $P(A) \cdot P(B) = 0.5 \times 0.4 = 0.2 = P(A \cap B)$. YES, independent.

**A17.2:** $\frac{1}{6} \times \frac{1}{6} = \frac{1}{36}$

**A17.3:** $\left(\frac{1}{2}\right)^4 = \frac{1}{16}$

**A17.4:** $0.9^3 = 0.729$

**A17.5:** $1 - \left(\frac{1}{2}\right)^{10} = 1 - \frac{1}{1024} = \frac{1023}{1024} \approx 0.999$

### FULL SOLUTIONS (P17.4 and P17.5)

**Full Solution P17.4:**

**Step 1:** Use independence.
Since components work independently:
$$P(\text{all work}) = P(C_1 \text{ works}) \times P(C_2 \text{ works}) \times P(C_3 \text{ works})$$

**Step 2:** Compute.
$$= 0.9 \times 0.9 \times 0.9 = 0.9^3 = 0.729$$

**Answer:** 0.729 or 72.9%

---

**Full Solution P17.5:**

**Step 1:** Use complement.
"At least one head" = complement of "all tails"

**Step 2:** Find $P(\text{all tails})$.
Each coin shows tails with probability $\frac{1}{2}$. By independence:
$$P(\text{all tails}) = \left(\frac{1}{2}\right)^{10} = \frac{1}{1024}$$

**Step 3:** Apply complement rule.
$$P(\text{at least 1 head}) = 1 - \frac{1}{1024} = \frac{1023}{1024}$$

**Answer:** $\frac{1023}{1024} \approx 0.999$

---

## 18. COMMON EXAM TEMPLATES

### Template 1: Birthday Problem

**General Setup:** $n$ people, $d$ possible birthdays (usually $d=365$). What is $P(\text{at least 2 share birthday})$?

**Solution Pattern:**
1. Use complement: $P(\geq 2 \text{ match}) = 1 - P(\text{all different})$
2. $P(\text{all different}) = \frac{d}{d} \times \frac{d-1}{d} \times \frac{d-2}{d} \times \cdots \times \frac{d-n+1}{d} = \frac{P(d,n)}{d^n}$

**Classic Example:** $n=23, d=365$
$$P(\text{match}) = 1 - \frac{365 \times 364 \times \cdots \times 343}{365^{23}} \approx 0.507$$

---

### Template 2: Balls and Bins (Occupancy)

**Setup:** Throw $n$ balls into $m$ bins uniformly at random.

**Common Questions:**
- $P(\text{specific bin is empty}) = \left(\frac{m-1}{m}\right)^n$
- $P(\text{all bins occupied})$ — use inclusion-exclusion

---

### Template 3: Card Problems

**Patterns:**
- **With replacement:** Independence → multiply
- **Without replacement:** Conditional probability → multiply conditional probs
- **Hands:** Combinations → $\frac{\binom{...}}{\binom{52}{5}}$

**Example:** $P(\text{flush}) = \frac{4 \times \binom{13}{5}}{\binom{52}{5}}$

---

### Template 4: Disease Testing

**Setup:** Prior $P(D)$, sensitivity $P(+|D)$, specificity $P(-|D^c)$.

**Want:** $P(D|+)$ (posterior)

**Solution:** Bayes' theorem
$$P(D|+) = \frac{P(+|D) P(D)}{P(+|D) P(D) + P(+|D^c) P(D^c)}$$

---

### Template 5: System Reliability

**Series System:** All components must work
$$P(\text{system works}) = \prod_{i=1}^{n} P(C_i \text{ works})$$

**Parallel System:** At least one component must work
$$P(\text{system works}) = 1 - \prod_{i=1}^{n} P(C_i \text{ fails})$$

---

### Template 6: Gambler's Ruin (Brief)

**Setup:** Start with $a$ dollars, play until reach $0$ or $N$. Each round: win $1 with prob $p$, lose $1 with prob $q=1-p$.

**Probability of ruin:** Complex; use recurrence or formula
- If $p = 1/2$: $P(\text{ruin}) = \frac{N-a}{N}$
- If $p \neq 1/2$: $P(\text{ruin}) = \frac{(q/p)^a - (q/p)^N}{1 - (q/p)^N}$

---

### Template 7: Coupon Collector

**Setup:** $n$ types of coupons. Collect randomly with replacement. Expected number to collect all $n$ types:
$$E[\text{coupons}] = n \left(1 + \frac{1}{2} + \frac{1}{3} + \cdots + \frac{1}{n}\right) = n H_n \approx n \ln n$$

---

### Template 8: Matching Problems

**Setup:** $n$ items, $n$ positions. Randomly assign. $P(\text{at least 1 match})$?

**Solution:** Inclusion-exclusion or derangements
$$P(\geq 1 \text{ match}) = 1 - \frac{D_n}{n!} \approx 1 - \frac{1}{e} \approx 0.632$$

---

## COMPREHENSIVE WORKED PROBLEM: Combining Templates

**Problem:** A company has 3 servers, each independently operational 95% of the time. The system is designed so that if at least 2 servers work, the company can function. A monitoring alarm is triggered if the system is down, but the alarm itself is faulty: it rings 98% of the time when system is down, and 5% of the time when system is up. The alarm rings. What is the probability the system is actually down?

**Key idea:** Combine reliability (parallel/series logic), independence, and Bayes.

**Step 1:** Find $P(\text{system down})$.
System down means at most 1 server works (0 or 1 work, so 2 or 3 fail).

$P(\text{0 work}) = 0.05^3 = 0.000125$
$P(\text{exactly 1 works}) = \binom{3}{1} (0.95)(0.05)^2 = 3 \times 0.95 \times 0.0025 = 0.007125$

$P(\text{system down}) = 0.000125 + 0.007125 = 0.00725$
$P(\text{system up}) = 1 - 0.00725 = 0.99275$

**Step 2:** Define alarm probabilities.
Let $A$ = alarm rings, $D$ = system down.
- $P(A|D) = 0.98$ (sensitivity)
- $P(A|D^c) = 0.05$ (false alarm)

**Step 3:** Apply Bayes.
$$P(D|A) = \frac{P(A|D) P(D)}{P(A|D) P(D) + P(A|D^c) P(D^c)}$$
$$= \frac{0.98 \times 0.00725}{0.98 \times 0.00725 + 0.05 \times 0.99275}$$
$$= \frac{0.007105}{0.007105 + 0.0496375} = \frac{0.007105}{0.0567425}$$
$$\approx 0.1252$$

**Answer:** About 12.5% chance system is actually down.

**Insight:** Despite a pretty good alarm, the very high system reliability (99.3%) means most alarms are false.

---

## IF YOU ONLY HAVE 10 MINUTES (Independence & Templates)

**Memorize these 3 things:**
1. **Independence:** $P(A \cap B) = P(A) \cdot P(B)$; equivalently $P(A|B) = P(A)$
2. **At least one (independent trials):** $P(\geq 1) = 1 - P(\text{none}) = 1 - (1-p)^n$
3. **Birthday/matching:** Use complement; for birthday with $n=23$, $P \approx 50\%$

**Do these 2 practice problems:**
1. Three coins flipped independently. $P(\text{at least 1 head}) = ?$ Answer: $1 - (1/2)^3 = 7/8$
2. Are disjoint events independent? Answer: NO (if both have positive probability)

---

## SUMMARY: All of Part III

**Key Formulas Recap:**
- $P(A|B) = \frac{P(A \cap B)}{P(B)}$
- $P(A \cap B) = P(A) P(B|A)$
- LOTP: $P(A) = \sum P(A|B_i) P(B_i)$
- Bayes: $P(B_i|A) = \frac{P(A|B_i) P(B_i)}{P(A)}$
- Independence: $P(A \cap B) = P(A) P(B)$

**Problem-Solving Workflow:**
1. **Identify what you're looking for** (probability of what event?)
2. **Check if independence applies** (can you multiply?)
3. **Check if complement is easier** ("at least one" → complement)
4. **Break into cases** (use LOTP if needed)
5. **Apply Bayes if reversing conditional**
6. **Draw a tree** if multi-stage/sequential

**Common Pitfalls:**
- Confusing $P(A|B)$ with $P(B|A)$
- Assuming disjoint = independent (opposite!)
- Forgetting to use complement for "at least" problems
- Not checking all conditions for mutual independence
- Arithmetic errors in Bayes (check denominator carefully)

