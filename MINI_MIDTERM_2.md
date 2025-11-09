# MINI-MIDTERM #2
## Time: 60 minutes | Total Points: 100

**Instructions:**
- Closed book, closed notes
- Calculator permitted
- Show all work for partial credit
- Box your final answers
- Manage your time: ~6 minutes per question

---

## PROBLEM 1 (10 points): Combinations and Binomial Coefficient

**(a)** [4 pts] Compute $\binom{8}{3}$.

**(b)** [6 pts] A committee of 5 is selected from 6 men and 4 women. How many committees have exactly 3 men and 2 women?

---

## PROBLEM 2 (12 points): Circular Permutations and Derangements

**(a)** [6 pts] How many ways can 7 people be seated around a circular table?

**(b)** [6 pts] Four letters are placed randomly into four addressed envelopes (one per envelope). What is the probability that no letter is in the correct envelope?

---

## PROBLEM 3 (10 points): Pigeonhole Principle

**(a)** [5 pts] If 8 people are in a room, show that at least two were born on the same day of the week.

**(b)** [5 pts] How many integers from {1, 2, 3, ..., 20} must you select to guarantee that two of them differ by exactly 5?

---

## PROBLEM 4 (12 points): Uniform Probability Model

A standard deck of 52 cards is shuffled and 5 cards are dealt.

**(a)** [6 pts] What is the probability of getting exactly 3 Kings?

**(b)** [6 pts] What is the probability of getting a full house (3 of one rank, 2 of another)?

---

## PROBLEM 5 (12 points): Complement and Addition Rules

A fair die is rolled.

**(a)** [4 pts] What is the probability of rolling a number greater than 2?

**(b)** [4 pts] What is the probability of rolling an even number OR a number greater than 4?

**(c)** [4 pts] Events $A$ and $B$ satisfy $P(A) = 0.7, P(B) = 0.6$. What are the maximum and minimum possible values of $P(A \cap B)$?

---

## PROBLEM 6 (10 points): Conditional Probability and Chain Rule

Three cards are drawn from a standard deck without replacement.

**(a)** [6 pts] What is the probability all three are hearts?

**(b)** [4 pts] Given that the first card is a heart, what is the probability that exactly two of the three cards are hearts?

---

## PROBLEM 7 (12 points): Law of Total Probability (Tree)

Urn A contains 4 red and 2 blue balls. Urn B contains 3 red and 3 blue balls. A fair coin is flipped. If heads, draw from Urn A. If tails, draw from Urn B.

**(a)** [4 pts] Draw a probability tree for this experiment.

**(b)** [4 pts] What is the probability of drawing a red ball?

**(c)** [4 pts] Given that a red ball was drawn, what is the probability it came from Urn A?

---

## PROBLEM 8 (12 points): Bayes' Theorem

A screening test for a disease has 95% sensitivity (detects 95% of those with disease) and 90% specificity (correctly identifies 90% of those without disease). The disease prevalence is 2%.

**(a)** [6 pts] If a person tests positive, what is the probability they have the disease?

**(b)** [6 pts] If a person tests negative, what is the probability they do NOT have the disease?

---

## PROBLEM 9 (12 points): Independence and System Reliability

A system consists of three independent components in parallel (system works if at least one component works). Each component works with probability 0.8.

**(a)** [4 pts] What is the probability all three components fail?

**(b)** [4 pts] What is the probability the system works?

**(c)** [4 pts] Given that the system works, what is the probability that exactly two components are working?

---

## PROBLEM 10 (8 points): Multiple Events and Independence

Roll two fair dice independently.

**(a)** [4 pts] What is the probability that the first die shows a 6 AND the sum is 8?

**(b)** [4 pts] Are the events "first die is 6" and "sum is 7" independent? Justify your answer with calculations.

---

# MINI-MIDTERM #2: SOLUTIONS & RUBRIC

## PROBLEM 1 SOLUTION (10 points)

**(a)** [4 pts]
$$\binom{8}{3} = \frac{8!}{3! \cdot 5!} = \frac{8 \times 7 \times 6}{3 \times 2 \times 1} = \frac{336}{6} = 56$$

**Rubric:** [4 pts] Correct calculation (all or nothing)

**(b)** [6 pts]
- Choose 3 men from 6: $\binom{6}{3} = 20$
- Choose 2 women from 4: $\binom{4}{2} = 6$
- Total: $20 \times 6 = 120$

**Rubric:**
- [2 pts] Choose men: $\binom{6}{3}$
- [2 pts] Choose women: $\binom{4}{2}$
- [2 pts] Multiply correctly

---

## PROBLEM 2 SOLUTION (12 points)

**(a)** [6 pts]
$(7-1)! = 6! = 720$

**Rubric:**
- [3 pts] Use circular permutation formula
- [3 pts] Correct calculation

**(b)** [6 pts]
Use derangement formula:
$$D_4 = 4! \sum_{i=0}^{4} \frac{(-1)^i}{i!} = 24 \left(1 - 1 + \frac{1}{2} - \frac{1}{6} + \frac{1}{24}\right)$$
$$= 24 \times \frac{9}{24} = 9$$

