# THINKING TOOLS, HEURISTICS & COMMON TRAPS

## 15 "HOW TO THINK" HEURISTICS

### COMBINATORICS HEURISTICS (1-7)

**H1: Order Decision Tree**
```
Does order matter?
├─ YES → Is repetition allowed?
│         ├─ YES → n^r
│         └─ NO  → P(n,r) = n!/(n-r)!
└─ NO  → Is repetition allowed?
          ├─ YES → Stars & bars: C(n+r-1,r)
          └─ NO  → C(n,r) = n!/[r!(n-r)!]
```
**Use:** First question for ANY counting problem.

---

**H2: Complement Counting**
When to use: "At least one," "at least k," or counting many cases.

Pattern: If direct counting involves many cases but complement is simple, use:
$$\text{Desired} = \text{Total} - \text{Complement}$$

Example: "At least one ace in 5 cards" = Total - "No aces"

---

**H3: Inclusion-Exclusion Recognition**
Use when: Counting unions OR counting "at least one of several properties."

Signal words: "or," "at least one," "satisfies property A or B."

Strategy:
- 2 sets: Add, subtract overlap
- 3+ sets: Alternating sum (positive singles, negative pairs, positive triples, ...)

---

**H4: Stars and Bars Trigger**
Use when problem mentions:
- "Distribute identical objects into distinct bins"
- "Non-negative integer solutions to $x_1 + x_2 + \cdots = n$"
- "How many ways to select r items from n types with replacement"

Formula: $\binom{n+r-1}{r}$ where $n$ = types, $r$ = items

**Constraint handling:** "At least 1 each" → pre-allocate, then stars-and-bars the rest

---

**H5: Symmetry Exploitation**
Use $\binom{n}{k} = \binom{n}{n-k}$ to simplify calculations.

Always compute the SMALLER value.

Example: $\binom{100}{98} = \binom{100}{2} = 4950$ (much easier!)

---

**H6: Multiset Pattern Recognition**
If problem has repeated items in arrangements:
- Identify all item types and their counts
- Use $\frac{n!}{n_1! n_2! \cdots n_k!}$

Signal words: "distinct arrangements," "permutations of letters in MISSISSIPPI"

---

**H7: Bijection Thinking**
Sometimes counting directly is hard, but you can map to an easier problem.

Example: "Lattice paths from (0,0) to (m,n)" = sequences of m R's and n U's = $\binom{m+n}{m}$

Look for: "This is really the same as [simpler problem]"

---

### PROBABILITY HEURISTICS (8-15)

**H8: Probability or Counting?**
Decision: Is the sample space uniform (equally likely outcomes)?
- YES → Probability = Counting: $P(A) = |A|/|\Omega|$
- NO → Must use axioms, conditional probability, etc.

Most exam problems (dice, cards, coins): USE COUNTING.

---

**H9: Conditional Probability Framing**
Given "probability of A given B," always write:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

Then ask: Can I find $P(A \cap B)$? Often via multiplication rule or tree.

**Reverse conditional:** If given $P(A|B)$ and want $P(B|A)$ → BAYES.

---

**H10: LOTP for "Total" Probability**
Use when: Can't compute $P(A)$ directly, but can partition the sample space.

Strategy:
1. Find a partition $B_1, \ldots, B_n$ (exhaustive, disjoint)
2. Find $P(A|B_i)$ for each $i$
3. Compute $P(A) = \sum P(A|B_i) P(B_i)$

Signal: Problem has multiple "scenarios" or "cases."

---

**H11: Bayes = Reverse Diagnostic**
Use when: Have cause→effect but want effect→cause.

Classic structure:
- Given: $P(\text{effect}|\text{cause})$ and $P(\text{cause})$
- Want: $P(\text{cause}|\text{effect})$

Formula:
$$P(\text{cause}|\text{effect}) = \frac{P(\text{effect}|\text{cause}) P(\text{cause})}{P(\text{effect})}$$

Use LOTP to find denominator.

---

**H12: Independence Check**
Don't assume independence — verify!

To check: Does $P(A \cap B) = P(A) \cdot P(B)$?

