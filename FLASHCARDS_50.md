# 50 FLASHCARD PROMPTS (Grouped by Topic)

## COUNTING BASICS (Cards 1-5)

**Card 1**
Q: State the Product Rule.
A: If task 1 has $n_1$ outcomes and task 2 has $n_2$ outcomes (independent), total outcomes = $n_1 \times n_2$.

**Card 2**
Q: State the Sum Rule.
A: If method 1 has $n_1$ outcomes and method 2 has $n_2$ outcomes (mutually exclusive), total = $n_1 + n_2$.

**Card 3**
Q: When do you multiply counts vs add counts?
A: Multiply for sequential independent choices (AND). Add for mutually exclusive alternatives (OR).

**Card 4**
Q: A password has 4 letters then 3 digits. How many passwords?
A: $26^4 \times 10^3 = 456,976 \times 1,000 = 456,976,000$

**Card 5**
Q: Quick check: Does order matter in this problem?
A: Ask: "If I swap two items, is it different?" YES → Permutation. NO → Combination.

---

## PERMUTATIONS (Cards 6-10)

**Card 6**
Q: Formula for $P(n,r)$ (permutations of $r$ from $n$)?
A: $P(n,r) = \frac{n!}{(n-r)!} = n(n-1)(n-2)\cdots(n-r+1)$

**Card 7**
Q: How many ways to arrange 5 books on a shelf?
A: $5! = 120$

**Card 8**
Q: Formula for circular permutations of $n$ distinct objects?
A: $(n-1)!$

**Card 9**
Q: How many distinct arrangements of MISSISSIPPI?
A: $\frac{11!}{1! \cdot 4! \cdot 4! \cdot 2!} = 34,650$

**Card 10**
Q: When to use multiset permutation formula?
A: When arranging objects with repetitions (e.g., letters in a word with repeated letters).

---

## COMBINATIONS (Cards 11-15)

**Card 11**
Q: Formula for $\binom{n}{r}$?
A: $\binom{n}{r} = \frac{n!}{r!(n-r)!}$

**Card 12**
Q: What is $\binom{n}{r}$ in words?
A: "n choose r" — number of ways to select $r$ objects from $n$ when order doesn't matter.

**Card 13**
Q: State the symmetry property of binomial coefficients.
A: $\binom{n}{r} = \binom{n}{n-r}$

**Card 14**
Q: What are $\binom{n}{0}$ and $\binom{n}{n}$?
A: Both equal 1.

**Card 15**
Q: How many 5-card hands from 52 cards?
A: $\binom{52}{5} = 2,598,960$

---

## STARS AND BARS (Cards 16-20)

**Card 16**
Q: Stars and bars formula for distributing $r$ identical items into $n$ bins?
A: $\binom{n+r-1}{r}$ or equivalently $\binom{n+r-1}{n-1}$

**Card 17**
Q: Common mistake with stars and bars?
A: Writing $\binom{n+r}{r}$ instead of $\binom{n+r-1}{r}$. Remember: it's $n+r-1$!

**Card 18**
Q: 10 identical cookies, 4 types. How many ways to select?
A: $\binom{4+10-1}{10} = \binom{13}{10} = \binom{13}{3} = 286$

**Card 19**
Q: How to handle "at least 1 per bin" constraint in stars and bars?
A: Give 1 to each bin first, then distribute the remaining using stars and bars.

**Card 20**
Q: How many non-negative integer solutions to $x_1 + x_2 + x_3 = 10$?
A: $\binom{3+10-1}{10} = \binom{12}{10} = 66$

---

## INCLUSION-EXCLUSION (Cards 21-25)

**Card 21**
Q: Formula for $|A \cup B|$?
A: $|A \cup B| = |A| + |B| - |A \cap B|$

**Card 22**
Q: What's the pattern in inclusion-exclusion signs?
A: Alternating: + singles, - pairs, + triples, - quadruples, ...

**Card 23**
Q: Derangement formula for $D_n$?
A: $D_n = n! \sum_{i=0}^{n} \frac{(-1)^i}{i!}$, approximately $n!/e$ for large $n$.

**Card 24**
Q: What is $D_4$ (4 letters in 4 envelopes, none correct)?
A: $D_4 = 9$

**Card 25**
Q: What fraction of permutations are derangements (large $n$)?
A: Approximately $1/e \approx 0.368$ or 36.8%.

---

## PIGEONHOLE (Cards 26-28)

**Card 26**
Q: State the simple pigeonhole principle.
A: If $n+1$ objects go into $n$ boxes, at least one box has $\geq 2$ objects.

**Card 27**
Q: State the generalized pigeonhole principle.
A: If $n$ objects go into $k$ boxes, at least one box has $\geq \lceil n/k \rceil$ objects.

