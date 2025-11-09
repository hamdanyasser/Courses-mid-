# SAMPLE MIDTERM 1 (BEGINNER)

---

## MIDTERM (STUDENT COPY)

**MATH 204 – Probability and Statistics**
**Midterm Examination 1 (Beginner Level)**
**Instructor: [Name]**
**Date: [Term/Year]**
**Duration: 60 minutes**
**Total: 100 points**

**Instructions:** Show all work. No calculators with symbolic capability. Justify all answers.

---

**Exercise 1 (20 points): Basic Counting**

**(a)** [8 pts] A password consists of 3 letters (A-Z) followed by 2 digits (0-9). How many different passwords are possible if repetition is allowed?

**(b)** [12 pts] From a class of 10 students, a teacher must select a president, vice-president, and secretary (all different). How many ways can this be done?

---

**Exercise 2 (25 points): Combinations and Distributions**

**(a)** [10 pts] A committee of 4 is chosen from 6 men and 5 women. How many committees contain exactly 2 men and 2 women?

**(b)** [15 pts] How many ways can 8 identical candies be distributed to 3 children such that each child receives at least one candy?

---

**Exercise 3 (20 points): Sample Spaces and Probability Axioms**

**(a)** [8 pts] A fair coin is flipped three times. List the sample space and find P(exactly two heads).

**(b)** [12 pts] Events A and B satisfy P(A) = 0.5, P(B) = 0.4, and P(A∪B) = 0.7. Find P(A∩B).

---

**Exercise 4 (20 points): Conditional Probability**

**(a)** [12 pts] An urn contains 4 red balls and 6 blue balls. Two balls are drawn without replacement. What is the probability both are red?

**(b)** [8 pts] Given the setup in (a), if the first ball drawn is red, what is the probability the second ball is blue?

---

**Exercise 5 (15 points): Independence**

Three coins are flipped independently: one fair coin, one biased coin with P(H) = 0.6, and one biased coin with P(H) = 0.3.

**(a)** [8 pts] What is the probability all three show heads?

**(b)** [7 pts] What is the probability at least one shows heads?

---

## ANSWER KEY

**Exercise 1:**
(a) 26³ × 10² = 17,576 × 100 = 1,757,600
(b) P(10,3) = 10 × 9 × 8 = 720

**Exercise 2:**
(a) C(6,2) × C(5,2) = 15 × 10 = 150
(b) C(7,2) = 21 [stars-and-bars: distribute 8-3=5 remaining candies among 3 children after giving each 1]

**Exercise 3:**
(a) Ω = {HHH, HHT, HTH, HTT, THH, THT, TTH, TTT}; P(exactly 2 heads) = 3/8
(b) P(A∩B) = P(A) + P(B) - P(A∪B) = 0.5 + 0.4 - 0.7 = 0.2

**Exercise 4:**
(a) (4/10) × (3/9) = 12/90 = 2/15
(b) P(2nd blue | 1st red) = 6/9 = 2/3

**Exercise 5:**
(a) 0.5 × 0.6 × 0.3 = 0.09
(b) 1 - P(all tails) = 1 - (0.5 × 0.4 × 0.7) = 1 - 0.14 = 0.86

---

## TEACHER NOTES

### Marking Rubric

**Exercise 1(a):** [8 points]
- 3 pts: Identify 26³ for letters
- 2 pts: Identify 10² for digits
- 3 pts: Multiply correctly and arrive at final answer

**Exercise 1(b):** [12 points]
- 4 pts: Recognize ordered selection (permutation)
- 4 pts: Set up P(10,3) correctly
- 4 pts: Compute correct answer

**Exercise 2(a):** [10 points]
- 5 pts: Calculate C(6,2) for men
- 5 pts: Calculate C(5,2) for women and apply product rule

**Exercise 2(b):** [15 points]
- 7 pts: Apply stars-and-bars method (pre-allocate 1 candy to each child)
- 4 pts: Set up C(7,2) or equivalent
- 4 pts: Compute correct final answer

**Exercise 3(a):** [8 points]
- 4 pts: List complete sample space (all 8 outcomes)
- 4 pts: Identify 3 favorable outcomes and compute 3/8

**Exercise 3(b):** [12 points]
- 6 pts: Apply addition rule formula P(A∪B) = P(A) + P(B) - P(A∩B)
- 6 pts: Rearrange and compute correct answer

**Exercise 4(a):** [12 points]
- 6 pts: First draw probability 4/10
- 6 pts: Second draw conditional probability 3/9 and multiply correctly

**Exercise 4(b):** [8 points]
- 4 pts: Recognize conditional probability setup
- 4 pts: Calculate 6/9 and simplify to 2/3