Alternative: Does $P(A|B) = P(A)$?

**Warning:** "Disjoint" and "independent" are OPPOSITE (except trivial cases).
- Disjoint: $P(A \cap B) = 0$
- Independent: $P(A \cap B) = P(A) P(B)$ (usually ≠ 0)

---

**H13: Complement for "At Least One"**
Almost always easier:
$$P(\text{at least one}) = 1 - P(\text{none})$$

Example: $P(\text{at least 1 head in 10 flips}) = 1 - (1/2)^{10}$

Signal words: "at least," "at most" (sometimes), "one or more"

---

**H14: Tree Drawing Protocol**
Draw a probability tree when:
- Multi-stage experiment (sequential events)
- Conditional probabilities given at each stage
- Want to visualize all paths

Rules:
- Probabilities on branches (conditional given previous stages)
- Multiply along path for joint probability
- Add across paths for marginal probability

---

**H15: Rare Event and Bayes Paradox**
Be skeptical of positive test results when:
- Base rate (prior) is very low
- False positive rate is non-negligible

Even with 99% accurate test, if disease is 0.1%, most positives are false!

Strategy: Always compute actual posterior using Bayes, don't trust intuition.

---

## 12 COMMON EXAM TRAPS & HOW TO AVOID THEM

### TRAP 1: Confusing Permutations and Combinations
**Trap:** Using $C(n,r)$ when order matters or $P(n,r)$ when it doesn't.

**Test:** Ask: "If I swap two items, is it a different outcome?"
- YES → Permutation
- NO → Combination

**Example:** "Choose 3 books from 10" uses $C(10,3)$. "Arrange 3 books from 10 on a shelf" uses $P(10,3)$.

---

### TRAP 2: Wrong Stars and Bars Formula
**Trap:** Writing $\binom{n+r}{r}$ instead of $\binom{n+r-1}{r}$.

**Fix:** Memorize the correct form: $r$ identical items into $n$ bins = $\binom{n+r-1}{r}$.

**Derivation reminder:** Think of $r$ stars and $n-1$ bars: total $n+r-1$ positions, choose $r$ for stars.

---

### TRAP 3: Forgetting to Subtract in Inclusion-Exclusion
**Trap:** Computing $P(A \cup B)$ as $P(A) + P(B)$ (forgetting to subtract overlap).

**Fix:** ALWAYS write: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ unless explicitly told events are disjoint.

---

### TRAP 4: Mixing Up $P(A|B)$ and $P(B|A)$
**Trap:** These are NOT the same! $P(\text{symptoms}|\text{disease}) \neq P(\text{disease}|\text{symptoms})$.

**Fix:**
- Read carefully: "probability of A given B" is $P(A|B)$
- To swap, use Bayes' theorem
- Check units/context: does the conditional make sense?

---

### TRAP 5: Assuming Disjoint Events are Independent
**Trap:** If $A \cap B = \emptyset$ (disjoint), thinking they're independent.

**Truth:** Disjoint events with positive probability are DEPENDENT.
- Knowing A occurred means B cannot occur: $P(B|A) = 0 \neq P(B)$.

**Fix:** Disjoint = mutually exclusive ≠ independent (unless one has probability 0).

---

### TRAP 6: Independence Without Justification
**Trap:** Multiplying probabilities without checking independence.

**Fix:** Only multiply if:
- Problem explicitly states independence, OR
- Independence follows from setup (e.g., separate dice rolls, coin flips, draws with replacement)

**Test:** Does knowing first event affect second? If yes, NOT independent.

---

### TRAP 7: Forgetting "Without Replacement" Affects Probability
**Trap:** Treating draws without replacement as if they were with replacement.

**Example:** $P(\text{2 red balls from 5 red, 3 blue without replacement})$
- WRONG: $(5/8) \times (5/8)$
- RIGHT: $(5/8) \times (4/7)$ — second probability changes!

**Fix:** Track how many items remain after each draw.

---

### TRAP 8: Complement of "At Least One" is Not "At Most One"
**Trap:** Thinking "not (at least one)" = "at most one".

