# 30 RANDOMIZED PROBLEM TEMPLATES

**Instructions:** Each template below has parameters in [brackets]. Fill in random values to generate new practice problems. Solutions use the generic parameters.

---

## COMBINATORICS TEMPLATES (1-15)

### Template 1: Product Rule - Passwords
**Problem:** A password consists of [A] letters followed by [B] digits followed by [C] special characters from a set of [D] options. How many passwords are possible?

**Parameters:** A = 2-4, B = 2-4, C = 1-2, D = 4-10

**Solution:** $26^A \times 10^B \times D^C$

**Example:** A=3, B=3, C=1, D=5 → $26^3 \times 10^3 \times 5 = 17,576 \times 1000 \times 5 = 87,880,000$

---

### Template 2: Permutations - Race
**Problem:** In a race with [N] runners, how many ways can the top [K] finishers be determined?

**Parameters:** N = 8-15, K = 3-5

**Solution:** $P(N,K) = \frac{N!}{(N-K)!}$

**Example:** N=10, K=3 → $P(10,3) = 10 \times 9 \times 8 = 720$

---

### Template 3: Combinations - Committee
**Problem:** From a group of [M] men and [W] women, select a committee of [K] people. How many ways?

**Parameters:** M = 5-8, W = 4-7, K = 3-6 (where K ≤ M+W)

**Solution:** $\binom{M+W}{K}$

**Example:** M=6, W=4, K=5 → $\binom{10}{5} = 252$

---

### Template 4: Combinations with Constraint
**Problem:** From [M] men and [W] women, form a committee of [K] people with exactly [X] women. How many ways?

**Parameters:** M = 5-8, W = 4-7, K = 4-6, X = 1 to K-1

**Solution:** $\binom{W}{X} \times \binom{M}{K-X}$

**Example:** M=6, W=5, K=5, X=3 → $\binom{5}{3} \times \binom{6}{2} = 10 \times 15 = 150$

---

### Template 5: Circular Permutations
**Problem:** How many ways can [N] people sit around a circular table?

**Parameters:** N = 4-10

**Solution:** $(N-1)!$

**Example:** N=7 → $6! = 720$

---

### Template 6: Multiset Permutations
**Problem:** How many distinct arrangements of the word [WORD]?

**Parameters:** Choose words with repeated letters:
- TENNESSEE (9 letters: T-1, E-4, N-2, S-2)
- REFEREE (7 letters: R-2, E-4, F-1)
- COMMITTEE (9 letters: C-1, O-1, M-2, I-1, T-2, E-2)

**Solution:** $\frac{n!}{\prod n_i!}$ where $n_i$ are the counts

**Example:** REFEREE → $\frac{7!}{2! \cdot 4! \cdot 1!} = \frac{5040}{2 \cdot 24} = 105$

---

### Template 7: Stars and Bars - Basic
**Problem:** How many ways to distribute [R] identical objects into [N] distinct boxes?

**Parameters:** R = 8-15, N = 3-6

**Solution:** $\binom{N+R-1}{R}$

**Example:** R=10, N=4 → $\binom{13}{10} = \binom{13}{3} = 286$

---

### Template 8: Stars and Bars - At Least One Each
**Problem:** Distribute [R] identical cookies to [N] children such that each gets at least one. How many ways?

**Parameters:** R = 10-20, N = 3-6, ensure R > N

**Solution:** $\binom{R-1}{N-1}$ (or equivalently $\binom{R-1}{R-N}$)

**Example:** R=12, N=4 → $\binom{11}{3} = 165$

---

### Template 9: Integer Solutions
**Problem:** How many non-negative integer solutions to $x_1 + x_2 + \cdots + x_k = n$?

**Parameters:** k = 3-5, n = 8-15

**Solution:** $\binom{n+k-1}{n}$ or $\binom{n+k-1}{k-1}$

**Example:** k=4, n=10 → $\binom{13}{10} = 286$

---

### Template 10: Inclusion-Exclusion - Divisibility
**Problem:** How many integers from 1 to [N] are divisible by [A] or [B]?

**Parameters:** N = 100-1000, A = 2-7, B = 2-7 (A ≠ B)

**Solution:** $\lfloor N/A \rfloor + \lfloor N/B \rfloor - \lfloor N/\text{lcm}(A,B) \rfloor$

**Example:** N=500, A=3, B=5 → $166 + 100 - 33 = 233$

---

### Template 11: Inclusion-Exclusion - Three Sets
**Problem:** Survey of [N] students: [A] study Math, [B] study Physics, [C] study Chemistry. [AB] study both Math & Physics, [AC] study both Math & Chemistry, [BC] study both Physics & Chemistry, [ABC] study all three. How many study at least one subject?

**Parameters:** N=100-200, choose consistent values

**Solution:** $A + B + C - AB - AC - BC + ABC$