**Exercise 5(a):** [8 points]
- 4 pts: Recognize independence allows multiplication
- 4 pts: Compute correct product 0.09

**Exercise 5(b):** [7 points]
- 4 pts: Use complement strategy (1 - P(all tails))
- 3 pts: Calculate correctly

### Partial Credit Guidelines

- **Methodology over arithmetic:** If a student sets up the correct formula/approach but makes an arithmetic error, award at least 60% of points for that part.
- **Ex 2(b):** If student uses stars-and-bars correctly but miscalculates the binomial coefficient, award 7-10/15.
- **Ex 4:** If student treats as "with replacement" but shows clear work, award 4/12 for Ex 4(a).
- **Ex 5(b):** If student attempts direct enumeration instead of complement, award points for any correct probability calculations even if approach is inefficient.

### 60-Minute Time Management Strategy

**Recommended allocation:**
- **Exercise 1:** 10 minutes (straightforward counting)
- **Exercise 2:** 15 minutes (requires careful setup, especially part b)
- **Exercise 3:** 12 minutes (part a quick, part b requires formula)
- **Exercise 4:** 12 minutes (conditional probability requires thought)
- **Exercise 5:** 10 minutes (independence and complement)
- **Review:** 1 minute

**Student strategy advice:**
1. Start with Exercise 1 (builds confidence, easiest points)
2. Move to Exercise 3 and Exercise 4 (moderate difficulty)
3. Then Exercise 2 and Exercise 5 (require more careful setup)
4. If stuck on a part, move on and return if time permits
5. Always show setup/formula even if uncertain about computation

### Common Student Errors to Watch For

1. **Ex 1(b):** Using C(10,3) instead of P(10,3) — order matters for distinct positions
2. **Ex 2(b):** Forgetting to subtract 3 before applying stars-and-bars
3. **Ex 3(a):** Listing fewer than 8 outcomes or miscounting heads
4. **Ex 4(a):** Using (4/10)² — failing to account for "without replacement"
5. **Ex 5(b):** Computing P(at least one heads) as 0.5 + 0.6 + 0.3 — wrong approach

### Exam Integrity

Remind students that academic honesty policies apply. This is an individual assessment. Proctoring recommended for in-person exams; lockdown browser for online administration.

---

## THREE TARGETED PRACTICE PROBLEMS

These problems are NOT on the exam but provide additional practice for weak areas.

### Practice Problem 1: Advanced Combinations
**Problem:** How many 5-card hands from a standard 52-card deck contain exactly 3 aces?

**Hint:** Choose 3 aces from 4 available aces, then choose 2 non-aces from the remaining 48 cards. Use product rule.

**One-line answer:** C(4,3) × C(48,2) = 4 × 1,128 = 4,512

---

### Practice Problem 2: Addition Rule with Overlap
**Problem:** A die is rolled. Event A = "roll is even", Event B = "roll > 3". Find P(A∪B).

**Hint:** List outcomes in A = {2,4,6} and B = {4,5,6}. Find A∩B, then use addition rule: P(A∪B) = P(A) + P(B) - P(A∩B).

**One-line answer:** P(A) = 3/6, P(B) = 3/6, P(A∩B) = 2/6, so P(A∪B) = 3/6 + 3/6 - 2/6 = 4/6 = 2/3

---

### Practice Problem 3: Law of Total Probability
**Problem:** Box 1 has 2 red and 3 blue balls. Box 2 has 4 red and 1 blue ball. A box is chosen uniformly at random, then a ball is drawn. What is P(red)?

**Hint:** Use law of total probability. Partition by box choice: P(red) = P(red|Box 1)×P(Box 1) + P(red|Box 2)×P(Box 2).

**One-line answer:** P(red) = (2/5)(1/2) + (4/5)(1/2) = 1/5 + 2/5 = 3/5

---

## ADDITIONAL NOTES FOR INSTRUCTORS

### Difficulty Calibration
This is a **beginner-level** midterm suitable for:
- Students 3-4 weeks into a probability course
- First assessment after covering basic counting and probability
- Students with limited prior exposure to probability

### Learning Objectives Assessed
- **Combinatorial analysis:** Basic permutations, combinations, stars-and-bars
- **Probability axioms:** Sample space enumeration, addition rule
- **Conditional probability:** Definition, without replacement scenarios
- **Independence:** Recognition and application

### Expected Performance
- **A range (85-100):** 20-30% of students
- **B range (70-84):** 30-40% of students
- **C range (60-69):** 20-30% of students
- **Below 60:** 10-20% (indicates need for intervention)

If class average is below 65, consider additional review sessions on stars-and-bars and conditional probability before next assessment.