**Truth:**
- Complement of "at least one" = "none" (zero)
- Complement of "at most one" = "at least two"

**Fix:** Write set notation or list cases explicitly to avoid confusion.

---

### TRAP 9: Using Probability Outside [0,1]
**Trap:** Computing probability and getting $P > 1$ or $P < 0$ but continuing anyway.

**Fix:** If you get impossible probability:
- Check arithmetic
- Check if you double-counted
- Verify formula applies to your situation

---

### TRAP 10: Birthday Problem and Overcounting
**Trap:** In birthday problem, computing $\binom{n}{2} \times \frac{1}{365}$ (this counts pairs, not probability).

**Right approach:**
$$P(\text{collision}) = 1 - \frac{365 \times 364 \times \cdots \times (365-n+1)}{365^n}$$

**Fix:** Use complement: all different birthdays.

---

### TRAP 11: Misapplying Symmetry
**Trap:** Assuming all outcomes are equally likely when they're not.

**Example:** Sum of two dice: "Sum = 2" and "sum = 7" are NOT equally likely.
- Sum = 2: one outcome (1,1)
- Sum = 7: six outcomes (1,6), (2,5), (3,4), (4,3), (5,2), (6,1)

**Fix:** Count outcomes in sample space carefully; don't assume symmetry without justification.

---

### TRAP 12: Bayes Without LOTP in Denominator
**Trap:** Computing $P(B|A) = \frac{P(A|B) P(B)}{P(A)}$ but using wrong $P(A)$.

**Fix:** If not given $P(A)$ directly, compute via LOTP:
$$P(A) = P(A|B)P(B) + P(A|B^c)P(B^c)$$

Don't make up a value for $P(A)$!

---

## STRATEGY: When You're Stuck on a Problem

**Step 1:** Reread the problem. What exactly are they asking for?

**Step 2:** Identify the type:
- Counting problem → use H1-H7
- Probability problem → use H8-H15

**Step 3:** Ask diagnostic questions:
- Is this a conditional probability?
- Can I use complement?
- Is there a partition I can exploit?
- Are events independent?

**Step 4:** Write down what you know:
- Given probabilities
- Sample space size
- Event definitions

**Step 5:** Draw a picture if applicable:
- Venn diagram for sets
- Probability tree for sequential events
- Table for sample space

**Step 6:** Start with simple cases:
- What if n=2? n=3?
- Does the pattern generalize?

**Step 7:** Check reasonableness:
- Is probability between 0 and 1?
- Does answer match intuition?
- Try extreme cases (n=0, n=1, very large n)

---

## RED FLAGS: When to Double-Check

🚩 **Probability > 1 or < 0** → Error in calculation or logic

🚩 **Answer seems too large** → Likely overcounted or used wrong formula

🚩 **Answer seems too small** → May have missed cases

🚩 **Got exact same answer for two different problems** → Probably mistake in one

🚩 **Arithmetic doesn't simplify nicely** → Check if you chose the right approach

🚩 **Problem says "independent" but you didn't use it** → Missed opportunity to simplify

🚩 **Problem says "given" but you didn't condition** → Likely used wrong probability

🚩 **Used addition when should multiply (or vice versa)** → Review product vs sum rule

---

## EXAM TIME MANAGEMENT

**For 60-minute, 100-point exam:**

1. **First pass (20 min):** Do all problems you immediately know how to solve. Build confidence, bank points.

2. **Second pass (25 min):** Attack medium-difficulty problems. Show work even if unsure.

3. **Third pass (10 min):** Hardest problems. Get partial credit: set up equations, state formulas, show approach even if can't finish.

4. **Review (5 min):**
   - Check arithmetic on high-point problems
   - Verify probabilities ∈ [0,1]
   - Make sure you answered what was asked

**Point allocation strategy:**
- 10-point problem: ~6 minutes
- 12-point problem: ~7 minutes
- Spend extra time on high-point problems where you're close to solution

**Partial credit maximization:**
- Write out formula first (often worth points)
- Show substitution
- Even if arithmetic is wrong, you get method points
- Never leave blank — write something!

