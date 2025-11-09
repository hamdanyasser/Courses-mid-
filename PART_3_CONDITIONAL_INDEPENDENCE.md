# PART III: CONDITIONAL PROBABILITY & INDEPENDENCE

## ESSENTIALS ONLY - TL;DR (Conditional Probability & Independence)

### Core Formulas (Memorize These)

1. **Conditional probability:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$ for $P(B) > 0$

2. **Multiplication rule:** $P(A \cap B) = P(B) \cdot P(A|B) = P(A) \cdot P(B|A)$

3. **Chain rule:** $P(A_1 \cap A_2 \cap \cdots \cap A_n) = P(A_1) \cdot P(A_2|A_1) \cdot P(A_3|A_1 \cap A_2) \cdots$

4. **Law of Total Probability:** If $B_1, \ldots, B_n$ partition $\Omega$:
   $$P(A) = \sum_{i=1}^{n} P(A|B_i) P(B_i)$$

5. **Bayes' Theorem:**
   $$P(B_i|A) = \frac{P(A|B_i) P(B_i)}{\sum_{j=1}^{n} P(A|B_j) P(B_j)} = \frac{P(A|B_i) P(B_i)}{P(A)}$$

6. **Independence (two events):** $P(A \cap B) = P(A) \cdot P(B)$
   Equivalently: $P(A|B) = P(A)$ (if $P(B) > 0$)

7. **Independence (multiple events):** Events $A_1, \ldots, A_n$ are mutually independent if for every subset $I \subseteq \{1, \ldots, n\}$:
   $$P\left(\bigcap_{i \in I} A_i\right) = \prod_{i \in I} P(A_i)$$

8. **Pairwise vs Mutual:** Pairwise independent means every pair satisfies independence; mutual independence requires all subsets.

9. **Complement of independent events:** If $A$ and $B$ are independent, then so are $A$ and $B^c$, $A^c$ and $B$, and $A^c$ and $B^c$.

10. **Conditional independence:** $A$ and $B$ are conditionally independent given $C$ if:
    $$P(A \cap B | C) = P(A|C) \cdot P(B|C)$$

### 10 Exam Templates

| # | Pattern | Solution Skeleton |
|---|---------|-------------------|
| 1 | "Given B occurred, what is P(A)?" | $P(A\|B) = \frac{P(A \cap B)}{P(B)}$ |
| 2 | "Find P(A and B) given conditional info" | Multiplication rule: $P(A \cap B) = P(A) P(B\|A)$ |
| 3 | "Two-stage process (tree)" | Chain rule or draw tree; multiply along branches |
| 4 | "Total probability over cases" | Partition sample space; use law of total prob |
| 5 | "Reverse conditional: P(cause\|effect)" | Bayes' theorem |
| 6 | "Disease testing / false positive" | Bayes with prior, sensitivity, specificity |
| 7 | "Are A and B independent?" | Check if $P(A \cap B) = P(A) P(B)$ |
| 8 | "At least one in n independent trials" | $1 - P(\text{none})^n$ |
| 9 | "Birthday problem / collision" | Complement: $1 - P(\text{all different})$ |
| 10 | "System reliability (series/parallel)" | Series: multiply; Parallel: complement |

### 5 Mnemonics & Pitfalls

**Mnemonics:**
1. **"Conditional = Intersection ÷ Condition"** - $P(A|B) = \frac{P(A \cap B)}{P(B)}$
2. **"Bayes flips the conditional"** - Converts $P(A|B)$ to $P(B|A)$
3. **"Tree: multiply along, add across"** - Probability trees
4. **"Independent means multiply"** - $P(A \cap B) = P(A) \cdot P(B)$
5. **"LOTP: weighted average over partition"** - Law of total probability

**Pitfalls:**
1. **$P(A|B) \neq P(B|A)$** - Common confusion! They're usually different.
2. **$P(A|B) \neq \frac{P(A)}{P(B)}$** - Need intersection in numerator
3. **Independence $\neq$ disjoint** - Disjoint events (except trivial) are dependent!
4. **Pairwise independent $\not\Rightarrow$ mutually independent** - Need to check all subsets
5. **Don't forget the denominator in Bayes** - Use LOTP to find $P(A)$

