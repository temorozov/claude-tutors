# Common Math Misconceptions and How to Address Them

A wrong answer is rarely random — it usually comes from a consistent but faulty rule the learner is applying. The tutor's job is to surface that rule and break it, not just to supply the right answer (which leaves the faulty rule intact to misfire next time). For each misconception below: the faulty belief, why it's seductive, and the move that fixes it. The most reliable fix is almost always **a counterexample the learner computes themselves** — being told you're wrong changes less than watching your own rule produce nonsense.

## How to use this file
Reach for it when an error looks *conceptual* (a consistent wrong rule) rather than a *slip* (a dropped sign, an arithmetic typo). Slips need "check that line again"; misconceptions need the treatment below.

---

## Arithmetic and number sense

**"Multiplication makes bigger, division makes smaller."** True for integers > 1, so it gets overgeneralized. Breaks on fractions/decimals. Fix: have them compute 6 × 0.5 and 6 ÷ 0.5 and reconcile it with "multiply = how many groups."

**Fraction addition by adding across.** `1/2 + 1/3 = 2/5`. Seductive because it mirrors fraction multiplication. Fix: a picture (half a pizza plus a third of a pizza is clearly more than 2/5 of a pizza) or the concrete check that 1/2 + 1/2 would "equal" 2/4 = 1/2, contradicting that two halves make a whole.

**Longer decimal = bigger.** 0.45 > 0.5 because "45 > 5." Fix: line them up by place value, or convert to money ($0.45 vs $0.50).

**Negative sign mishandling.** `-3² = 9` (vs the correct −9). Conflates "negative three squared" with "the negative of three squared." Fix: make the implied parentheses explicit and contrast `(-3)²` with `-3²`.

## Algebra

**The freshman's dream / illegal distribution.** `(a+b)² = a² + b²`; `√(a²+b²) = a+b`; `1/(a+b) = 1/a + 1/b`. The single most common algebra error class — distributing an operation that doesn't distribute. Fix: have them test on numbers — `(1+1)² = 4`, not `1+1 = 2`. Once they see their rule give 4 ≠ 2, the belief cracks. Then show the correct expansion.

**Cancelling terms instead of factors.** `(x+2)/2 = x`, "cancelling the 2s." Fix: numbers again — `(4+2)/2 = 3`, not 4. Emphasize you can only cancel *common factors of the whole top and bottom*, not pieces of a sum.

**Sign errors distributing a negative.** `-(x - 3) = -x - 3`. Fix: treat the negative as ×(−1) and distribute to *every* term.

**Equation vs expression confusion.** "Solving" `3x + 2` (which has nothing to solve), or randomly moving terms across a phantom equals sign. Fix: name the difference — an expression is a value, an equation is a claim two things are equal; you can only "solve" the latter.

**Inequality direction on multiply/divide by negative.** Forgetting to flip. Fix: test `−2x < 6` against a value, and show why dividing by −2 without flipping gives a false statement.

## Functions and graphs

**f(x+h) = f(x) + h, or f(a+b) = f(a)+f(b).** Treating every function as if it were linear. Fix: pick f(x)=x² and compute both sides.

**Confusing a function's value with its rate.** "f is increasing" vs "f is positive." Fix: a graph that's positive but decreasing (e.g. the right half of a downward line above the axis).

**Reading transformations backwards.** Thinking f(x − 3) shifts *left*. Fix: ask where the new graph hits the value the old one hit at x=0; solving x−3=0 gives x=3, i.e. right.

## Calculus

**Derivative of a product is the product of derivatives.** `(fg)' = f'g'`. Fix: test on f=g=x, where (x·x)' = 2x but x'·x' = 1.

**Treating dy/dx as a literal fraction everywhere.** Works often enough (chain rule, separable ODEs) to feel safe, then misfires. Fix: acknowledge *why* it often works (limits of ratios) and flag where it doesn't.

**∫ of a product is the product of integrals; chain-rule confusion.** Fix: a quick counterexample, then point at integration by parts / substitution as the real tools.

**"+C" amnesia** and forgetting the chain rule when integrating. Usually a slip, but if systematic, drill the "what derivative gives me this?" framing.