Total arrangements: $4! = 24$

$$P(\text{no match}) = \frac{9}{24} = \frac{3}{8}$$

**Rubric:**
- [2 pts] Recognize derangement problem
- [2 pts] Calculate $D_4 = 9$
- [2 pts] Correct probability

---

## PROBLEM 3 SOLUTION (10 points)

**(a)** [5 pts]
There are 7 days of the week. With 8 people, by pigeonhole principle, at least $\lceil 8/7 \rceil = 2$ people share the same day of the week.

**Rubric:**
- [3 pts] Identify 7 "boxes" (days)
- [2 pts] Apply pigeonhole correctly

**(b)** [5 pts]
Partition {1,...,20} into pairs that differ by 5:
- {1,6}, {2,7}, {3,8}, {4,9}, {5,10}, {6,11}, {7,12}, {8,13}, {9,14}, {10,15}, {11,16}, {12,17}, {13,18}, {14,19}, {15,20}

Wait, this overcounts. Better partition:
- {1,6,11,16}, {2,7,12,17}, {3,8,13,18}, {4,9,14,19}, {5,10,15,20}

These are 5 "chains". If we select 6 numbers, by pigeonhole, two come from the same chain. Adjacent elements in a chain differ by 5.

Actually, simpler: consider pairs: {1,6}, {2,7}, ..., {15,20}. That's 15 pairs plus {16,17,18,19,20} left over. Actually this is getting complex.

Better approach: Partition into sets where no two differ by 5:
$A = \{1,2,3,4,5\}$ and $B = \{6,7,8,9,10\}$ cannot both be selected without a pair differing by 5.

Actually, the answer is 11. If we choose numbers $\{1,2,3,4,5,11,12,13,14,15\}$ (10 numbers), no two differ by 5. But adding any 11th forces a collision.

**Rubric:**
- [3 pts] Reasonable approach
- [2 pts] Answer of 11 (accept reasonable justification)

---

## PROBLEM 4 SOLUTION (12 points)

**(a)** [6 pts]
Total hands: $\binom{52}{5}$

Favorable: Choose 3 Kings from 4, and 2 non-Kings from 48.
$$\binom{4}{3} \times \binom{48}{2} = 4 \times 1128 = 4512$$

$$P = \frac{4512}{\binom{52}{5}} = \frac{4512}{2598960} = \frac{94}{54145} \approx 0.00174$$

**Rubric:**
- [2 pts] Total hands correct
- [3 pts] Favorable hands correct
- [1 pt] Correct probability

**(b)** [6 pts]
Choose the rank for trips: 13 ways
Choose 3 cards from that rank: $\binom{4}{3} = 4$
Choose the rank for pair: 12 ways (different from trips)
Choose 2 cards from that rank: $\binom{4}{2} = 6$

Total: $13 \times 4 \times 12 \times 6 = 3744$

$$P = \frac{3744}{2598960} = \frac{6}{4165} \approx 0.00144$$

**Rubric:**
- [4 pts] Correct counting of full houses
- [2 pts] Correct probability

---

## PROBLEM 5 SOLUTION (12 points)

**(a)** [4 pts]
Greater than 2: {3, 4, 5, 6}
$$P = \frac{4}{6} = \frac{2}{3}$$

**Rubric:** [4 pts] Correct

**(b)** [4 pts]
$A$ = even = {2,4,6}, $P(A) = 1/2$
$B$ = greater than 4 = {5,6}, $P(B) = 1/3$
$A \cap B$ = {6}, $P(A \cap B) = 1/6$

$$P(A \cup B) = \frac{1}{2} + \frac{1}{3} - \frac{1}{6} = \frac{3+2-1}{6} = \frac{4}{6} = \frac{2}{3}$$

**Rubric:**
- [2 pts] Identify sets and probabilities
- [2 pts] Correct addition rule calculation

**(c)** [4 pts]
Minimum: By Bonferroni, $P(A \cap B) \geq P(A) + P(B) - 1 = 0.7 + 0.6 - 1 = 0.3$

Maximum: $P(A \cap B) \leq \min(P(A), P(B)) = \min(0.7, 0.6) = 0.6$

**Rubric:**
- [2 pts] Correct minimum
- [2 pts] Correct maximum

---

## PROBLEM 6 SOLUTION (10 points)

**(a)** [6 pts]
$$P = \frac{13}{52} \times \frac{12}{51} \times \frac{11}{50} = \frac{13 \times 12 \times 11}{52 \times 51 \times 50} = \frac{1716}{132600} = \frac{11}{850}$$

**Rubric:**
- [2 pts] Each conditional probability
- [2 pts] Multiply correctly

**(b)** [4 pts]
Given first is heart. Need exactly 2 total hearts means exactly 1 more heart in next 2 cards.

Remaining: 12 hearts, 39 non-hearts (51 total).

$P(\text{exactly 1 more heart}) = P(H, NH) + P(NH, H)$
$$= \frac{12}{51} \times \frac{39}{50} + \frac{39}{51} \times \frac{12}{50}$$
$$= 2 \times \frac{12 \times 39}{51 \times 50} = \frac{936}{2550} = \frac{156}{425}$$

