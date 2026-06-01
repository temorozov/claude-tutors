# claude-tutors

Skills that make Claude tutor the way the best human teachers do — guiding you to the answer instead of handing it over, so you actually learn it.

## The problem they solve

AI tutors have one failure mode: they explain *too* well. A fluent answer feels like understanding — you nod, move on, and can't reproduce it a week later. Research on AI-assisted learning shows measurable skill decline in students who lean on generated answers.

These skills are engineered against exactly that. They make *you* do the thinking, and they're built on established education research — not vibes.

## The skills

| Skill | What it is |
|-------|-----------|
| [`tutor`](./tutor/) | Universal tutor for any subject. The shared engine below, plus a *path mode* for "I want to learn X." Used as the fallback when no specialist is installed. |
| [`math-tutor`](./math-tutor/) | Math, algebra through calculus, probability, and linear algebra — with a catalog of the specific misconceptions learners hold at each topic. |
| [`programming-tutor`](./programming-tutor/) | Programming, language-agnostic. Built on the *notional machine* (most bugs are a wrong model of execution) and teaches debugging as a scientific method, not random trial-and-error. |

## How they actually work

- **A hint ladder, not an answer.** One nudge per turn — diagnose, check the foundation, surface the strategy — and *you* produce the next step. Producing it is what builds the skill; receiving it doesn't.
- **It reads the situation first.** Stuck on a problem, wanting a concept explained, and checking finished work each demand a *different* response. Giving the wrong one is the most common way tutoring fails.
- **No "does that make sense?"** — a yes/no question that everyone answers "yes." Replaced with reconstruction and prediction: the only checks a confused learner can't fake with a nod.
- **A misconception catalog per subject.** Not generic tips — the exact wrong rules learners actually hold, each with a counterexample *you* compute yourself. Believe `(a+b)² = a²+b²`? You work out `(1+1)² = 4 ≠ 2` and watch your own rule break. That sticks; being told you're wrong doesn't.

Grounded in Skemp's relational understanding, du Boulay's notional machine, PRIMM, and cognitive load theory — sources in each skill's `references/`.

## Install

1. Download a skill folder as a ZIP — open it (e.g. [`math-tutor`](./math-tutor/)), click the green **Code** button → **Download ZIP**.
2. In [claude.ai](https://claude.ai): **Settings → Customize → Skills → +** → **Upload a skill**, then upload the ZIP.
3. Done — Claude uses it automatically when you study.

## Contributing

Have an idea for a skill? Open an issue or a pull request.