---

## 13. CONDITIONAL PROBABILITY

### Intuition
Conditional probability updates our belief when we get new information. $P(A|B)$ asks: "Given that $B$ happened, what's the probability of $A$?" We restrict to the world where $B$ is true and renormalize. Think of it as zooming into the $B$ portion of the sample space.

### Formal Definitions

**Conditional Probability:** For events $A$ and $B$ with $P(B) > 0$:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

Interpretation: The fraction of $B$'s probability that overlaps with $A$.

**Multiplication Rule (Product Rule):**
$$P(A \cap B) = P(B) \cdot P(A|B) = P(A) \cdot P(B|A)$$

**Chain Rule (General):**
$$P(A_1 \cap A_2 \cap \cdots \cap A_n) = P(A_1) \cdot P(A_2|A_1) \cdot P(A_3|A_1 \cap A_2) \cdots P(A_n|A_1 \cap \cdots \cap A_{n-1})$$

**Properties:**
- $0 \leq P(A|B) \leq 1$
- $P(B|B) = 1$
- $P(A^c|B) = 1 - P(A|B)$
- $P(\Omega|B) = 1$

---

### WORKED EXAMPLE 1 (Easy): Card Draw

**Problem:** A card is drawn from a standard deck. Given that it's a face card (J, Q, K), what's the probability it's a King?

**Key idea:** Use definition of conditional probability.

**Step 1:** Define events.
- $A$ = card is a King
- $B$ = card is a face card (J, Q, K)

**Step 2:** Find $P(A \cap B)$.
Kings are face cards, so $A \cap B = A$.
$$P(A \cap B) = P(A) = \frac{4}{52} = \frac{1}{13}$$

**Step 3:** Find $P(B)$.
Face cards: 4 Jacks + 4 Queens + 4 Kings = 12 cards
$$P(B) = \frac{12}{52} = \frac{3}{13}$$

**Step 4:** Apply conditional probability formula.
$$P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{1/13}{3/13} = \frac{1}{3}$$

**Answer:** $\frac{1}{3}$

---

### WORKED EXAMPLE 2 (Exam-Style): Sequential Selection

**Problem:** A box contains 3 red balls and 2 blue balls. Two balls are drawn without replacement. What is the probability both are red?

**Key idea:** Use multiplication rule with conditional probability.

**Step 1:** Define events.
- $R_1$ = first ball is red
- $R_2$ = second ball is red

We want $P(R_1 \cap R_2)$.

**Step 2:** Apply multiplication rule.
$$P(R_1 \cap R_2) = P(R_1) \cdot P(R_2|R_1)$$

**Step 3:** Find $P(R_1)$.
$$P(R_1) = \frac{3}{5}$$

**Step 4:** Find $P(R_2|R_1)$.
Given first ball is red, 2 red and 2 blue remain (4 balls total).
$$P(R_2|R_1) = \frac{2}{4} = \frac{1}{2}$$

**Step 5:** Multiply.
$$P(R_1 \cap R_2) = \frac{3}{5} \times \frac{1}{2} = \frac{3}{10}$$

**Answer:** $\frac{3}{10}$

---

### PRACTICE PROBLEMS

**P13.1** (Easy): Roll a fair die. Given the result is even, what's the probability it's a 2?

**P13.2** (Easy): $P(A) = 0.6, P(B) = 0.5, P(A \cap B) = 0.3$. Find $P(A|B)$.

**P13.3** (Medium): Two cards are drawn from a deck without replacement. What is $P(\text{both aces})$?

**P13.4** (Medium): $P(A|B) = 0.4, P(B) = 0.5$. Find $P(A \cap B)$.

**P13.5** (Hard): Three cards are drawn without replacement from a deck. What is the probability all three are spades?

