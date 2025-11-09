# EXAM CHECKLIST & FINAL SUMMARY

## PRE-EXAM CHECKLIST (Night Before)

### ✓ Formulas Memorized
- [ ] Product and Sum rules
- [ ] $P(n,r) = \frac{n!}{(n-r)!}$
- [ ] $\binom{n}{r} = \frac{n!}{r!(n-r)!}$
- [ ] Stars and bars: $\binom{n+r-1}{r}$
- [ ] Inclusion-exclusion (2 and 3 sets)
- [ ] Derangements: $D_n \approx n!/e$
- [ ] $P(A^c) = 1 - P(A)$
- [ ] $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
- [ ] $P(A|B) = \frac{P(A \cap B)}{P(B)}$
- [ ] $P(A \cap B) = P(A)P(B|A)$
- [ ] LOTP: $P(A) = \sum P(A|B_i)P(B_i)$
- [ ] Bayes: $P(B|A) = \frac{P(A|B)P(B)}{P(A)}$
- [ ] Independence: $P(A \cap B) = P(A)P(B)$

### ✓ Key Concepts Clear
- [ ] Order matters → permutation; order doesn't → combination
- [ ] Identical objects into distinct bins → stars and bars
- [ ] "At least one" → use complement
- [ ] Conditional probability: restrict to given event's universe
- [ ] LOTP: break into exhaustive cases
- [ ] Bayes: reverse the conditional
- [ ] Independence: multiply probabilities; NOT same as disjoint
- [ ] Disjoint events are dependent (if both have positive probability)

### ✓ Common Traps Reviewed
- [ ] Don't confuse $P(A|B)$ with $P(B|A)$
- [ ] Don't forget to subtract overlap in $P(A \cup B)$
- [ ] Stars and bars is $n+r-1$, not $n+r$
- [ ] Without replacement changes probabilities
- [ ] Complement of "at least 1" is "0", not "at most 1"
- [ ] Check independence before multiplying

### ✓ Materials Prepared
- [ ] Calculator with fresh batteries
- [ ] Pencils and eraser
- [ ] Watch or timer to track pace
- [ ] Student ID and any required materials

### ✓ Mental Preparation
- [ ] Reviewed both mini-midterms
- [ ] Identified weak topics and reviewed them
- [ ] Got 7-8 hours of sleep
- [ ] Ate a good breakfast
- [ ] Arrived early to exam room

---

## EXAM DAY STRATEGY

### First 2 Minutes: Survey
1. **Quick scan** of all problems
2. **Mark** easy/medium/hard
3. **Note** point values
4. **Plan** time allocation

### Problem-Solving Protocol

**For EACH problem:**

**STEP 1: READ CAREFULLY** (15 seconds)
- What exactly is being asked?
- What type of problem is it?
- What information is given?

**STEP 2: CLASSIFY** (10 seconds)
- Counting or probability?
- If counting: order matters? repetition?
- If probability: conditional? independent? complement?

**STEP 3: SET UP** (30-60 seconds)
- Write down relevant formula
- Define events clearly
- Draw diagram if helpful (tree, Venn, etc.)

**STEP 4: SOLVE** (2-4 minutes)
- Show all work step-by-step
- Check units and reasonableness as you go
- Don't skip steps (partial credit!)

**STEP 5: VERIFY** (15 seconds)
- Is probability between 0 and 1?
- Does answer make intuitive sense?
- Did you answer what was asked?
- Box or highlight final answer

---

## TIME ALLOCATION GUIDE

**For 60-minute, 100-point exam:**

| Point Value | Time Budget | Strategy |
|-------------|-------------|----------|
| 8-10 pts | 5-6 min | Usually straightforward; don't linger |
| 12-15 pts | 7-9 min | Medium difficulty; show work carefully |
| 20+ pts | 12-15 min | Often multi-part; budget time per part |

**Recommended pacing:**
- **Minutes 0-20:** All easy/medium problems you know cold
- **Minutes 20-45:** Harder problems; show setup even if stuck
- **Minutes 45-55:** Toughest problems; get partial credit
- **Minutes 55-60:** Review, check arithmetic, ensure all answered

**If stuck (>2 min on one problem):**
1. Write down what you know
2. Set up the equation/formula
3. Move on and come back later
4. Even incomplete work gets partial credit

---

## TOPIC-SPECIFIC QUICK CHECKS

### COMBINATORICS Problems

**Before you calculate, ask:**
- [ ] Does order matter? (If yes → permutation; if no → combination)
- [ ] Is repetition allowed?
- [ ] Are objects identical or distinct?
- [ ] Can I use complement to simplify?

**Red flags:**
- Getting a fractional count (check your formula!)
- Answer seems unreasonably large (overcounting?)
- Forgot to account for constraint

**Formula check:**
- Permutation: includes $(n-r)!$ in denominator
- Combination: includes both $r!$ and $(n-r)!$ in denominator
- Stars and bars: $n+r-1$ not $n+r$

