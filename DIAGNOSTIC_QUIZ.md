# DIAGNOSTIC QUIZ

**Instructions:** Answer all 10 questions. Show minimal working where needed. Time: 20 minutes.

**1.** How many ways can 5 books be arranged on a shelf?

**2.** A committee of 3 is chosen from 8 people. How many different committees are possible?

**3.** How many 4-digit numbers can be formed using digits 1-9 with repetition allowed?

**4.** State the three Kolmogorov axioms of probability.

**5.** If P(A) = 0.6 and P(B) = 0.5, what are the minimum and maximum possible values of P(A ∩ B)?

**6.** A fair die is rolled twice. What is the probability that the sum is 7?

**7.** Define conditional probability P(A|B) in terms of P(A∩B) and P(B).

**8.** Events A and B satisfy P(A) = 0.4, P(B) = 0.6, P(A∩B) = 0.24. Are A and B independent?

**9.** A box contains 5 red and 3 blue balls. Two balls are drawn without replacement. What is P(both red)?

**10.** How many non-negative integer solutions are there to x₁ + x₂ + x₃ = 10?

---

## DIAGNOSTIC QUIZ — ANSWER KEY

**1.** 5! = 120

**2.** C(8,3) = 56

**3.** 9⁴ = 6,561

**4.** (i) P(A) ≥ 0 for all events A; (ii) P(Ω) = 1; (iii) For disjoint events A₁, A₂, ...: P(A₁ ∪ A₂ ∪ ...) = P(A₁) + P(A₂) + ...

**5.** Minimum: 0.1; Maximum: 0.5

**6.** 6/36 = 1/6

**7.** P(A|B) = P(A∩B) / P(B), provided P(B) > 0

**8.** Yes (since 0.4 × 0.6 = 0.24 = P(A∩B))

**9.** (5/8) × (4/7) = 20/56 = 5/14

**10.** C(12,10) = C(12,2) = 66

---

## SCORING GUIDE

- **Questions 1-3, 6, 9-10:** 10 points each (straightforward computation)
- **Question 4:** 15 points (must state all three axioms correctly)
- **Question 5:** 10 points (5 pts for min, 5 pts for max with brief justification)
- **Question 7:** 10 points (correct formula)
- **Question 8:** 15 points (must check independence condition and conclude)

**Total: 100 points**

**Passing score:** 60/100

---

## DIAGNOSTIC INTERPRETATION

**90-100:** Excellent foundation. Ready for advanced topics.

**70-89:** Good understanding. Review weak areas before midterm.

**50-69:** Fair grasp. Significant study needed in combinatorics and conditional probability.

**Below 50:** Foundational gaps. Strongly recommend working through basic examples in all three chapters before attempting midterm.

---

## COMMON MISTAKES TO WATCH FOR

**Q1:** Using C(5,5) instead of 5! (confusing arrangement with selection)

**Q2:** Using P(8,3) instead of C(8,3) (order doesn't matter for committees)

**Q3:** Using 10⁴ instead of 9⁴ (digits are 1-9, not 0-9)

**Q5:** Not using Bonferroni inequality for minimum: max(0, P(A)+P(B)-1)

**Q8:** Checking P(A|B) = P(A) instead of the definition P(A∩B) = P(A)P(B)

**Q9:** Treating as "with replacement" and using (5/8)²

**Q10:** Using C(10,3) instead of C(12,2) (stars-and-bars confusion)