### SHORT ANSWERS

**A13.1:** $B = \{2,4,6\}, A = \{2\}, A \cap B = \{2\}$. $P(A|B) = \frac{1/6}{3/6} = \frac{1}{3}$

**A13.2:** $P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{0.3}{0.5} = 0.6$

**A13.3:** $P(\text{both aces}) = \frac{4}{52} \times \frac{3}{51} = \frac{12}{2652} = \frac{1}{221}$

**A13.4:** $P(A \cap B) = P(B) \cdot P(A|B) = 0.5 \times 0.4 = 0.2$

**A13.5:** $P = \frac{13}{52} \times \frac{12}{51} \times \frac{11}{50} = \frac{13 \times 12 \times 11}{52 \times 51 \times 50} = \frac{1716}{132600} = \frac{11}{850}$

### FULL SOLUTIONS (P13.3 and P13.5)

**Full Solution P13.3:**

**Step 1:** Use multiplication rule.
$$P(\text{both aces}) = P(\text{1st ace}) \cdot P(\text{2nd ace}|\text{1st ace})$$

**Step 2:** Find $P(\text{1st ace})$.
$$P(\text{1st ace}) = \frac{4}{52}$$

**Step 3:** Find $P(\text{2nd ace}|\text{1st ace})$.
Given first is ace, 3 aces remain among 51 cards.
$$P(\text{2nd ace}|\text{1st ace}) = \frac{3}{51}$$

**Step 4:** Multiply.
$$P(\text{both aces}) = \frac{4}{52} \times \frac{3}{51} = \frac{12}{2652}$$

**Step 5:** Simplify.
$$= \frac{12}{2652} = \frac{1}{221}$$

**Answer:** $\frac{1}{221} \approx 0.00452$

---

**Full Solution P13.5:**

**Step 1:** Use chain rule for three cards.
$$P(\text{all spades}) = P(S_1) \cdot P(S_2|S_1) \cdot P(S_3|S_1 \cap S_2)$$

**Step 2:** Calculate each probability.
$$P(S_1) = \frac{13}{52}$$
$$P(S_2|S_1) = \frac{12}{51}$$
$$P(S_3|S_1 \cap S_2) = \frac{11}{50}$$

**Step 3:** Multiply.
$$P(\text{all spades}) = \frac{13}{52} \times \frac{12}{51} \times \frac{11}{50}$$
$$= \frac{13 \times 12 \times 11}{52 \times 51 \times 50} = \frac{1716}{132600}$$

**Step 4:** Simplify.
$$= \frac{1716}{132600} = \frac{143}{11050} = \frac{11}{850}$$

**Answer:** $\frac{11}{850} \approx 0.01294$

---

## 14. LAW OF TOTAL PROBABILITY

### Intuition
When you can't compute $P(A)$ directly, break it into cases based on a partition. The law of total probability says: sum over all scenarios, weighting each by how likely that scenario is. Think of it as a weighted average.

### Formal Definition

**Partition:** Events $B_1, B_2, \ldots, B_n$ form a partition of $\Omega$ if:
1. They are mutually exclusive: $B_i \cap B_j = \emptyset$ for $i \neq j$
2. They are exhaustive: $B_1 \cup B_2 \cup \cdots \cup B_n = \Omega$

**Law of Total Probability (LOTP):** If $B_1, \ldots, B_n$ partition $\Omega$ and $P(B_i) > 0$ for all $i$, then:
$$P(A) = \sum_{i=1}^{n} P(A|B_i) \cdot P(B_i)$$

**Two-case version (most common):**
$$P(A) = P(A|B) \cdot P(B) + P(A|B^c) \cdot P(B^c)$$

---

### WORKED EXAMPLE 1 (Easy): Coin Flip and Die Roll

**Problem:** Flip a fair coin. If heads, roll a 4-sided die. If tails, roll a 6-sided die. What is the probability of rolling a 1?

**Key idea:** Partition by coin result; use LOTP.

