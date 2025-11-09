# PART I: COMBINATORIAL ANALYSIS - DETAILED

## 1. COUNTING BASICS & FUNDAMENTAL PRINCIPLES

### Intuition
Think of counting as answering "how many ways?" The product rule multiplies when you make sequential independent choices. The sum rule adds when you choose between mutually exclusive options (like picking from separate menus).

### Formal Definitions

**Product Rule:** If a procedure can be broken into $k$ successive tasks, where task 1 has $n_1$ outcomes, task 2 has $n_2$ outcomes, ..., task $k$ has $n_k$ outcomes, then the total number of outcomes for the procedure is:
$$n_1 \cdot n_2 \cdot \ldots \cdot n_k$$

**Sum Rule:** If a task can be done in one of $k$ mutually exclusive ways, where way 1 can be done in $n_1$ ways, way 2 in $n_2$ ways, ..., way $k$ in $n_k$ ways, then the total number of ways is:
$$n_1 + n_2 + \ldots + n_k$$

### Solution Structure: Idea → Plan → Computation → Answer

**Idea:** Identify whether choices are sequential (multiply) or alternative (add)
**Plan:** Break problem into stages or cases; verify independence/disjointness
**Computation:** Apply product or sum rule
**Answer:** State result in context of problem

---

### WORKED EXAMPLE 1 (Easy): License Plates

**Problem:** A license plate consists of 3 letters followed by 4 digits. How many different license plates are possible?

**Key idea:** Sequential independent choices → product rule.

**Step 1:** Identify the structure.
- 3 letter positions: each can be A-Z (26 choices)
- 4 digit positions: each can be 0-9 (10 choices)

**Step 2:** Apply product rule.
Total = (choices for pos 1) × (choices for pos 2) × ... × (choices for pos 7)

**Step 3:** Compute.
$$\text{Total} = 26 \times 26 \times 26 \times 10 \times 10 \times 10 \times 10$$
$$= 26^3 \times 10^4$$
$$= 17,576 \times 10,000$$
$$= 175,760,000$$

**Answer:** 175,760,000 different license plates.

---

### WORKED EXAMPLE 2 (Exam-Style): Passwords with Restrictions

**Problem:** How many 8-character passwords can be formed using uppercase letters (26), lowercase letters (26), and digits (10), where the password must contain at least one digit and at least one uppercase letter?

**Key idea:** "At least one" suggests complement counting: Total - Bad cases.

**Step 1:** Calculate total passwords with no restrictions.
- Each of 8 positions: 26 + 26 + 10 = 62 choices
- Total = $62^8$

**Step 2:** Identify what to subtract (bad cases).
Let $A$ = passwords with no digits (only letters: 52 choices per position)
Let $B$ = passwords with no uppercase (lowercase + digits: 36 choices per position)

We want: Total - (passwords missing digits OR missing uppercase)
= Total - $|A \cup B|$

**Step 3:** Apply inclusion-exclusion to find $|A \cup B|$.
$$|A \cup B| = |A| + |B| - |A \cap B|$$

- $|A|$ = passwords with only letters = $52^8$
- $|B|$ = passwords with only lowercase and digits = $36^8$
- $|A \cap B|$ = passwords with only lowercase letters = $26^8$

**Step 4:** Compute.
$$|A \cup B| = 52^8 + 36^8 - 26^8$$
$$= 53,459,728,531,456 + 2,821,109,907,456 - 208,827,064,576$$
$$= 56,072,011,374,336$$

**Step 5:** Final answer.
$$\text{Valid passwords} = 62^8 - 56,072,011,374,336$$
$$= 218,340,105,584,896 - 56,072,011,374,336$$
$$= 162,268,094,210,560$$

**Answer:** 162,268,094,210,560 valid passwords.

---

### PRACTICE PROBLEMS

**P1.1** (Easy): How many different 3-course meals can be formed from 4 appetizers, 7 entrees, and 5 desserts?

**P1.2** (Easy): A multiple choice test has 10 questions. Each question has 4 choices. How many ways can a student answer all questions?

**P1.3** (Medium): How many 4-digit numbers can be formed from {1,2,3,4,5,6,7} if digits can repeat?

**P1.4** (Medium): How many bit strings of length 10 contain exactly three 1s or exactly three 0s?

**P1.5** (Hard): How many integers from 1 to 1000 are divisible by 3 or 5 or 7?

### SHORT ANSWERS

**A1.1:** $4 \times 7 \times 5 = 140$

**A1.2:** $4^{10} = 1,048,576$

**A1.3:** $7^4 = 2,401$

