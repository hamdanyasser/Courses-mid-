# PART I: ADVANCED COMBINATORIAL ANALYSIS

## 4. ADVANCED COUNTING FORMULAS

### Intuition
The binomial theorem tells you how to expand $(x+y)^n$ quickly and find specific terms. Multinomial coefficients generalize "choose" to multiple categories. Pascal's identity gives recursive relationships that help verify calculations and prove identities.

### Formal Definitions

**Binomial Theorem:**
$$(x + y)^n = \sum_{k=0}^{n} \binom{n}{k} x^k y^{n-k}$$

**Multinomial Coefficient:** The number of ways to partition $n$ objects into $k$ groups of sizes $n_1, n_2, \ldots, n_k$ where $n_1 + n_2 + \cdots + n_k = n$:
$$\binom{n}{n_1, n_2, \ldots, n_k} = \frac{n!}{n_1! n_2! \cdots n_k!}$$

**Multinomial Theorem:**
$$(x_1 + x_2 + \cdots + x_k)^n = \sum \binom{n}{n_1, n_2, \ldots, n_k} x_1^{n_1} x_2^{n_2} \cdots x_k^{n_k}$$
where the sum is over all non-negative integers $n_1, \ldots, n_k$ such that $n_1 + \cdots + n_k = n$.

**Pascal's Identity:**
$$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$

**Other useful identities:**
- $\sum_{k=0}^{n} \binom{n}{k} = 2^n$
- $\sum_{k=0}^{n} (-1)^k \binom{n}{k} = 0$
- $\binom{n}{k} = \frac{n}{k} \binom{n-1}{k-1}$

---

### WORKED EXAMPLE 1 (Easy): Binomial Expansion

**Problem:** Find the coefficient of $x^3 y^4$ in the expansion of $(x+y)^7$.

**Key idea:** Use binomial theorem; coefficient is $\binom{n}{k}$ where $k$ is power of $x$.

**Step 1:** Identify the binomial theorem form.
$$(x+y)^7 = \sum_{k=0}^{7} \binom{7}{k} x^k y^{7-k}$$

**Step 2:** Match the desired term.
We want $x^3 y^4$, so $k=3$ and $7-k=4$. ✓

**Step 3:** The coefficient is $\binom{7}{3}$.
$$\binom{7}{3} = \frac{7!}{3! \cdot 4!} = \frac{7 \times 6 \times 5}{3 \times 2 \times 1} = \frac{210}{6} = 35$$

**Answer:** The coefficient is 35.

---

### WORKED EXAMPLE 2 (Exam-Style): Multinomial Application

**Problem:** In how many ways can 10 students be divided into three groups: one group of 4, one group of 3, and one group of 3?

**Key idea:** Multinomial coefficient (partitioning into labeled groups).

**Step 1:** Identify parameters.
- Total students: $n = 10$
- Group sizes: 4, 3, 3

**Step 2:** Apply multinomial coefficient.
$$\binom{10}{4, 3, 3} = \frac{10!}{4! \cdot 3! \cdot 3!}$$

**Step 3:** Compute.
$$10! = 3,628,800$$
$$4! = 24, \quad 3! = 6$$
$$\text{Denominator} = 24 \times 6 \times 6 = 864$$

**Step 4:** Divide.
$$\frac{3,628,800}{864} = 4,200$$

**Answer:** 4,200 ways.

**Note:** If the two groups of 3 were indistinguishable, we'd divide by $2!$ to get $4,200/2 = 2,100$.

---

### PRACTICE PROBLEMS

**P4.1** (Easy): What is the sum $\sum_{k=0}^{10} \binom{10}{k}$?

**P4.2** (Easy): Find the coefficient of $x^5$ in $(2x + 3)^8$.

**P4.3** (Medium): Verify Pascal's identity for $\binom{6}{2}$.

**P4.4** (Medium): How many ways can 12 people be divided into three teams of 4 each (teams are distinguishable)?

**P4.5** (Hard): Find the coefficient of $x^2 y^3 z^2$ in $(x+y+z)^7$.

### SHORT ANSWERS

**A4.1:** $2^{10} = 1,024$