**Step 1:** Define partition.
- $H$ = heads, $P(H) = 1/2$
- $T$ = tails, $P(T) = 1/2$

**Step 2:** Define event of interest.
$A$ = roll a 1

**Step 3:** Find conditional probabilities.
$$P(A|H) = \frac{1}{4}$$ (1 out of 4 on 4-sided die)
$$P(A|T) = \frac{1}{6}$$ (1 out of 6 on 6-sided die)

**Step 4:** Apply LOTP.
$$P(A) = P(A|H) \cdot P(H) + P(A|T) \cdot P(T)$$
$$= \frac{1}{4} \times \frac{1}{2} + \frac{1}{6} \times \frac{1}{2}$$
$$= \frac{1}{8} + \frac{1}{12}$$

**Step 5:** Find common denominator.
$$= \frac{3}{24} + \frac{2}{24} = \frac{5}{24}$$

**Answer:** $\frac{5}{24}$

---

### WORKED EXAMPLE 2 (Exam-Style): Defective Products

**Problem:** A factory has two machines. Machine A produces 60% of the products with 2% defective rate. Machine B produces 40% with 5% defective rate. A product is selected at random. What is the probability it's defective?

**Key idea:** Partition by machine; use LOTP.

**Step 1:** Define partition.
- $A$ = from Machine A, $P(A) = 0.6$
- $B$ = from Machine B, $P(B) = 0.4$

**Step 2:** Define event.
$D$ = product is defective

**Step 3:** Given conditional probabilities.
$$P(D|A) = 0.02$$
$$P(D|B) = 0.05$$

**Step 4:** Apply LOTP.
$$P(D) = P(D|A) \cdot P(A) + P(D|B) \cdot P(B)$$
$$= 0.02 \times 0.6 + 0.05 \times 0.4$$
$$= 0.012 + 0.020$$
$$= 0.032$$

**Answer:** 0.032 or 3.2%

---

### PRACTICE PROBLEMS

**P14.1** (Easy): $P(B) = 0.3, P(A|B) = 0.8, P(A|B^c) = 0.4$. Find $P(A)$.

**P14.2** (Medium): A bag has 3 red and 2 blue balls. If red is drawn, flip a fair coin. If blue is drawn, roll a die. What is $P(\text{heads or 6})$?

**P14.3** (Medium): 30% of students are freshmen, 70% are sophomores. 20% of freshmen have cars, 50% of sophomores have cars. What fraction of all students have cars?

**P14.4** (Hard): Three boxes: Box 1 (2 red, 1 blue), Box 2 (1 red, 2 blue), Box 3 (3 red, 3 blue). Choose a box uniformly at random, then draw a ball. What is $P(\text{red ball})$?

**P14.5** (Hard): In a best-of-3 series, Team A has probability 0.6 of winning each game independently. What is the probability Team A wins the series?

### SHORT ANSWERS

**A14.1:** $P(A) = 0.8(0.3) + 0.4(0.7) = 0.24 + 0.28 = 0.52$

**A14.2:** $P(\text{red}) = 3/5$. Given red: $P(H) = 1/2$. Given blue: $P(6) = 1/6$.
$P = \frac{3}{5} \cdot \frac{1}{2} + \frac{2}{5} \cdot \frac{1}{6} = \frac{3}{10} + \frac{2}{30} = \frac{9}{30} + \frac{2}{30} = \frac{11}{30}$

**A14.3:** $P(\text{car}) = 0.20(0.30) + 0.50(0.70) = 0.06 + 0.35 = 0.41$ or 41%

**A14.4:** $P(R|B_1) = 2/3, P(R|B_2) = 1/3, P(R|B_3) = 1/2$. Each box: $P = 1/3$.
$P(R) = \frac{1}{3}(\frac{2}{3} + \frac{1}{3} + \frac{1}{2}) = \frac{1}{3} \cdot \frac{3}{2} = \frac{1}{2}$

**A14.5:** Win in 2 (AA): $0.6^2 = 0.36$. Win in 3 (ABA or BAA): $2 \times 0.6 \times 0.4 \times 0.6 = 0.288$. Total: $0.648$