**A1.4:** $\binom{10}{3} + \binom{10}{3} - 2 = 20 + 20 - 2 = 38$ (subtract cases with exactly 3 of each)
Actually: exactly three 1s gives $\binom{10}{3} = 120$; exactly three 0s gives $\binom{10}{3} = 120$; both can't happen simultaneously except in one case (when we have exactly 3 ones AND 3 zeros which is impossible in a 10-bit string where 3+3 ≠ 10). Wait, let me reconsider.
If exactly three 1s, then exactly seven 0s. If exactly three 0s, then exactly seven 1s. These are disjoint.
So answer is $\binom{10}{3} + \binom{10}{3} = 120 + 120 = 240$.

**A1.5:** Use inclusion-exclusion. $\lfloor 1000/3 \rfloor + \lfloor 1000/5 \rfloor + \lfloor 1000/7 \rfloor - \lfloor 1000/15 \rfloor - \lfloor 1000/21 \rfloor - \lfloor 1000/35 \rfloor + \lfloor 1000/105 \rfloor$
$= 333 + 200 + 142 - 66 - 47 - 28 + 9 = 543$

### FULL SOLUTIONS (P1.4 and P1.5)

**Full Solution P1.4:**

**Step 1:** Interpret "exactly three 1s OR exactly three 0s."
- Case A: exactly three 1s (hence exactly seven 0s)
- Case B: exactly three 0s (hence exactly seven 1s)
- These cases are mutually exclusive (can't have both)

**Step 2:** Count each case.
- Case A: Choose 3 positions for the 1s: $\binom{10}{3} = 120$
- Case B: Choose 3 positions for the 0s: $\binom{10}{3} = 120$

**Step 3:** Apply sum rule.
Total = $120 + 120 = 240$

**Answer:** 240 bit strings.

---

**Full Solution P1.5:**

**Step 1:** Let $A$ = multiples of 3, $B$ = multiples of 5, $C$ = multiples of 7.
We want $|A \cup B \cup C|$.

**Step 2:** Apply inclusion-exclusion principle.
$$|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$$

**Step 3:** Calculate each term.
- $|A| = \lfloor 1000/3 \rfloor = 333$
- $|B| = \lfloor 1000/5 \rfloor = 200$
- $|C| = \lfloor 1000/7 \rfloor = 142$
- $|A \cap B| = $ multiples of $\text{lcm}(3,5) = 15$: $\lfloor 1000/15 \rfloor = 66$
- $|A \cap C| = $ multiples of $\text{lcm}(3,7) = 21$: $\lfloor 1000/21 \rfloor = 47$
- $|B \cap C| = $ multiples of $\text{lcm}(5,7) = 35$: $\lfloor 1000/35 \rfloor = 28$
- $|A \cap B \cap C| = $ multiples of $\text{lcm}(3,5,7) = 105$: $\lfloor 1000/105 \rfloor = 9$

**Step 4:** Compute.
$$|A \cup B \cup C| = 333 + 200 + 142 - 66 - 47 - 28 + 9$$
$$= 675 - 141 + 9$$
$$= 543$$

**Answer:** 543 integers.

---

## 2. PERMUTATIONS

### Intuition
Permutations count ordered arrangements. If you're lining up people, arranging books, or assigning positions where order matters, use permutations. The key question: "Does switching two items create a different outcome?"

### Formal Definitions

**Permutation (no repetition):** The number of ways to arrange $r$ objects chosen from $n$ distinct objects is:
$$P(n,r) = \frac{n!}{(n-r)!} = n(n-1)(n-2)\cdots(n-r+1)$$

**Permutation (with repetition):** The number of $r$-permutations of $n$ distinct objects where repetition is allowed:
$$n^r$$

**Circular permutation:** The number of ways to arrange $n$ distinct objects in a circle:
$$(n-1)!$$

**Permutation of multiset:** The number of ways to arrange $n$ objects where there are $n_1$ of type 1, $n_2$ of type 2, ..., $n_k$ of type $k$ (where $n_1 + n_2 + \cdots + n_k = n$):
$$\frac{n!}{n_1! \, n_2! \cdots n_k!}$$

---

### WORKED EXAMPLE 1 (Easy): Race Rankings

**Problem:** In a race with 12 runners, how many different ways can gold, silver, and bronze medals be awarded?

**Key idea:** Order matters (gold ≠ silver), no repetition → $P(n,r)$.

**Step 1:** Identify parameters.
- $n = 12$ runners
- $r = 3$ positions to fill

**Step 2:** Apply permutation formula.
$$P(12, 3) = \frac{12!}{(12-3)!} = \frac{12!}{9!}$$

**Step 3:** Compute.
$$P(12, 3) = 12 \times 11 \times 10 = 1,320$$

**Answer:** 1,320 different medal outcomes.

---

### WORKED EXAMPLE 2 (Exam-Style): Multiset Permutation

**Problem:** How many distinct arrangements are there of the letters in MISSISSIPPI?

**Key idea:** Repeated letters → multiset permutation formula.

**Step 1:** Count total letters and repetitions.
- Total letters: $n = 11$
- M: 1
- I: 4
- S: 4
- P: 2

**Step 2:** Apply multiset permutation formula.
$$\text{Arrangements} = \frac{11!}{1! \cdot 4! \cdot 4! \cdot 2!}$$

**Step 3:** Compute step by step.
$$11! = 39,916,800$$
$$4! = 24$$
$$2! = 2$$

**Step 4:** Calculate denominator.
$$1! \cdot 4! \cdot 4! \cdot 2! = 1 \times 24 \times 24 \times 2 = 1,152$$

**Step 5:** Divide.
$$\frac{39,916,800}{1,152} = 34,650$$

**Answer:** 34,650 distinct arrangements.

---

### PRACTICE PROBLEMS

**P2.1** (Easy): How many ways can 5 people be arranged in a line?

**P2.2** (Easy): How many 3-letter "words" (arrangements) can be formed from the alphabet (with repetition allowed)?

**P2.3** (Medium): How many ways can 6 people be seated around a circular table?

**P2.4** (Medium): How many distinct arrangements of the letters in SUCCESS?

**P2.5** (Hard): How many ways can we arrange the letters in BANANA such that no two N's are adjacent?

### SHORT ANSWERS

**A2.1:** $5! = 120$

**A2.2:** $26^3 = 17,576$

**A2.3:** $(6-1)! = 5! = 120$

**A2.4:** $\frac{7!}{3! \cdot 2! \cdot 1! \cdot 1!} = \frac{5040}{6 \times 2} = \frac{5040}{12} = 420$

**A2.5:** Arrange B, A, A, A first: $\frac{4!}{3!} = 4$ ways. This creates 5 gaps (\_B\_A\_A\_A\_). Choose 2 of 5 gaps for the N's: $\binom{5}{2} = 10$ ways. Total: $4 \times 10 = 40$.

### FULL SOLUTIONS (P2.4 and P2.5)

**Full Solution P2.4:**

**Step 1:** Count letters in SUCCESS.
- S: 3
- U: 1
- C: 2
- E: 1
- Total: 7 letters

**Step 2:** Apply multiset permutation formula.
$$\frac{7!}{3! \cdot 2! \cdot 1! \cdot 1!}$$

**Step 3:** Compute.
$$7! = 5,040$$
$$3! = 6, \quad 2! = 2$$
$$\text{Denominator} = 6 \times 2 \times 1 \times 1 = 12$$

**Step 4:** Divide.
$$\frac{5,040}{12} = 420$$

**Answer:** 420 distinct arrangements.

---

**Full Solution P2.5:**

**Step 1:** Identify the constraint.
BANANA has: B(1), A(3), N(2). We need no two N's adjacent.

**Step 2:** Strategy: place non-N letters first, then insert N's into gaps.
Non-N letters: B, A, A, A (4 letters with 3 A's)

**Step 3:** Arrange non-N letters.
$$\frac{4!}{3!} = \frac{24}{6} = 4 \text{ ways}$$

**Step 4:** Identify gaps for N's.
Any arrangement of 4 letters creates 5 gaps: \_X\_X\_X\_X\_

**Step 5:** Choose 2 of 5 gaps for the two N's.
$$\binom{5}{2} = 10$$

**Step 6:** Apply product rule.
Total = (arrangements of B,A,A,A) × (ways to place N's)
$$= 4 \times 10 = 40$$

**Answer:** 40 arrangements.

---

## 3. COMBINATIONS

### Intuition
Combinations count selections where order doesn't matter. Choosing a committee, selecting pizza toppings, or picking cards from a deck (when you don't care about the order drawn) all use combinations. Remember: $\binom{n}{r}$ = "n choose r."

### Formal Definitions

**Combination (without repetition):** The number of ways to choose $r$ objects from $n$ distinct objects:
$$\binom{n}{r} = C(n,r) = \frac{n!}{r!(n-r)!}$$

**Properties:**
- $\binom{n}{r} = \binom{n}{n-r}$ (symmetry)
- $\binom{n}{0} = \binom{n}{n} = 1$
- $\binom{n}{1} = n$

**Combination (with repetition / Stars and Bars):** The number of ways to choose $r$ objects from $n$ types with repetition allowed:
$$\binom{n+r-1}{r} = \binom{n+r-1}{n-1}$$

**Interpretation:** Distributing $r$ identical objects into $n$ distinct bins.

---

### WORKED EXAMPLE 1 (Easy): Committee Selection

**Problem:** From a group of 10 people, how many ways can we select a committee of 4?

**Key idea:** Order doesn't matter → combination.

**Step 1:** Identify parameters.
- $n = 10$
- $r = 4$

**Step 2:** Apply combination formula.
$$\binom{10}{4} = \frac{10!}{4! \cdot 6!}$$

**Step 3:** Compute.
$$\binom{10}{4} = \frac{10 \times 9 \times 8 \times 7}{4 \times 3 \times 2 \times 1}$$
$$= \frac{5,040}{24} = 210$$

**Answer:** 210 ways.

---

### WORKED EXAMPLE 2 (Exam-Style): Stars and Bars

**Problem:** How many ways can we distribute 10 identical candies to 4 children such that each child gets at least one candy?

**Key idea:** "At least one" constraint → adjust stars and bars.

**Step 1:** Give each child 1 candy first.
Remaining candies: $10 - 4 = 6$

**Step 2:** Now distribute 6 identical candies to 4 children with no restrictions.
This is a standard stars and bars problem.

**Step 3:** Apply stars and bars formula.
$$\binom{n+r-1}{r} = \binom{4+6-1}{6} = \binom{9}{6}$$

**Step 4:** Use symmetry property.
$$\binom{9}{6} = \binom{9}{3} = \frac{9 \times 8 \times 7}{3 \times 2 \times 1} = \frac{504}{6} = 84$$

**Answer:** 84 ways.

---

### PRACTICE PROBLEMS

**P3.1** (Easy): How many ways can you choose 3 books from a shelf of 8 books?

**P3.2** (Easy): A pizza shop offers 10 toppings. How many different 4-topping pizzas can be ordered?

**P3.3** (Medium): How many non-negative integer solutions are there to $x_1 + x_2 + x_3 = 10$?

**P3.4** (Medium): From a deck of 52 cards, how many 5-card hands contain exactly 3 aces?

**P3.5** (Hard): How many ways can 12 identical balls be placed into 5 distinct boxes such that no box is empty?

### SHORT ANSWERS

**A3.1:** $\binom{8}{3} = 56$

**A3.2:** $\binom{10}{4} = 210$

**A3.3:** $\binom{10+3-1}{10} = \binom{12}{10} = \binom{12}{2} = 66$

**A3.4:** $\binom{4}{3} \times \binom{48}{2} = 4 \times 1128 = 4,512$

**A3.5:** Give each box 1 ball first: $12-5=7$ balls remain. Distribute 7 balls into 5 boxes: $\binom{7+5-1}{7} = \binom{11}{7} = \binom{11}{4} = 330$

### FULL SOLUTIONS (P3.4 and P3.5)

**Full Solution P3.4:**

**Step 1:** Break into independent choices.
- Choose 3 aces from 4 aces
- Choose 2 non-aces from 48 non-aces

**Step 2:** Count each choice.
- Aces: $\binom{4}{3} = 4$
- Non-aces: $\binom{48}{2} = \frac{48 \times 47}{2} = \frac{2,256}{2} = 1,128$

**Step 3:** Apply product rule.
$$\text{Total} = 4 \times 1,128 = 4,512$$

**Answer:** 4,512 hands.

---

**Full Solution P3.5:**

**Step 1:** Convert "no box empty" to "at least one ball per box."
Give each of 5 boxes one ball initially.
Balls used: 5
Balls remaining: $12 - 5 = 7$

**Step 2:** Now distribute 7 identical balls into 5 distinct boxes with no restrictions.
Use stars and bars.

**Step 3:** Apply formula.
$$\binom{n+r-1}{r} = \binom{5+7-1}{7} = \binom{11}{7}$$

**Step 4:** Use symmetry.
$$\binom{11}{7} = \binom{11}{4} = \frac{11 \times 10 \times 9 \times 8}{4 \times 3 \times 2 \times 1}$$
$$= \frac{7,920}{24} = 330$$

**Answer:** 330 ways.

---

## IF YOU ONLY HAVE 10 MINUTES (Combinatorics)

**Memorize these 3 things:**
1. **Decision tree:** Order matters? → Permutation ($P(n,r)$ or $n!$). Order doesn't matter? → Combination ($\binom{n}{r}$).
2. **Stars and bars:** $r$ identical into $n$ bins = $\binom{n+r-1}{r}$. Remember: it's $n+r-1$, not $n+r$.
3. **Inclusion-Exclusion (2 sets):** $|A \cup B| = |A| + |B| - |A \cap B|$

**Do these 2 practice problems:**
1. How many ways to choose 5 cards from 52? Answer: $\binom{52}{5} = 2,598,960$
2. Arrange letters in BOOK: $\frac{4!}{2!} = 12$