**A4.2:** Coefficient of $x^5$: $\binom{8}{5} (2)^5 (3)^3 = 56 \times 32 \times 27 = 48,384$

**A4.3:** $\binom{6}{2} = 15 = \binom{5}{1} + \binom{5}{2} = 5 + 10 = 15$ ✓

**A4.4:** $\binom{12}{4,4,4} = \frac{12!}{4! \cdot 4! \cdot 4!} = \frac{479,001,600}{24 \times 24 \times 24} = 34,650$

**A4.5:** $\binom{7}{2,3,2} = \frac{7!}{2! \cdot 3! \cdot 2!} = \frac{5,040}{2 \times 6 \times 2} = \frac{5,040}{24} = 210$

### FULL SOLUTIONS (P4.2 and P4.5)

**Full Solution P4.2:**

**Step 1:** Rewrite using binomial theorem.
$$(2x + 3)^8 = \sum_{k=0}^{8} \binom{8}{k} (2x)^k (3)^{8-k}$$

**Step 2:** Find term with $x^5$.
We need $k=5$:
$$\binom{8}{5} (2x)^5 (3)^3 = \binom{8}{5} \cdot 2^5 \cdot x^5 \cdot 3^3$$

**Step 3:** Calculate coefficient.
$$\binom{8}{5} = \binom{8}{3} = \frac{8 \times 7 \times 6}{3 \times 2 \times 1} = \frac{336}{6} = 56$$
$$2^5 = 32$$
$$3^3 = 27$$

**Step 4:** Multiply.
$$56 \times 32 \times 27 = 56 \times 864 = 48,384$$

**Answer:** Coefficient is 48,384.

---

**Full Solution P4.5:**

**Step 1:** Recognize multinomial theorem.
$$(x+y+z)^7 = \sum \binom{7}{n_1, n_2, n_3} x^{n_1} y^{n_2} z^{n_3}$$
where $n_1 + n_2 + n_3 = 7$.

**Step 2:** Identify desired term.
We want $x^2 y^3 z^2$, so $n_1=2, n_2=3, n_3=2$.
Check: $2+3+2=7$ ✓

**Step 3:** Apply multinomial coefficient.
$$\binom{7}{2,3,2} = \frac{7!}{2! \cdot 3! \cdot 2!}$$

**Step 4:** Compute.
$$7! = 5,040$$
$$2! = 2, \quad 3! = 6$$
$$\text{Denominator} = 2 \times 6 \times 2 = 24$$
$$\frac{5,040}{24} = 210$$

**Answer:** Coefficient is 210.

---

## 5. INCLUSION-EXCLUSION PRINCIPLE

### Intuition
When counting objects with at least one of several properties, naive addition over-counts overlaps. Inclusion-exclusion fixes this by alternately adding and subtracting intersection counts. Think of Venn diagrams: add the circles, subtract the overlaps, add back the triple overlaps, etc.

### Formal Definitions

**Inclusion-Exclusion (Two Sets):**
$$|A \cup B| = |A| + |B| - |A \cap B|$$

**Inclusion-Exclusion (Three Sets):**
$$|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$$

**Inclusion-Exclusion (General):**
$$\left| \bigcup_{i=1}^{n} A_i \right| = \sum_{i} |A_i| - \sum_{i<j} |A_i \cap A_j| + \sum_{i<j<k} |A_i \cap A_j \cap A_k| - \cdots + (-1)^{n+1} |A_1 \cap \cdots \cap A_n|$$

**Derangements:** A derangement is a permutation where no element appears in its original position. The number of derangements of $n$ objects is:
$$D_n = n! \sum_{i=0}^{n} \frac{(-1)^i}{i!} = n! \left( \frac{1}{0!} - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \cdots + \frac{(-1)^n}{n!} \right)$$

Approximation: $D_n \approx \frac{n!}{e}$ for large $n$.

---

### WORKED EXAMPLE 1 (Easy): Two-Set PIE

**Problem:** In a class of 30 students, 18 play soccer, 15 play basketball, and 8 play both. How many students play at least one of these sports?

**Key idea:** Use two-set inclusion-exclusion.