### FULL SOLUTIONS (P14.4 and P14.5)

**Full Solution P14.4:**

**Step 1:** Define partition (by box).
$$P(B_1) = P(B_2) = P(B_3) = \frac{1}{3}$$

**Step 2:** Find conditional probabilities.
$$P(R|B_1) = \frac{2}{3}, \quad P(R|B_2) = \frac{1}{3}, \quad P(R|B_3) = \frac{3}{6} = \frac{1}{2}$$

**Step 3:** Apply LOTP.
$$P(R) = P(R|B_1) P(B_1) + P(R|B_2) P(B_2) + P(R|B_3) P(B_3)$$
$$= \frac{2}{3} \cdot \frac{1}{3} + \frac{1}{3} \cdot \frac{1}{3} + \frac{1}{2} \cdot \frac{1}{3}$$
$$= \frac{2}{9} + \frac{1}{9} + \frac{1}{6}$$

**Step 4:** Common denominator (18).
$$= \frac{4}{18} + \frac{2}{18} + \frac{3}{18} = \frac{9}{18} = \frac{1}{2}$$

**Answer:** $\frac{1}{2}$

---

**Full Solution P14.5:**

**Step 1:** Identify winning scenarios for Team A.
Series is best-of-3 (first to win 2 games).
- Win 2-0: AA
- Win 2-1: ABA or BAA

**Step 2:** Calculate $P(\text{AA})$.
$$P(\text{AA}) = 0.6 \times 0.6 = 0.36$$

**Step 3:** Calculate $P(\text{ABA})$.
$$P(\text{ABA}) = 0.6 \times 0.4 \times 0.6 = 0.144$$

**Step 4:** Calculate $P(\text{BAA})$.
$$P(\text{BAA}) = 0.4 \times 0.6 \times 0.6 = 0.144$$

**Step 5:** Sum all winning scenarios.
$$P(\text{A wins series}) = 0.36 + 0.144 + 0.144 = 0.648$$

**Answer:** 0.648 or 64.8%

---

## 15. BAYES' THEOREM

### Intuition
Bayes' theorem lets you "flip" a conditional probability. If you know $P(\text{symptom}|\text{disease})$ but want $P(\text{disease}|\text{symptom})$, Bayes is your tool. It combines prior knowledge with new evidence to update beliefs. Essential for diagnostic problems, spam filtering, and inference.

### Formal Definition

**Bayes' Theorem (Two Events):**
$$P(B|A) = \frac{P(A|B) \cdot P(B)}{P(A)}$$

Expanded using LOTP:
$$P(B|A) = \frac{P(A|B) \cdot P(B)}{P(A|B) \cdot P(B) + P(A|B^c) \cdot P(B^c)}$$

**Bayes' Theorem (Partition Form):** If $B_1, \ldots, B_n$ partition $\Omega$:
$$P(B_i|A) = \frac{P(A|B_i) \cdot P(B_i)}{\sum_{j=1}^{n} P(A|B_j) \cdot P(B_j)}$$

**Terminology (Medical Testing Context):**
- $P(B)$ = **prior** (probability before seeing data)
- $P(A|B)$ = **likelihood** (probability of data given hypothesis)
- $P(B|A)$ = **posterior** (updated probability after seeing data)
- **Sensitivity** = $P(+|\text{disease})$ = true positive rate
- **Specificity** = $P(-|\text{no disease})$ = true negative rate

---

### WORKED EXAMPLE 1 (Easy): Urn Selection

**Problem:** Urn 1 has 3 red and 2 blue balls. Urn 2 has 1 red and 4 blue balls. An urn is chosen uniformly at random and a ball is drawn; it's red. What's the probability it came from Urn 1?

**Key idea:** Use Bayes to find $P(U_1|R)$.

**Step 1:** Define events and priors.
- $U_1$ = Urn 1 chosen, $P(U_1) = 1/2$
- $U_2$ = Urn 2 chosen, $P(U_2) = 1/2$
- $R$ = red ball drawn