**Example:** A=50, B=40, C=35, AB=15, AC=12, BC=10, ABC=5
→ $50+40+35-15-12-10+5 = 93$

---

### Template 12: Derangements
**Problem:** [N] people check their hats. Hats returned randomly. What's the probability no one gets their own hat?

**Parameters:** N = 3-7

**Solution:** $\frac{D_N}{N!}$ where $D_N = N! \sum_{i=0}^{N} \frac{(-1)^i}{i!}$

**Example:** N=5 → $D_5 = 44$, so $P = 44/120 = 11/30$

---

### Template 13: Pigeonhole - Basic
**Problem:** Show that among [N] integers, at least two have the same remainder when divided by [K].

**Parameters:** N = K+1 to K+5, K = 5-12

**Solution:** By pigeonhole: N integers, K remainders → at least $\lceil N/K \rceil$ share a remainder.

**Example:** N=13, K=12 → At least 2 share a remainder.

---

### Template 14: Binomial Coefficient
**Problem:** Find the coefficient of $x^k$ in the expansion of $(1+x)^n$.

**Parameters:** n = 8-15, k = 2 to n-2

**Solution:** $\binom{n}{k}$

**Example:** n=10, k=4 → $\binom{10}{4} = 210$

---

### Template 15: Multinomial Coefficient
**Problem:** Divide [N] items into [K] groups of sizes [n₁], [n₂], ..., [nₖ] where $\sum n_i = N$. How many ways?

**Parameters:** N=10-15, K=3-4, choose sizes summing to N

**Solution:** $\binom{N}{n_1, n_2, \ldots, n_k} = \frac{N!}{n_1! n_2! \cdots n_k!}$

**Example:** N=12, groups of 5,4,3 → $\frac{12!}{5! 4! 3!} = 27,720$

---

## PROBABILITY TEMPLATES (16-30)

### Template 16: Uniform Probability - Dice
**Problem:** Roll [N] fair dice. What is the probability the sum equals [S]?

**Parameters:** N = 2-3, S depends on N (for N=2, S=2-12; for N=3, S=3-18)

**Solution:** Count favorable outcomes / $6^N$

**Example:** N=2, S=7 → 6 ways / 36 = 1/6

---

### Template 17: Uniform Probability - Cards
**Problem:** Deal [K] cards from a standard deck. What is $P(\text{exactly } X \text{ aces})$?

**Parameters:** K = 5-7, X = 0 to 4

**Solution:** $\frac{\binom{4}{X} \binom{48}{K-X}}{\binom{52}{K}}$

**Example:** K=5, X=2 → $\frac{\binom{4}{2}\binom{48}{3}}{\binom{52}{5}} = \frac{6 \times 17296}{2598960}$

---

### Template 18: Complement - At Least One
**Problem:** Flip [N] fair coins. What is $P(\text{at least one head})$?

**Parameters:** N = 5-12

**Solution:** $1 - (1/2)^N$

**Example:** N=8 → $1 - 1/256 = 255/256$

---

### Template 19: Addition Rule
**Problem:** Events A and B have $P(A) = [p_A]$, $P(B) = [p_B]$, $P(A \cap B) = [p_{AB}]$. Find $P(A \cup B)$.

**Parameters:** Choose $0 < p_A, p_B < 1$ and $p_{AB} \leq \min(p_A, p_B)$

**Solution:** $p_A + p_B - p_{AB}$

**Example:** $p_A=0.6, p_B=0.5, p_{AB}=0.3$ → $0.6+0.5-0.3=0.8$

---

### Template 20: Conditional Probability - Urn
**Problem:** An urn has [R] red and [B] blue balls. Draw [K] balls without replacement. What is $P(\text{all red})$?

**Parameters:** R = 4-8, B = 3-6, K = 2-3 (K ≤ R)

**Solution:** $\frac{R}{R+B} \times \frac{R-1}{R+B-1} \times \cdots$ (K factors)

**Example:** R=5, B=3, K=2 → $\frac{5}{8} \times \frac{4}{7} = \frac{20}{56} = \frac{5}{14}$

---

### Template 21: Conditional Probability - Given Information
**Problem:** $P(A) = [p_A]$, $P(B) = [p_B]$, $P(A \cap B) = [p_{AB}]$. Find $P(A|B)$.

**Parameters:** Choose consistent values

**Solution:** $\frac{p_{AB}}{p_B}$

**Example:** $p_A=0.6, p_B=0.5, p_{AB}=0.3$ → $P(A|B) = 0.3/0.5 = 0.6$

---

### Template 22: Law of Total Probability - Two Machines
**Problem:** Machine A produces [P_A]% of output with [D_A]% defect rate. Machine B produces [P_B]% with [D_B]% defect rate. What fraction of all products are defective?

**Parameters:** P_A + P_B = 100, D_A and D_B between 1-10