**Step 1:** Define sets.
- $A$ = students who play soccer, $|A| = 18$
- $B$ = students who play basketball, $|B| = 15$
- $A \cap B$ = students who play both, $|A \cap B| = 8$

**Step 2:** Apply inclusion-exclusion.
$$|A \cup B| = |A| + |B| - |A \cap B|$$

**Step 3:** Compute.
$$|A \cup B| = 18 + 15 - 8 = 25$$

**Answer:** 25 students play at least one sport.

---

### WORKED EXAMPLE 2 (Exam-Style): Derangements

**Problem:** Five letters are written to five different people, and the letters are placed randomly into five pre-addressed envelopes (one letter per envelope). What is the probability that no letter is placed in the correct envelope?

**Key idea:** Use derangement formula, then divide by total permutations.

**Step 1:** Calculate total ways to place letters.
Total permutations = $5! = 120$

**Step 2:** Calculate derangements $D_5$.
$$D_5 = 5! \sum_{i=0}^{5} \frac{(-1)^i}{i!}$$

**Step 3:** Compute sum.
$$\sum_{i=0}^{5} \frac{(-1)^i}{i!} = \frac{1}{0!} - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \frac{1}{4!} - \frac{1}{5!}$$
$$= 1 - 1 + \frac{1}{2} - \frac{1}{6} + \frac{1}{24} - \frac{1}{120}$$
$$= \frac{1}{2} - \frac{1}{6} + \frac{1}{24} - \frac{1}{120}$$

**Step 4:** Find common denominator (120).
$$= \frac{60}{120} - \frac{20}{120} + \frac{5}{120} - \frac{1}{120} = \frac{44}{120}$$

**Step 5:** Calculate $D_5$.
$$D_5 = 120 \times \frac{44}{120} = 44$$

**Step 6:** Calculate probability.
$$P(\text{no correct}) = \frac{D_5}{5!} = \frac{44}{120} = \frac{11}{30} \approx 0.367$$

**Answer:** $\frac{11}{30}$ or approximately 36.7%.

---

### PRACTICE PROBLEMS

**P5.1** (Easy): Among 100 students, 60 study French, 50 study Spanish, and 30 study both. How many study at least one language?

**P5.2** (Medium): How many integers from 1 to 200 are divisible by 2 or 3?

**P5.3** (Medium): Calculate $D_4$ (derangements of 4 objects).

**P5.4** (Hard): How many permutations of {1,2,3,4,5} have exactly two fixed points?

**P5.5** (Hard): Use inclusion-exclusion to find how many integers from 1 to 1000 are coprime to 30 (i.e., $\gcd(n, 30) = 1$).

### SHORT ANSWERS

**A5.1:** $60 + 50 - 30 = 80$

**A5.2:** $|A \cup B| = 100 + 66 - 33 = 133$
Where $A$ = multiples of 2: $\lfloor 200/2 \rfloor = 100$
$B$ = multiples of 3: $\lfloor 200/3 \rfloor = 66$
$A \cap B$ = multiples of 6: $\lfloor 200/6 \rfloor = 33$

**A5.3:** $D_4 = 4! \left(1 - 1 + \frac{1}{2} - \frac{1}{6} + \frac{1}{24}\right) = 24 \times \frac{9}{24} = 9$

**A5.4:** Choose 2 fixed points: $\binom{5}{2} = 10$. Remaining 3 must be deranged: $D_3 = 2$. Total: $10 \times 2 = 20$

**A5.5:** Use $\phi(30)$ or inclusion-exclusion. $30 = 2 \times 3 \times 5$.
Answer: $1000 - \lfloor 1000/2 \rfloor - \lfloor 1000/3 \rfloor - \lfloor 1000/5 \rfloor + \lfloor 1000/6 \rfloor + \lfloor 1000/10 \rfloor + \lfloor 1000/15 \rfloor - \lfloor 1000/30 \rfloor$
$= 1000 - 500 - 333 - 200 + 166 + 100 + 66 - 33 = 266$

### FULL SOLUTIONS (P5.3 and P5.4)

**Full Solution P5.3:**

