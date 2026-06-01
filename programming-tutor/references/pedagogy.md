# Pedagogical Background (Programming)

This builds on the general learning science in the `tutor` skill (Skemp's relational vs. instrumental understanding, the illusion of competence, cognitive load, ZPD, Bloom). Below is what is *specific* to learning programming.

## The notional machine

A **notional machine** is the learner's mental model of how the computer executes code — what happens, step by step, when a program runs. The term (du Boulay, 1986) names the single most important construct in programming education: nearly every persistent bug and misconception is a discrepancy between the learner's notional machine and the real one.

A novice with a faulty notional machine writes code by pattern-matching surface syntax to remembered snippets. They can't predict what their own code will do, so they can't debug it — debugging *requires* a model to reason from. The expert's notional machine is accurate enough that they can "run the code in their head."

**Implication:** When something breaks or confuses, don't start with the fix. Find out what the learner thinks the machine does — usually by having them trace execution by hand. The gap between their trace and reality *is* the lesson. Teaching the notional machine is the highest-leverage thing a programming tutor does.

### State and time — the hardest shift

The deepest novice difficulty is seeing a program not as static text but as a *process that evolves state over time*. Lines are not simultaneously-true facts (as in math/algebra); they are instructions executed in sequence, each mutating state. `x = x + 1` is contradictory as an equation and obvious as an instruction. Until this shift happens, assignment, loops, and mutation all stay mysterious.

**Implication:** Make state and sequence visible constantly — trace tables, "what is each variable after this line," stepping a debugger. Reinforce that the program *does things in order*, it doesn't *describe* things.

## Tracing before writing

Research (notably the multi-institutional "Leeds" and McCracken studies) found that students who cannot *trace* code — predict its output by hand — also cannot *write* it. Comprehension precedes generation. A learner who can't say what a loop does cannot reliably author one.

**Implication:** Don't rush a struggling learner into writing more code. Have them read and trace working code first. "Predict the output, then run it" is the core exercise: a wrong prediction pinpoints the faulty model with surgical precision.

## PRIMM — a structured progression

PRIMM (Sentance et al.) sequences a programming lesson to delay writing-from-scratch until understanding is in place:

- **Predict** what a given program will do (no running yet).
- **Run** it and compare to the prediction — surface the gap.
- **Investigate** how it works (trace it, annotate it, change one thing).
- **Modify** it to do something slightly different.
- **Make** something new with the same pattern.

The progression moves from reading to writing, and from supported to independent. It directly attacks the illusion of competence: you cannot fake the Predict step.

**Implication:** When a learner is stuck or jumping ahead to "Make" without foundation, drop back down the PRIMM ladder. Predict and Investigate on working code build the model that Make requires.

## Cognitive load in programming

Programming overloads working memory badly: syntax, semantics, problem logic, and tooling all compete for the same ~4 slots. A beginner debugging a syntax error has no capacity left to reason about the algorithm.

**Implication:** Separate concerns. Don't make a learner fight syntax and logic simultaneously — resolve the syntax noise, then think about the algorithm. Use small, runnable examples. Introduce one new idea at a time. Worked examples (a fully traced example) cost less load than discovery for novices.

## Debugging is the scientific method, and it's teachable

Novices debug by random perturbation — changing things and re-running, hoping. Experts debug as hypothesis testing: observe the symptom, form a hypothesis about the cause, design a test that would confirm or refute it, change one variable, narrow. This is a learnable, transferable skill, and most self-learners are never taught it explicitly.

**Implication:** In debug mode, teach the *loop* (read evidence → hypothesize → localize → test one thing → generalize), not the specific fix. Force a hypothesis before any change ("what do you think is happening?"). The fix solves one bug; the method solves all future ones.

## The AI illusion of competence — sharper for code

The general illusion of competence (recognition mistaken for recall) is worse in programming because AI-generated code *runs*. Working output is far more convincing than a worked explanation: it compiles, it passes the happy path, so the learner concludes they understood it. They didn't — they recognized a solution. Studies of AI-assisted coding show measurable skill decline when learners lean on generated code.

**Implication:** Generating correct code for a learner is the most damaging thing this skill can do. The runnable-ness is exactly the trap. Counter it relentlessly with Predict / Reconstruct / Transfer — make them produce, not receive. A learner who needs you slightly less each session is the goal; one who ships your code learned nothing.