---

### PROBABILITY Problems

**Before you calculate, ask:**
- [ ] Is this uniform probability? (Can I use counting?)
- [ ] Is this conditional? (Do I need $P(A|B) = \frac{P(A \cap B)}{P(B)}$?)
- [ ] Are events independent? (Can I multiply?)
- [ ] Is complement easier? (Especially for "at least one")
- [ ] Do I need to partition? (Use LOTP)
- [ ] Do I need to reverse conditional? (Use Bayes)

**Red flags:**
- Probability > 1 or < 0 (error in calculation!)
- Used $P(A) \times P(B)$ without confirming independence
- Confused $P(A|B)$ with $P(B|A)$
- Added probabilities for non-disjoint events without subtracting overlap

**Formula check:**
- Conditional probability: intersection in numerator, condition in denominator
- Bayes: use LOTP for denominator if not given
- Independence: verify before multiplying

---

## PARTIAL CREDIT MAXIMIZATION

**Even if you can't solve completely:**

✓ **Write the relevant formula** (often worth 20-30% of points)

✓ **Define your notation** ($A$ = event, $n$ = sample size, etc.)

✓ **Show setup** (substitute given values into formula)

✓ **Explain your reasoning** (brief: "Use complement since...")

✓ **Attempt calculation** even if unsure (arithmetic errors get more credit than blank)

✗ **DON'T leave blank** — no work = no points

✗ **DON'T erase completely** — wrong attempt is better than nothing

**Example of good partial credit work:**
```
Problem: P(at least one head in 5 flips)?

Use complement: P(≥1 head) = 1 - P(no heads)
P(no heads) = P(all tails) = (1/2)^5 = 1/32
P(≥1 head) = 1 - 1/32 = 31/32

[Even if you made arithmetic error, you'd get points for method]
```

---

## LAST-MINUTE REMINDERS

### The Big Three Traps
1. **$P(A|B) \neq P(B|A)$** — Read direction carefully!
2. **Disjoint ≠ Independent** — Opposite concepts
3. **"At least one" → complement** — Almost always easier

### The Big Three Formulas
1. **Conditional:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$
2. **LOTP:** $P(A) = \sum P(A|B_i)P(B_i)$
3. **Bayes:** $P(B|A) = \frac{P(A|B)P(B)}{P(A)}$

### The Big Three Strategies
1. **Complement** for "at least" problems
2. **Partition** when you can't compute directly
3. **Draw a picture** (tree, Venn, table) when confused

---

## POST-EXAM IMMEDIATE DEBRIEF

**Right after exam (5 minutes):**

Write down:
- [ ] Problems you felt confident on
- [ ] Problems you struggled with
- [ ] Concepts that were tested heavily
- [ ] Any surprises or unexpected question types

This helps you:
- Identify patterns in what's tested
- Know what to review for next exam
- Reduce anxiety (you did your best!)

**DON'T:**
- Discuss specific answers with classmates (causes anxiety)
- Try to reconstruct exact answers (what's done is done)
- Dwell on mistakes (focus on learning for next time)

---

## CONFIDENCE BOOSTERS

**You've prepared by:**
✓ Mastering all core formulas and theorems
✓ Solving 100+ practice problems
✓ Taking 2 full practice exams
✓ Reviewing heuristics and common traps
✓ Creating summary sheets and flashcards
✓ Following a structured 12-hour study plan

**You are READY for this exam!**

**During the exam:**
- Take deep breaths if you feel stuck
- Remember: you know this material
- Trust your preparation
- Show your work and move forward

**After the exam:**
- You did your best
- Probability is challenging — everyone struggles
- One exam doesn't define you
- Learn from it and move on

---

## FINAL FORMULA SHEET (Absolute Essentials)

**COUNTING:**
1. $P(n,r) = \frac{n!}{(n-r)!}$, $\binom{n}{r} = \frac{n!}{r!(n-r)!}$, $\binom{n+r-1}{r}$ (stars/bars)

**PROBABILITY AXIOMS:**
2. $P(A^c) = 1-P(A)$, $P(A \cup B) = P(A)+P(B)-P(A \cap B)$

**CONDITIONAL & INDEPENDENCE:**
3. $P(A|B) = \frac{P(A \cap B)}{P(B)}$, $P(A \cap B) = P(A)P(B|A)$
4. LOTP: $P(A) = P(A|B)P(B) + P(A|B^c)P(B^c)$
5. Bayes: $P(B|A) = \frac{P(A|B)P(B)}{P(A)}$
6. Independence: $P(A \cap B) = P(A)P(B)$

**Memorize these six — everything else derives from them!**

---

## GOOD LUCK! 🍀

Remember:
- **Breathe**
- **Read carefully**
- **Show your work**
- **Trust your preparation**

You've got this! Now go ace that exam! 💪