**Step 1:** Apply derangement formula.
$$D_4 = 4! \sum_{i=0}^{4} \frac{(-1)^i}{i!}$$

**Step 2:** Calculate sum.
$$\sum_{i=0}^{4} \frac{(-1)^i}{i!} = 1 - 1 + \frac{1}{2} - \frac{1}{6} + \frac{1}{24}$$

**Step 3:** Common denominator (24).
$$= \frac{24}{24} - \frac{24}{24} + \frac{12}{24} - \frac{4}{24} + \frac{1}{24} = \frac{9}{24}$$

**Step 4:** Multiply by $4!$.
$$D_4 = 24 \times \frac{9}{24} = 9$$

**Answer:** 9 derangements.

**Verification:** The 9 derangements of {1,2,3,4} are:
2143, 2341, 2413, 3142, 3241, 3412, 4123, 4312, 4321

---

**Full Solution P5.4:**

**Step 1:** Strategy breakdown.
- Choose which 2 positions are fixed points
- Ensure remaining 3 elements are deranged

**Step 2:** Choose 2 fixed points.
$$\binom{5}{2} = 10 \text{ ways}$$

**Step 3:** Derange the remaining 3 elements.
Need $D_3$:
$$D_3 = 3! \sum_{i=0}^{3} \frac{(-1)^i}{i!} = 6 \left(1 - 1 + \frac{1}{2} - \frac{1}{6}\right)$$
$$= 6 \times \frac{2}{6} = 2$$

The 2 derangements of {a,b,c} are: bca, cab

**Step 4:** Apply product rule.
$$\text{Total} = 10 \times 2 = 20$$

**Answer:** 20 permutations.

---

## 6. PIGEONHOLE PRINCIPLE

### Intuition
If you have more pigeons than pigeonholes, at least one hole must contain multiple pigeons. This simple idea is surprisingly powerful for proving existence results and finding bounds.

### Formal Definitions

**Pigeonhole Principle (Simple Form):**
If $n+1$ objects are placed into $n$ boxes, then at least one box contains at least 2 objects.

**Pigeonhole Principle (Generalized Form):**
If $n$ objects are placed into $k$ boxes, then at least one box contains at least $\lceil n/k \rceil$ objects.

Equivalently: If average is $n/k$, some box has at least the ceiling of the average.

---

### WORKED EXAMPLE 1 (Easy): Socks in a Drawer

**Problem:** A drawer contains 10 red socks and 10 blue socks. If you pull out socks in the dark, how many must you pull to guarantee a matching pair?

**Key idea:** Use simple pigeonhole with 2 "boxes" (colors).

**Step 1:** Identify pigeonholes and pigeons.
- Boxes: 2 colors (red, blue)
- Pigeons: socks drawn

**Step 2:** Apply simple pigeonhole principle.
With 3 socks and 2 colors, at least one color appears twice.

**Answer:** 3 socks guarantees a matching pair.

---

### WORKED EXAMPLE 2 (Exam-Style): Numbers and Remainders

**Problem:** Show that among any 11 integers, there exist two whose difference is divisible by 10.

**Key idea:** Remainders mod 10 are the pigeonholes.

**Step 1:** Identify boxes.
Possible remainders when divided by 10: {0, 1, 2, 3, 4, 5, 6, 7, 8, 9} → 10 boxes

**Step 2:** Apply pigeonhole principle.
- 11 integers (pigeons)
- 10 possible remainders (boxes)
- By pigeonhole: at least two integers have the same remainder mod 10

**Step 3:** Conclude.
If two integers $a$ and $b$ have the same remainder mod 10, then $a - b \equiv 0 \pmod{10}$, meaning $10 | (a-b)$.

**Answer:** Proven by pigeonhole principle.

---

### PRACTICE PROBLEMS

**P6.1** (Easy): In a group of 13 people, show that at least two were born in the same month.

**P6.2** (Medium): Show that in any sequence of 101 integers, there exists a consecutive subsequence whose sum is divisible by 100.

**P6.3** (Medium): Among 6 people, show that either 3 are mutual friends or 3 are mutual strangers.