**Solution:** $\frac{P_A}{100} \times \frac{D_A}{100} + \frac{P_B}{100} \times \frac{D_B}{100}$

**Example:** P_A=60, D_A=3, P_B=40, D_B=5 → $0.6 \times 0.03 + 0.4 \times 0.05 = 0.038$

---

### Template 23: Bayes' Theorem - Disease Testing
**Problem:** Disease prevalence [PREV]%. Test has [SENS]% sensitivity and [SPEC]% specificity. If test positive, what's $P(\text{disease})$?

**Parameters:** PREV = 0.1-5, SENS = 90-99, SPEC = 85-99

**Solution:** $\frac{\text{SENS} \times \text{PREV}}{\text{SENS} \times \text{PREV} + (100-\text{SPEC}) \times (100-\text{PREV})}$ (convert to decimals)

**Example:** PREV=1, SENS=95, SPEC=90
→ $\frac{0.95 \times 0.01}{0.95 \times 0.01 + 0.10 \times 0.99} = \frac{0.0095}{0.1085} \approx 0.0876$

---

### Template 24: Bayes - Urn Selection
**Problem:** Urn 1 has [R1] red, [B1] blue. Urn 2 has [R2] red, [B2] blue. Pick urn uniformly, draw a ball; it's red. $P(\text{Urn 1})$?

**Parameters:** R1, B1, R2, B2 = 2-6 each

**Solution:** $\frac{\frac{R1}{R1+B1}}{\frac{R1}{R1+B1} + \frac{R2}{R2+B2}} \times \frac{1}{1}$ (since urns chosen uniformly)

Simplify: $\frac{R1(R2+B2)}{R1(R2+B2) + R2(R1+B1)}$

**Example:** R1=3, B1=2, R2=1, B2=4
→ $\frac{(3/5)}{(3/5)+(1/5)} = \frac{3/5}{4/5} = 3/4$

---

### Template 25: Independence - Check
**Problem:** $P(A) = [p_A]$, $P(B) = [p_B]$, $P(A \cap B) = [p_{AB}]$. Are A and B independent?

**Parameters:** Choose values; sometimes make $p_{AB} = p_A \times p_B$, sometimes not

**Solution:** Check if $p_{AB} = p_A \times p_B$

**Example:** $p_A=0.5, p_B=0.4, p_{AB}=0.2$ → Yes, $0.5 \times 0.4 = 0.2$ ✓

---

### Template 26: Independence - Multiple Trials
**Problem:** A coin has $P(H) = [p]$. Flip [N] times independently. $P(\text{at least one head})$?

**Parameters:** p = 0.3-0.7, N = 4-8

**Solution:** $1 - (1-p)^N$

**Example:** p=0.6, N=5 → $1 - 0.4^5 = 1 - 0.01024 = 0.98976$

---

### Template 27: Series System Reliability
**Problem:** System has [N] components in series (all must work). Each works independently with probability [p]. What is $P(\text{system works})$?

**Parameters:** N = 3-5, p = 0.7-0.95

**Solution:** $p^N$

**Example:** N=4, p=0.9 → $0.9^4 = 0.6561$

---

### Template 28: Parallel System Reliability
**Problem:** System has [N] components in parallel (at least one must work). Each works independently with probability [p]. What is $P(\text{system works})$?

**Parameters:** N = 2-4, p = 0.6-0.9

**Solution:** $1 - (1-p)^N$

**Example:** N=3, p=0.8 → $1 - 0.2^3 = 1 - 0.008 = 0.992$

---

### Template 29: Birthday Problem
**Problem:** In a room of [N] people, what is the probability at least two share a birthday? (Assume 365 days)

**Parameters:** N = 15-40

**Solution:** $1 - \frac{365!/(365-N)!}{365^N}$

**Example:** N=30 → $1 - \frac{P(365,30)}{365^{30}} \approx 0.706$

---

### Template 30: Conditional Independence
**Problem:** Events A, B with $P(A|C) = [p_A]$, $P(B|C) = [p_B]$. If A and B are conditionally independent given C, find $P(A \cap B | C)$.

**Parameters:** p_A, p_B between 0.2-0.8

**Solution:** $p_A \times p_B$

**Example:** $p_A=0.6, p_B=0.5$ → $P(A \cap B|C) = 0.3$

---

# USING THESE TEMPLATES

**Quick Practice Session (30 min):**
1. Pick 5 random templates
2. Generate parameters (use dice/random numbers)
3. Solve each problem
4. Check solution against template formula

**Full Practice Drill (2 hours):**
1. Generate all 30 problems with random parameters
2. Solve in timed conditions (4 min each)
3. Grade yourself
4. Review mistakes

**Custom Exam Creation:**
- Select 10 templates covering different topics
- Generate specific problems
- Solve as a practice test
- This creates infinite practice exams!