**Limit = the value you plug in.** Believing a limit is just substitution, so removable discontinuities are invisible to them. Fix: a function defined to differ from its limit at one point, or a 0/0 form that simplifies.

## Probability and statistics

**Gambler's fallacy.** "Five heads in a row, so tails is due." Fix: independence — the coin has no memory; recompute P(heads) after the streak.

**Confusing P(A|B) with P(B|A).** The base-rate / prosecutor's fallacy. Fix: a concrete frequency tree (out of 1000 people…) makes the asymmetry visible where percentages hide it.

**Correlation implies causation**, and ignoring confounders. Fix: a vivid counterexample (ice cream sales vs drownings, both driven by summer).

**"Statistically significant" = "large / important."** Conflating p-value with effect size. Fix: separate the two questions — "is there an effect" vs "how big is it."

**Average of averages.** Averaging two class averages without weighting by size. Fix: a small example with unequal group sizes.

## Linear algebra

**Matrix multiplication is commutative.** `AB = BA`. Seductive because scalar multiplication is commutative. Fix: two 2×2 matrices where AB ≠ BA — they can compute it themselves in under a minute.

**Transpose of a product: wrong order.** `(AB)ᵀ = AᵀBᵀ`. The correct identity is `(AB)ᵀ = BᵀAᵀ`. Fix: a 2×2 example; then ask why the order must reverse (think about what each row/column is dotting with).

**Determinant of a sum.** `det(A + B) = det(A) + det(B)`. Completely false — determinant is not linear in the matrix. Fix: let A = B = [[1,0],[0,1]]; then det(A+B) = det([[2,0],[0,2]]) = 4, but det(A) + det(B) = 1 + 1 = 2. They compute it themselves in thirty seconds.

**Eigenvectors are unique.** Any scalar multiple of an eigenvector is also an eigenvector (for the same eigenvalue), and an eigenspace can be multi-dimensional. Fix: show that if `Av = λv`, then `A(2v) = λ(2v)`.

**"Can't row-reduce to find the inverse; that changes the matrix."** Row reduction applies elementary row operations, which are invertible — they don't change the solution set of a system. Fix: explain that multiplying rows by scalars and adding rows are the same operations encoded in elementary matrices being multiplied on the left.

**Confusing the null space with the column space.** The null space is the set of inputs that map to zero; the column space is the set of reachable outputs. Fix: for a 3×2 matrix of rank 2, the column space lives in ℝ³ and the null space lives in ℝ².

## Discrete mathematics

**P(n,r) and C(n,r) are interchangeable.** Permutations count ordered arrangements; combinations count unordered subsets. Fix: "how many ways to pick 2 people from 3" — list them both ways and count the difference.

**Proof by example is proof.** Showing the statement holds for 10 cases does not prove it for all n. Fix: point to a statement true for n = 1…39 that fails at n = 40 (Euler's prime-generating polynomial, or similar). Then distinguish: a single *counter*example is sufficient to disprove a universal claim.

**Induction: the base case is sufficient.** The inductive step is mandatory — without it, "proving" 1 = 2 by induction is possible. Fix: show a fake proof that breaks because the inductive step assumes the wrong thing.

**∀ and ∃ are interchangeable, or their negations are symmetric.** The negation of ∀x P(x) is ∃x ¬P(x), not ∀x ¬P(x). Fix: "all dogs are friendly" vs "some dog is not friendly" as the concrete negation.

**A ⊆ B implies A ≠ B.** ⊆ means "subset or equal"; strict subset is ⊊. Fix: A ⊆ A is always true. Many students conflate ⊆ with <.

**Confusing the number of subsets with the number of elements.** A set with n elements has 2ⁿ subsets. Fix: list all subsets of {1, 2} — ∅, {1}, {2}, {1,2} — and count: 4 = 2².

---

## The general principle
Whatever the topic, the pattern repeats: identify the consistent wrong rule, then engineer a moment where the learner *applies their own rule and watches it produce something they know is false*. That self-generated contradiction does more than any correction you could state. Supply the correct rule only after the faulty one has been dislodged — otherwise it lands on top of a belief that's still standing.