**P6.4** (Hard): A bag contains 100 balls numbered 1 to 100. How many balls must you draw to guarantee that the sum of two of the drawn balls equals 100?

**P6.5** (Hard): Prove that in any set of $n+1$ distinct integers from {1, 2, ..., 2n}, there exist two integers where one divides the other.

### SHORT ANSWERS

**A6.1:** 13 people, 12 months → pigeonhole → at least $\lceil 13/12 \rceil = 2$ in same month

**A6.2:** Consider partial sums $S_0=0, S_1, S_2, \ldots, S_{101}$ (102 values). Remainders mod 100 are 0-99 (100 values). By pigeonhole, two partial sums have same remainder, so their difference is divisible by 100.

**A6.3:** This is Ramsey number $R(3,3) = 6$. Consider one person; they have 5 connections. By pigeonhole, at least 3 are "friend" or at least 3 are "stranger." Complete the argument with cases.

**A6.4:** Consider pairs that sum to 100: {1,99}, {2,98}, ..., {49,51}, plus {50}, {100}. That's 51 "pigeonholes." Draw 52 balls → at least two from same pair.

**A6.5:** Write each integer as $2^k \cdot m$ where $m$ is odd. There are $n$ odd numbers in range 1 to $2n$. With $n+1$ integers, two share the same odd part $m$, say $2^a \cdot m$ and $2^b \cdot m$ with $a < b$. Then $2^a \cdot m | 2^b \cdot m$.

### FULL SOLUTIONS (P6.2 and P6.5)

**Full Solution P6.2:**

**Step 1:** Define partial sums.
Let the sequence be $a_1, a_2, \ldots, a_{101}$.
Define $S_k = a_1 + a_2 + \cdots + a_k$ for $k=1, \ldots, 101$, and $S_0 = 0$.

**Step 2:** Count partial sums and remainders.
- Partial sums: $S_0, S_1, \ldots, S_{101}$ → 102 values
- Possible remainders mod 100: 0, 1, 2, ..., 99 → 100 values

**Step 3:** Apply pigeonhole principle.
102 partial sums into 100 remainder classes → at least two partial sums have the same remainder mod 100.

**Step 4:** Conclude.
If $S_i \equiv S_j \pmod{100}$ with $i < j$, then:
$$S_j - S_i = a_{i+1} + a_{i+2} + \cdots + a_j \equiv 0 \pmod{100}$$

This is a consecutive subsequence with sum divisible by 100.

**Answer:** Proven.

---

**Full Solution P6.5:**

**Step 1:** Represent each integer uniquely.
Every positive integer $n$ can be written uniquely as $n = 2^k \cdot m$ where $m$ is odd and $k \geq 0$.

**Step 2:** Identify the odd parts in range.
For integers in {1, 2, ..., 2n}, the possible odd parts are: {1, 3, 5, 7, ..., 2n-1}.
Number of odd integers in this range: $n$

**Step 3:** Apply pigeonhole principle.
- We select $n+1$ distinct integers (pigeons)
- There are $n$ possible odd parts (boxes)
- By pigeonhole: at least two of our integers share the same odd part $m$

**Step 4:** Show divisibility.
Say two integers are $2^a \cdot m$ and $2^b \cdot m$ where $a < b$ (WLOG).
Then:
$$2^a \cdot m \mid 2^b \cdot m$$
because $2^b \cdot m = 2^{b-a} \cdot (2^a \cdot m)$ and $2^{b-a}$ is an integer.

**Answer:** Proven.

---

## 7. URN MODELS (Quick Reference)

### Intuition
Urn models organize counting problems by two dimensions: (1) Does order matter? (2) Can items repeat? This creates a 2×2 table that covers most basic counting scenarios.

### The Four Urn Models

Drawing $r$ objects from $n$ distinct objects:

| | **Order Matters** | **Order Doesn't Matter** |
|---|---|---|
| **Without Replacement** | $P(n,r) = \frac{n!}{(n-r)!}$ | $C(n,r) = \binom{n}{r}$ |
| **With Replacement** | $n^r$ | $\binom{n+r-1}{r}$ |