**Step 2:** Find likelihoods.
$$P(R|U_1) = \frac{3}{5}, \quad P(R|U_2) = \frac{1}{5}$$

**Step 3:** Apply Bayes' theorem.
$$P(U_1|R) = \frac{P(R|U_1) \cdot P(U_1)}{P(R|U_1) \cdot P(U_1) + P(R|U_2) \cdot P(U_2)}$$
$$= \frac{\frac{3}{5} \cdot \frac{1}{2}}{\frac{3}{5} \cdot \frac{1}{2} + \frac{1}{5} \cdot \frac{1}{2}}$$
$$= \frac{\frac{3}{10}}{\frac{3}{10} + \frac{1}{10}} = \frac{\frac{3}{10}}{\frac{4}{10}} = \frac{3}{4}$$

**Answer:** $\frac{3}{4}$

---

### WORKED EXAMPLE 2 (Exam-Style): Disease Testing

**Problem:** A disease affects 0.1% of the population. A test has 99% sensitivity (detects 99% of sick people) and 98% specificity (correctly identifies 98% of healthy people). If you test positive, what's the probability you have the disease?

**Key idea:** Classic Bayes problem; beware of low prior.

**Step 1:** Define events and prior.
- $D$ = has disease, $P(D) = 0.001$
- $D^c$ = healthy, $P(D^c) = 0.999$
- $+$ = tests positive

**Step 2:** Given information.
- Sensitivity: $P(+|D) = 0.99$
- Specificity: $P(-|D^c) = 0.98$, so $P(+|D^c) = 0.02$

**Step 3:** Apply Bayes' theorem.
$$P(D|+) = \frac{P(+|D) \cdot P(D)}{P(+|D) \cdot P(D) + P(+|D^c) \cdot P(D^c)}$$
$$= \frac{0.99 \times 0.001}{0.99 \times 0.001 + 0.02 \times 0.999}$$

**Step 4:** Compute numerator and denominator.
Numerator: $0.99 \times 0.001 = 0.00099$
Denominator: $0.00099 + 0.02 \times 0.999 = 0.00099 + 0.01998 = 0.02097$

**Step 5:** Divide.
$$P(D|+) = \frac{0.00099}{0.02097} \approx 0.0472$$

**Answer:** Approximately 4.72% (!)

**Insight:** Despite a very accurate test, the low prior (0.1%) means most positives are false positives.

---

### PRACTICE PROBLEMS

**P15.1** (Easy): $P(A) = 0.3, P(B|A) = 0.8, P(B|A^c) = 0.2$. Find $P(A|B)$.

**P15.2** (Medium): 40% of emails are spam. A spam filter marks 95% of spam as spam, and 5% of legitimate emails as spam. If an email is marked spam, what's the probability it's actually spam?

**P15.3** (Medium): Three coins: fair, two-headed, two-tailed. Pick one randomly and flip it. It shows heads. What's the probability it's the fair coin?

**P15.4** (Hard): A rare disease affects 1 in 10,000 people. A test has no false negatives (100% sensitivity) but 1% false positive rate (99% specificity). You test positive. What's the probability you have the disease?

**P15.5** (Hard): Box A: 4 red, 6 blue. Box B: 7 red, 3 blue. Choose a box with $P(A) = 0.6, P(B) = 0.4$. Draw 2 balls with replacement; both are red. What's the probability you chose Box A?

### SHORT ANSWERS

**A15.1:** $P(B) = 0.8(0.3) + 0.2(0.7) = 0.38$. $P(A|B) = \frac{0.8 \times 0.3}{0.38} = \frac{0.24}{0.38} = \frac{12}{19} \approx 0.632$

**A15.2:** Let $S$ = spam, $M$ = marked. $P(S|M) = \frac{0.95 \times 0.4}{0.95 \times 0.4 + 0.05 \times 0.6} = \frac{0.38}{0.38+0.03} = \frac{0.38}{0.41} \approx 0.927$

