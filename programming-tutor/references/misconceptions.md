# Common Programming Misconceptions and How to Address Them

A wrong answer or bug is rarely random — it usually comes from a consistent but faulty model of *what the machine does*. The tutor's job is to surface that model and break it, not just supply the fix (which leaves the faulty model intact to misfire on the next program). The most reliable fix is almost always **a case the learner predicts and runs themselves** — watching your own model produce output you know is wrong dislodges it far better than being told.

## How to use this file

Reach for it when an error looks *conceptual* (a consistent wrong model of execution) rather than a *slip* (a typo, a missing bracket, a one-off wrong name). Slips need "check that line"; misconceptions need the treatment below. Almost all of these trace back to a faulty **notional machine** — see `pedagogy.md`.

The fixes are language-agnostic in spirit; translate the counterexample into the learner's language.

---

## Variables, state, and assignment

**A variable is a box that holds a value.** This "box" model works until references appear, then breaks badly. In many languages a variable is a *label bound to* a value/object, not a container. Fix: when aliasing bites (below), switch to the label-and-arrow model and have them draw it.

**Assignment is mathematical equality.** Reading `x = x + 1` as an equation (impossible) instead of an instruction ("compute x+1, store back into x"). Fix: have them trace `x = 5; x = x + 1` and state x after each line. Name `=` as "becomes," not "equals."

**All lines are true at once.** Treating a program as static text where every line simultaneously holds, rather than a sequence mutating state over time. Fix: a trace table — value of each variable after each line. The whole point of programming clicks here.

**Assignment copies the object.** `b = a` then mutating `b` surprises them by changing `a`. For reference types, both names point at one object. Fix: box-and-arrow drawing; have them predict, then run, a mutation through one alias and observe the other change.

**`==` vs `=`.** Using assignment where comparison is meant (or vice versa). Fix: name them out loud — "becomes" vs "is equal to" — and read the buggy line aloud; the wrong verb exposes the bug.

## Equality and identity

**Identity vs. value equality.** `==`/`is`/`.equals` confusion: two distinct objects with equal contents may be value-equal but not identical. Fix: build two equal-content lists, compare with both operators, predict each result, run.

**Floating point is exact.** Expecting `0.1 + 0.2 == 0.3` to be true. Fix: have them print `0.1 + 0.2` and watch the trailing error appear; introduce tolerance comparison.

## Control flow

**Off-by-one / fencepost.** Loop runs one too many or too few times; confusion over inclusive vs. exclusive bounds. Fix: trace the loop variable's values explicitly for a tiny range; count the iterations by hand and compare.

**The condition is watched continuously.** Believing an `if` (or a `while` condition) re-checks the moment its variables change, like a spreadsheet. It's checked only when control reaches it. Fix: a trace where a variable changes *after* the `if`; predict whether the branch re-fires (it doesn't).

**Loop variable after the loop.** Assuming it equals the last in-range value, or is undefined, depending on the wrong model. Fix: print it after the loop; reconcile with how the loop actually terminates.

## Functions

**Print vs. return.** A function that prints "works" in the console, so they think it returns; then `result = f()` is empty/None. The single most common beginner function bug. Fix: have them assign the print-function's result to a variable and inspect it — the absence of a return value becomes concrete.

**Parameters are linked to the arguments.** Reassigning a parameter inside the function is expected to change the caller's variable (pass-by-value confusion); or, conversely, mutating a passed object is expected *not* to affect the caller (reference confusion). Fix: two experiments — reassign a parameter vs. mutate a passed object — predict and run each; the difference makes the value/reference split visible.

**Functions run when defined.** Expecting code inside a `def`/function body to execute at definition rather than at call. Fix: put a print in the body, define but don't call, run; nothing prints.

## Scope

**Everything is global / inner sees and writes outer freely.** Confusion over what's visible where, and especially over reading vs. *reassigning* an outer variable from inside a function. Fix: a minimal example where an inner reassignment doesn't leak out; trace which name lives where.

## Recursion

**Distrust of the recursive leap.** Trying to trace every level of a deep recursion and getting lost, instead of trusting the recursive call to handle the smaller case. Fix: verify the base case, then *assume* the recursive call is correct for n−1 and check only that the current step is right — the inductive shape.

**No base case / wrong base case.** Infinite recursion or wrong boundary. Fix: trace the chain of calls toward the base; have them find where it should stop and doesn't.

**Recursion has no state across calls.** Misunderstanding the call stack — each call has its own frame and locals. Fix: draw the stack growing and unwinding for a tiny input.

## Data structures

**Mutating a collection while iterating it.** Skipped elements or errors. Fix: trace indices as items are removed; the shifting positions explain the skips.

**Confusing a reference to a list with a copy of it.** Building a list of "rows" that are all the same underlying object. Fix: predict the result of mutating one row; run; watch them all change.

**Dictionary/hash key assumptions.** Expecting insertion order, or using a mutable/unhashable key. Fix: language-specific demo of the actual behavior.

## Types

**Dynamic typing means no types.** Thinking values are untyped, then hitting `"3" + 4`. Fix: print the type of each value; show the operation's behavior (concatenate vs. add vs. error) is type-driven.

**Implicit coercion is predictable / absent.** Surprises from automatic string↔number conversion (or the lack of it). Fix: predict a few mixed-type expressions, run, reconcile with the language's actual coercion rules.

## Concurrency and asynchrony

**Code waits for async work.** Expecting an async/awaited call, callback, or promise to have completed on the next line. Fix: log before/after and inside the callback; the out-of-order output makes the non-blocking model visible.

**Race conditions can't happen "in such simple code."** Assuming sequential intuition holds under concurrency. Fix: a minimal shared-counter example with interleaving; reason about an unlucky ordering.

## Errors and debugging

**The error message is noise to skip.** Ignoring the message and line number, guessing instead. Fix: read the message together, word by word, and map it to the line — half of debugging is reading the evidence.

**A bug is randomness to perturb away.** Changing things and re-running without a hypothesis. Fix: require a stated hypothesis before any change (see `pedagogy.md`, debugging-as-science).

## The superbug

**The computer understands intent.** The deepest novice misconception: believing the machine infers what you *meant* rather than executing exactly what you *wrote*. It underlies countless "but it should know what I want" frustrations. Fix: whenever it surfaces, return to literal execution — "the machine isn't interpreting your intent; let's read exactly what you told it to do, one line at a time."

---

## The general principle

Whatever the topic, the pattern repeats: identify the consistent wrong model of execution, then engineer a moment where the learner *predicts an output from their model, runs it, and watches the machine produce something else*. That self-generated contradiction does more than any correction you could state. Supply the correct model only after the faulty one has been dislodged — otherwise it lands on a belief that's still standing.
