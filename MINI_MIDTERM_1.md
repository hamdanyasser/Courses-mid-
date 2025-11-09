# MINI-MIDTERM #1
## Time: 60 minutes | Total Points: 100

**Instructions:**
- Closed book, closed notes
- Calculator permitted
- Show all work for partial credit
- Box your final answers
- Manage your time: ~6 minutes per question

---

## PROBLEM 1 (10 points): Basic Counting

A password consists of:
- 2 uppercase letters (A-Z)
- 3 digits (0-9)
- 1 special character from {!, @, #, $}

All positions are distinct (letters, then digits, then special character in that order).

**(a)** [5 pts] How many different passwords are possible?

**(b)** [5 pts] How many passwords have no repeated digits?

---

## PROBLEM 2 (12 points): Permutations and Combinations

**(a)** [4 pts] How many ways can 8 people be arranged in a line?

**(b)** [4 pts] How many ways can a committee of 4 be selected from 10 people?

**(c)** [4 pts] How many distinct arrangements are there of the letters in BOOKKEEPER?

---

## PROBLEM 3 (12 points): Stars and Bars

A bakery has 4 types of cookies. You want to buy 12 cookies.

**(a)** [6 pts] How many ways can you select 12 cookies if you can choose any mix (including all of one type)?

**(b)** [6 pts] How many ways if you must buy at least one cookie of each type?

---

## PROBLEM 4 (12 points): Inclusion-Exclusion

In a survey of 100 students:
- 45 study Mathematics
- 38 study Physics
- 32 study Chemistry
- 15 study both Math and Physics
- 12 study both Math and Chemistry
- 10 study both Physics and Chemistry
- 5 study all three subjects

**(a)** [6 pts] How many students study at least one of these subjects?

**(b)** [6 pts] How many students study exactly two of these subjects?

---

## PROBLEM 5 (10 points): Sample Spaces and Events

A fair six-sided die is rolled twice.

**(a)** [3 pts] How many outcomes are in the sample space?

**(b)** [4 pts] List all outcomes in the event "sum equals 8".

**(c)** [3 pts] What is $P(\text{sum} = 8)$?

---

## PROBLEM 6 (12 points): Probability Axioms and Properties

Let $A$ and $B$ be events with $P(A) = 0.6$, $P(B) = 0.5$, and $P(A \cap B) = 0.3$.

**(a)** [3 pts] Find $P(A^c)$.

**(b)** [4 pts] Find $P(A \cup B)$.

**(c)** [5 pts] Find $P(A^c \cap B)$.

---

## PROBLEM 7 (10 points): Conditional Probability

A box contains 5 red balls and 3 blue balls. Two balls are drawn sequentially without replacement.

**(a)** [5 pts] What is the probability both balls are red?

**(b)** [5 pts] Given that the first ball is red, what is the probability the second ball is blue?

---

## PROBLEM 8 (12 points): Law of Total Probability

A factory has two machines. Machine A produces 60% of the total output and has a 3% defect rate. Machine B produces 40% of the output and has a 5% defect rate.

**(a)** [7 pts] What is the probability a randomly selected product is defective?

**(b)** [5 pts] If a product is found to be defective, what is the probability it came from Machine A?

---

## PROBLEM 9 (10 points): Independence

Events $A$ and $B$ have $P(A) = 0.4$ and $P(B) = 0.5$.

**(a)** [3 pts] If $A$ and $B$ are independent, find $P(A \cap B)$.

**(b)** [4 pts] If $A$ and $B$ are independent, find $P(A \cup B)$.

**(c)** [3 pts] Can $A$ and $B$ be both independent and disjoint? Explain briefly.

---

## PROBLEM 10 (10 points): Birthday Problem

In a class of 30 students, assume birthdays are uniformly distributed over 365 days.

**(a)** [8 pts] What is the probability that at least two students share the same birthday? (Set up the calculation; you may leave in product form or use calculator)

**(b)** [2 pts] Would this probability be higher or lower with 40 students? (No calculation needed, just explain reasoning)

---

# MINI-MIDTERM #1: SOLUTIONS & RUBRIC

## PROBLEM 1 SOLUTION (10 points)

**Key idea:** Sequential independent choices → product rule.

**(a)** [5 pts]
- 2 uppercase letters: $26^2$ choices
- 3 digits: $10^3$ choices
- 1 special character: 4 choices

Total: $26^2 \times 10^3 \times 4 = 676 \times 1000 \times 4 = 2,704,000$

**Rubric:**
- [2 pts] Identify product rule applies
- [2 pts] Correct calculation of each component
- [1 pt] Correct final answer

**(b)** [5 pts]
- 2 uppercase letters: still $26^2$ (no restriction)
- 3 digits with no repeats: $10 \times 9 \times 8 = 720$
- 1 special character: 4

Total: $676 \times 720 \times 4 = 1,946,880$

**Rubric:**
- [2 pts] Recognize only digits have restriction
- [2 pts] Correct permutation calculation for digits
- [1 pt] Correct final answer

---

## PROBLEM 2 SOLUTION (12 points)

**(a)** [4 pts]
$8! = 40,320$

**Rubric:** [4 pts] Correct formula and answer (all or nothing)

**(b)** [4 pts]
$\binom{10}{4} = \frac{10!}{4! \cdot 6!} = \frac{10 \times 9 \times 8 \times 7}{24} = 210$

**Rubric:** [4 pts] Correct formula and answer

**(c)** [4 pts]
BOOKKEEPER: 10 letters total
- B: 1, O: 2, K: 2, E: 3, P: 1, R: 1

$$\frac{10!}{1! \cdot 2! \cdot 2! \cdot 3! \cdot 1! \cdot 1!} = \frac{3,628,800}{2 \times 2 \times 6} = \frac{3,628,800}{24} = 151,200$$

**Rubric:**
- [1 pt] Identify multiset permutation
- [2 pts] Correct letter counts
- [1 pt] Correct calculation

---

## PROBLEM 3 SOLUTION (12 points)

**Key idea:** Stars and bars (distributing identical cookies into distinct types).

**(a)** [6 pts]
$\binom{4+12-1}{12} = \binom{15}{12} = \binom{15}{3} = \frac{15 \times 14 \times 13}{6} = 455$

**Rubric:**
- [3 pts] Correct stars and bars formula
- [2 pts] Correct substitution
- [1 pt] Correct calculation

**(b)** [6 pts]
Give 1 cookie of each type first: $12 - 4 = 8$ cookies remain.
Distribute 8 cookies into 4 types:
$\binom{4+8-1}{8} = \binom{11}{8} = \binom{11}{3} = \frac{11 \times 10 \times 9}{6} = 165$

**Rubric:**
- [2 pts] Strategy: pre-allocate one per type
- [2 pts] Correct reduced problem (8 cookies)
- [2 pts] Correct calculation

---

## PROBLEM 4 SOLUTION (12 points)

**Key idea:** Inclusion-exclusion principle.

**(a)** [6 pts]
Let $M$ = Math, $P$ = Physics, $C$ = Chemistry.

$$|M \cup P \cup C| = |M| + |P| + |C| - |M \cap P| - |M \cap C| - |P \cap C| + |M \cap P \cap C|$$
$$= 45 + 38 + 32 - 15 - 12 - 10 + 5 = 115 - 37 + 5 = 83$$

**Rubric:**
- [2 pts] Write inclusion-exclusion formula
- [3 pts] Substitute correctly
- [1 pt] Correct arithmetic

**(b)** [6 pts]
Exactly two = (M∩P only) + (M∩C only) + (P∩C only)

- $|M \cap P| - |M \cap P \cap C| = 15 - 5 = 10$
- $|M \cap C| - |M \cap P \cap C| = 12 - 5 = 7$
- $|P \cap C| - |M \cap P \cap C| = 10 - 5 = 5$

Total: $10 + 7 + 5 = 22$

**Rubric:**
- [3 pts] Recognize need to subtract triple intersection from each pair
- [2 pts] Correct calculations for each
- [1 pt] Correct sum

---

## PROBLEM 5 SOLUTION (10 points)

**(a)** [3 pts]
$6 \times 6 = 36$

**Rubric:** [3 pts] Correct answer

**(b)** [4 pts]
Sum = 8: {(2,6), (3,5), (4,4), (5,3), (6,2)}

**Rubric:**
- [3 pts] All 5 outcomes listed
- [1 pt] No extras

**(c)** [3 pts]
$$P(\text{sum} = 8) = \frac{5}{36}$$

**Rubric:**
- [2 pts] Correct numerator (5)
- [1 pt] Correct denominator (36)

---

## PROBLEM 6 SOLUTION (12 points)

**(a)** [3 pts]
$P(A^c) = 1 - P(A) = 1 - 0.6 = 0.4$

**Rubric:** [3 pts] Correct formula and answer

**(b)** [4 pts]
$P(A \cup B) = P(A) + P(B) - P(A \cap B) = 0.6 + 0.5 - 0.3 = 0.8$

**Rubric:**
- [2 pts] Correct formula
- [2 pts] Correct calculation

**(c)** [5 pts]
Method 1: $P(A^c \cap B) = P(B) - P(A \cap B) = 0.5 - 0.3 = 0.2$

Method 2: $P(A^c \cap B) = P(B) \cdot P(A^c | B) = P(B) - P(A \cap B)$

**Rubric:**
- [3 pts] Correct approach
- [2 pts] Correct answer

---

## PROBLEM 7 SOLUTION (10 points)

**(a)** [5 pts]
$$P(\text{both red}) = \frac{5}{8} \times \frac{4}{7} = \frac{20}{56} = \frac{5}{14}$$

**Rubric:**
- [2 pts] First probability: 5/8
- [2 pts] Conditional second probability: 4/7
- [1 pt] Correct product

**(b)** [5 pts]
Given first is red, 4 red and 3 blue remain (7 total).
$$P(\text{2nd blue}|\text{1st red}) = \frac{3}{7}$$

**Rubric:**
- [3 pts] Correct reasoning about remaining balls
- [2 pts] Correct answer

---

## PROBLEM 8 SOLUTION (12 points)

**Key idea:** Law of total probability, then Bayes.

**(a)** [7 pts]
Let $D$ = defective, $A$ = from Machine A, $B$ = from Machine B.

$$P(D) = P(D|A) P(A) + P(D|B) P(B)$$
$$= 0.03 \times 0.6 + 0.05 \times 0.4$$
$$= 0.018 + 0.020 = 0.038$$

**Rubric:**
- [3 pts] Set up LOTP correctly
- [3 pts] Correct substitution
- [1 pt] Correct calculation

**(b)** [5 pts]
$$P(A|D) = \frac{P(D|A) P(A)}{P(D)} = \frac{0.018}{0.038} = \frac{18}{38} = \frac{9}{19} \approx 0.474$$

**Rubric:**
- [2 pts] Recognize Bayes' theorem
- [2 pts] Correct numerator (use result from part a)
- [1 pt] Correct calculation

---

## PROBLEM 9 SOLUTION (10 points)

**(a)** [3 pts]
$P(A \cap B) = P(A) \times P(B) = 0.4 \times 0.5 = 0.2$

**Rubric:** [3 pts] Correct

**(b)** [4 pts]
$P(A \cup B) = P(A) + P(B) - P(A \cap B) = 0.4 + 0.5 - 0.2 = 0.7$

**Rubric:**
- [2 pts] Use addition rule
- [2 pts] Correct answer

**(c)** [3 pts]
No (assuming both have positive probability). If disjoint, $P(A \cap B) = 0$, but independence requires $P(A \cap B) = 0.4 \times 0.5 = 0.2 \neq 0$.

**Rubric:**
- [2 pts] Answer "No"
- [1 pt] Correct reasoning

---

## PROBLEM 10 SOLUTION (10 points)

**(a)** [8 pts]
$$P(\text{at least 2 match}) = 1 - P(\text{all different})$$

$$P(\text{all different}) = \frac{365}{365} \times \frac{364}{365} \times \frac{363}{365} \times \cdots \times \frac{336}{365}$$

$$= \frac{365!/(365-30)!}{365^{30}} = \frac{P(365,30)}{365^{30}}$$

$$\approx 1 - 0.2937 \approx 0.706$$ (by calculator)

**Rubric:**
- [3 pts] Use complement
- [3 pts] Correct setup of "all different" probability
- [2 pts] Reasonable numerical answer (accept setup without final calculation)

**(b)** [2 pts]
Higher. More people means more pairs, hence higher chance of collision.

**Rubric:** [2 pts] Correct answer with brief reasoning

---

## GRADING SUMMARY

| Problem | Points | Topic |
|---------|--------|-------|
| 1 | 10 | Product rule |
| 2 | 12 | Permutations, combinations, multiset |
| 3 | 12 | Stars and bars |
| 4 | 12 | Inclusion-exclusion |
| 5 | 10 | Sample spaces |
| 6 | 12 | Probability properties |
| 7 | 10 | Conditional probability |
| 8 | 12 | LOTP and Bayes |
| 9 | 10 | Independence |
| 10 | 10 | Birthday problem |
| **Total** | **100** | |

**Time Management Tips:**
- Spend ~6 minutes per problem
- If stuck, move on and return later
- Show work even if unsure (partial credit!)
- Check that probabilities are between 0 and 1