**Card 28**
Q: Why must 2 of 13 people share a birth month?
A: 13 people, 12 months. By pigeonhole: $\lceil 13/12 \rceil = 2$.

---

## PROBABILITY AXIOMS (Cards 29-33)

**Card 29**
Q: State Kolmogorov's three axioms.
A: (1) $P(A) \geq 0$, (2) $P(\Omega) = 1$, (3) $P(A_1 \cup A_2 \cup \cdots) = \sum P(A_i)$ for disjoint events.

**Card 30**
Q: Complement rule formula?
A: $P(A^c) = 1 - P(A)$

**Card 31**
Q: Addition rule for $P(A \cup B)$?
A: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

**Card 32**
Q: What is the union bound (Boole's inequality)?
A: $P(A_1 \cup \cdots \cup A_n) \leq P(A_1) + \cdots + P(A_n)$

**Card 33**
Q: If $A \subseteq B$, what can we say about $P(A)$ and $P(B)$?
A: $P(A) \leq P(B)$ (monotonicity)

---

## CONDITIONAL PROBABILITY (Cards 34-38)

**Card 34**
Q: Definition of $P(A|B)$?
A: $P(A|B) = \frac{P(A \cap B)}{P(B)}$ for $P(B) > 0$

**Card 35**
Q: Multiplication rule (product rule)?
A: $P(A \cap B) = P(A) \cdot P(B|A) = P(B) \cdot P(A|B)$

**Card 36**
Q: Is $P(A|B) = P(B|A)$ in general?
A: NO! These are usually different. Use Bayes to convert.

**Card 37**
Q: Chain rule for 3 events?
A: $P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$

**Card 38**
Q: Draw 2 cards without replacement. $P(\text{both aces})$?
A: $\frac{4}{52} \times \frac{3}{51} = \frac{1}{221}$

---

## LAW OF TOTAL PROBABILITY & BAYES (Cards 39-43)

**Card 39**
Q: Law of Total Probability (2 cases)?
A: $P(A) = P(A|B) P(B) + P(A|B^c) P(B^c)$

**Card 40**
Q: When to use LOTP?
A: When you can't compute $P(A)$ directly but can partition the sample space.

**Card 41**
Q: Bayes' theorem formula?
A: $P(B|A) = \frac{P(A|B) P(B)}{P(A)}$ where $P(A)$ from LOTP if needed.

**Card 42**
Q: In Bayes, what are prior, likelihood, and posterior?
A: Prior = $P(B)$ (before evidence), Likelihood = $P(A|B)$ (evidence given hypothesis), Posterior = $P(B|A)$ (after evidence).

**Card 43**
Q: Disease 1%, test 90% sensitive/specific. Test positive. $P(\text{disease})$?
A: Approx 8-10% (exact: use Bayes). Low prior → most positives false.

---

## INDEPENDENCE (Cards 44-48)

**Card 44**
Q: Definition of independence for events $A$ and $B$?
A: $P(A \cap B) = P(A) \cdot P(B)$

**Card 45**
Q: Alternative characterization of independence?
A: $P(A|B) = P(A)$ (knowing $B$ doesn't change probability of $A$)

**Card 46**
Q: Are disjoint events independent?
A: NO! (if both have positive probability). Disjoint means dependent.

**Card 47**
Q: If $A$ and $B$ independent, what about $A$ and $B^c$?
A: Also independent (and $A^c$ & $B$, and $A^c$ & $B^c$).

**Card 48**
Q: Probability of at least 1 success in 5 independent trials, each $p=0.3$?
A: $1 - (0.7)^5 = 1 - 0.16807 \approx 0.832$

---

## EXAM TEMPLATES (Cards 49-50)

**Card 49**
Q: Birthday problem with 23 people?
A: $P(\text{collision}) \approx 50.7\%$ (over half!)

**Card 50**
Q: System with 3 components in parallel, each works with $p=0.8$. $P(\text{system works})$?
A: $1 - (0.2)^3 = 1 - 0.008 = 0.992$

---

# HOW TO USE THESE FLASHCARDS

**Study Method 1: Spaced Repetition**
- Day 1: Cards 1-25
- Day 2: Cards 26-50, review any you got wrong from Day 1
- Day 3: All cards, focus on weak areas

**Study Method 2: Topic Focus**
- Focus on one topic group (e.g., Conditional Probability)
- Master all cards in that group before moving on

**Study Method 3: Active Recall**
- Read question
- Say answer out loud BEFORE looking
- Grade yourself: know it / uncertain / don't know
- Repeat uncertain/don't know cards

**Quick Review (15 minutes):**
Cards 5, 6, 11, 16, 21, 30, 31, 34, 39, 41, 44, 46 (12 high-yield cards)