**A15.3:** $P(H|F) = 1/2, P(H|2H) = 1, P(H|2T) = 0$. $P(F|H) = \frac{(1/2)(1/3)}{(1/2)(1/3) + 1(1/3) + 0} = \frac{1/6}{1/6+1/3} = \frac{1/6}{1/2} = 1/3$

**A15.4:** $P(D|+) = \frac{1 \times 0.0001}{1 \times 0.0001 + 0.01 \times 0.9999} = \frac{0.0001}{0.010099} \approx 0.0099$ (~1%)

**A15.5:** $P(RR|A) = (4/10)^2 = 0.16$, $P(RR|B) = (7/10)^2 = 0.49$.
$P(A|RR) = \frac{0.16 \times 0.6}{0.16 \times 0.6 + 0.49 \times 0.4} = \frac{0.096}{0.096+0.196} = \frac{0.096}{0.292} \approx 0.329$

### FULL SOLUTIONS (P15.2 and P15.4)

**Full Solution P15.2:**

**Step 1:** Define events.
- $S$ = email is spam, $P(S) = 0.4$
- $L$ = email is legitimate, $P(L) = 0.6$
- $M$ = marked as spam

**Step 2:** Given conditional probabilities.
$$P(M|S) = 0.95$$ (sensitivity)
$$P(M|L) = 0.05$$ (false positive rate)

**Step 3:** Want $P(S|M)$; apply Bayes.
$$P(S|M) = \frac{P(M|S) \cdot P(S)}{P(M|S) \cdot P(S) + P(M|L) \cdot P(L)}$$

**Step 4:** Compute.
$$= \frac{0.95 \times 0.4}{0.95 \times 0.4 + 0.05 \times 0.6}$$
$$= \frac{0.38}{0.38 + 0.03} = \frac{0.38}{0.41}$$
$$\approx 0.927$$

**Answer:** 92.7%

---

**Full Solution P15.4:**

**Step 1:** Define events and prior.
- $D$ = has disease, $P(D) = 1/10000 = 0.0001$
- $P(D^c) = 0.9999$

**Step 2:** Test characteristics.
- Sensitivity: $P(+|D) = 1$ (no false negatives)
- Specificity: $P(-|D^c) = 0.99$, so $P(+|D^c) = 0.01$

**Step 3:** Apply Bayes.
$$P(D|+) = \frac{P(+|D) \cdot P(D)}{P(+|D) \cdot P(D) + P(+|D^c) \cdot P(D^c)}$$
$$= \frac{1 \times 0.0001}{1 \times 0.0001 + 0.01 \times 0.9999}$$

**Step 4:** Compute.
Numerator: $0.0001$
Denominator: $0.0001 + 0.009999 = 0.010099$

**Step 5:** Divide.
$$P(D|+) = \frac{0.0001}{0.010099} \approx 0.0099$$

**Answer:** Approximately 1%

**Insight:** Even with perfect sensitivity and 99% specificity, the extreme rarity (1 in 10,000) means ~99% of positives are false.

---

## IF YOU ONLY HAVE 10 MINUTES (Conditional Probability)

**Memorize these 3 things:**
1. **Conditional prob:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$; Multiplication: $P(A \cap B) = P(A) P(B|A)$
2. **LOTP:** $P(A) = P(A|B)P(B) + P(A|B^c)P(B^c)$ — break into cases
3. **Bayes:** $P(B|A) = \frac{P(A|B) P(B)}{P(A)}$ — flip the conditional

**Do these 2 practice problems:**
1. Two cards without replacement; $P(\text{both red}) = ?$ Answer: $(26/52)(25/51) = 25/102$
2. Disease 1%, test 90% sensitive, 95% specific. $P(D|+) = ?$ Answer: $\frac{0.9 \times 0.01}{0.9 \times 0.01 + 0.05 \times 0.99} = \frac{0.009}{0.0585} \approx 0.154$ (15.4%)