**Interpretations:**
- **Top-left:** Permutations (arrange $r$ from $n$)
- **Top-right:** Combinations (choose $r$ from $n$)
- **Bottom-left:** Sequences with repetition (passwords, etc.)
- **Bottom-right:** Stars and bars (distribute identical items)

---

### WORKED EXAMPLE (Quick): Identify the Model

**Problem:** How many ways can we select a 5-card hand from a 52-card deck if:
(a) Order matters, no replacement
(b) Order doesn't matter, no replacement
(c) Order matters, with replacement
(d) Order doesn't matter, with replacement

**Solutions:**

**(a)** $P(52, 5) = \frac{52!}{47!} = 52 \times 51 \times 50 \times 49 \times 48 = 311,875,200$

**(b)** $\binom{52}{5} = \frac{52!}{5! \cdot 47!} = 2,598,960$ (standard poker hand)

**(c)** $52^5 = 380,204,032$

**(d)** $\binom{52+5-1}{5} = \binom{56}{5} = 3,819,816$

---

## 8. SIMPLE RECURRENCES & GENERATING FUNCTIONS (Brief Intro)

### Intuition
Some counting problems are easiest solved by finding a pattern: express the answer for $n$ in terms of smaller values. Generating functions encode sequences as power series, turning recurrence relations into algebra.

### Basic Recurrence Example

**Fibonacci sequence:** $F_n = F_{n-1} + F_{n-2}$ with $F_0=0, F_1=1$

**Solving strategy:**
1. Write out first few terms
2. Find pattern
3. Verify by induction (if needed)

### Generating Functions (Very Brief)

**Definition:** The generating function for sequence $a_0, a_1, a_2, \ldots$ is:
$$G(x) = a_0 + a_1 x + a_2 x^2 + a_3 x^3 + \cdots$$

**Example:** For $a_n = 1$ (all terms 1):
$$G(x) = 1 + x + x^2 + x^3 + \cdots = \frac{1}{1-x}$$

**Binomial series:**
$$(1+x)^n = \sum_{k=0}^{n} \binom{n}{k} x^k$$

---

### WORKED EXAMPLE: Tower of Hanoi

**Problem:** Find a recurrence for $T_n$, the number of moves needed to solve the Tower of Hanoi with $n$ disks.

**Key idea:** To move $n$ disks, move top $n-1$ to spare peg, move largest, then move $n-1$ back.

**Step 1:** Establish recurrence.
$$T_n = T_{n-1} + 1 + T_{n-1} = 2T_{n-1} + 1$$

**Step 2:** Base case.
$$T_1 = 1$$

**Step 3:** Compute first few terms.
- $T_1 = 1$
- $T_2 = 2(1) + 1 = 3$
- $T_3 = 2(3) + 1 = 7$
- $T_4 = 2(7) + 1 = 15$

**Step 4:** Guess closed form.
Pattern suggests $T_n = 2^n - 1$

**Step 5:** Verify (by induction).
Base: $T_1 = 1 = 2^1 - 1$ ✓
Inductive step: Assume $T_k = 2^k - 1$. Then:
$$T_{k+1} = 2T_k + 1 = 2(2^k - 1) + 1 = 2^{k+1} - 2 + 1 = 2^{k+1} - 1$$ ✓

**Answer:** $T_n = 2^n - 1$

---

## IF YOU ONLY HAVE 10 MINUTES (Advanced Combinatorics)

**Memorize these 3 things:**
1. **Inclusion-Exclusion (3 sets):** $|A \cup B \cup C| = |A|+|B|+|C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$
2. **Derangements:** $D_n \approx n!/e \approx 0.368 \cdot n!$, exact: $D_n = n! \sum_{i=0}^{n} \frac{(-1)^i}{i!}$
3. **Generalized pigeonhole:** $n$ objects in $k$ boxes → at least one box has $\geq \lceil n/k \rceil$ objects

**Do these 2 practice problems:**
1. Among 50 students, 30 study math, 25 study physics, 10 study both. How many study at least one? Answer: $30+25-10=45$
2. Calculate $D_3$: $D_3 = 6(1-1+1/2-1/6) = 6 \cdot 1/3 = 2$