**Rubric:**
- [2 pts] Recognize two cases
- [2 pts] Correct calculation

---

## PROBLEM 7 SOLUTION (12 points)

**(a)** [4 pts]

```
      Start
       / \
   [1/2] [1/2]
     /     \
    H       T
   / \     / \
 [2/3][1/3][1/2][1/2]
  R   B   R    B
```

**Rubric:** [4 pts] Correct tree structure with all probabilities

**(b)** [4 pts]
$$P(R) = P(R|H) P(H) + P(R|T) P(T)$$
$$= \frac{4}{6} \times \frac{1}{2} + \frac{3}{6} \times \frac{1}{2}$$
$$= \frac{2}{6} + \frac{3}{12} = \frac{1}{3} + \frac{1}{4} = \frac{7}{12}$$

Wait: $P(R|A) = 4/6 = 2/3$, $P(R|B) = 3/6 = 1/2$

$$P(R) = \frac{2}{3} \times \frac{1}{2} + \frac{1}{2} \times \frac{1}{2} = \frac{1}{3} + \frac{1}{4} = \frac{7}{12}$$

**Rubric:**
- [2 pts] LOTP setup
- [2 pts] Correct calculation

**(c)** [4 pts]
$$P(A|R) = \frac{P(R|A) P(A)}{P(R)} = \frac{(2/3)(1/2)}{7/12} = \frac{1/3}{7/12} = \frac{12}{21} = \frac{4}{7}$$

**Rubric:**
- [2 pts] Apply Bayes
- [2 pts] Correct answer

---

## PROBLEM 8 SOLUTION (12 points)

**(a)** [6 pts]
$D$ = disease, $P(D) = 0.02$
$P(+|D) = 0.95$, $P(+|D^c) = 0.10$

$$P(D|+) = \frac{0.95 \times 0.02}{0.95 \times 0.02 + 0.10 \times 0.98}$$
$$= \frac{0.019}{0.019 + 0.098} = \frac{0.019}{0.117} \approx 0.162$$

**Rubric:**
- [3 pts] Setup Bayes correctly
- [3 pts] Correct calculation

**(b)** [6 pts]
$P(-|D) = 0.05$, $P(-|D^c) = 0.90$

$$P(D^c|-) = \frac{P(-|D^c) P(D^c)}{P(-|D) P(D) + P(-|D^c) P(D^c)}$$
$$= \frac{0.90 \times 0.98}{0.05 \times 0.02 + 0.90 \times 0.98}$$
$$= \frac{0.882}{0.001 + 0.882} = \frac{0.882}{0.883} \approx 0.999$$

**Rubric:**
- [3 pts] Setup correctly
- [3 pts] Correct calculation

---

## PROBLEM 9 SOLUTION (12 points)

**(a)** [4 pts]
$$P(\text{all fail}) = 0.2^3 = 0.008$$

**Rubric:** [4 pts] Correct

**(b)** [4 pts]
$$P(\text{system works}) = 1 - P(\text{all fail}) = 1 - 0.008 = 0.992$$

**Rubric:** [4 pts] Correct

**(c)** [4 pts]
Need exactly 2 work and 1 fails.
$$P(\text{exactly 2 work}) = \binom{3}{2} (0.8)^2 (0.2)^1 = 3 \times 0.64 \times 0.2 = 0.384$$

Given system works:
$$P(\text{exactly 2 work}|\text{system works}) = \frac{0.384}{0.992} = \frac{0.384}{0.992} \approx 0.387$$

**Rubric:**
- [2 pts] Calculate $P(\text{exactly 2 work})$
- [2 pts] Divide by $P(\text{system works})$

---

## PROBLEM 10 SOLUTION (8 points)

**(a)** [4 pts]
First die = 6 AND sum = 8 means second die = 2.
$$P = \frac{1}{6} \times \frac{1}{6} = \frac{1}{36}$$

**Rubric:** [4 pts] Correct

**(b)** [4 pts]
$A$ = first die is 6, $P(A) = 1/6$
$B$ = sum is 7, $P(B) = 6/36 = 1/6$
$A \cap B$ = first is 6 and sum is 7 = {(6,1)}, $P(A \cap B) = 1/36$

Check: $P(A) P(B) = \frac{1}{6} \times \frac{1}{6} = \frac{1}{36} = P(A \cap B)$

YES, independent.

**Rubric:**
- [2 pts] Calculate all three probabilities
- [2 pts] Correct conclusion with justification

---

## GRADING SUMMARY

| Problem | Points | Topic |
|---------|--------|-------|
| 1 | 10 | Combinations |
| 2 | 12 | Circular perm, derangements |
| 3 | 10 | Pigeonhole |
| 4 | 12 | Uniform model, cards |
| 5 | 12 | Complement, addition, bounds |
| 6 | 10 | Conditional probability |
| 7 | 12 | Trees, LOTP, Bayes |
| 8 | 12 | Bayes (medical) |
| 9 | 12 | Independence, reliability |
| 10 | 8 | Independence checking |
| **Total** | **100** | |

