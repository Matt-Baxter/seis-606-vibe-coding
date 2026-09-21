# v1 Scope — That's a Great Question

**Matt Baxter — SEIS 606-01, Homework 2 working notes**

Working note, not a deliverable. Settles what v1 of the app is before the specify phase,
so the specs have something concrete to describe. App repo:
[Thats-a-Great-Question](https://github.com/Matt-Baxter/Thats-a-Great-Question).

## What it is

That's a Great Question takes a seed — a topic, a claim, a half-formed idea, or a question —
and returns a small set of questions worth asking about it. Any returned question can be
opened to generate further questions about *that* question, letting the user follow a single
line of inquiry deeper rather than stopping at the first set. The app generates questions
only; it never answers them. Nothing is stored on a server and there are no accounts.

## In and out of v1

| In | Out |
|---|---|
| One text box for the seed, with a length cap | Answering the questions |
| Returns 3–5 questions | Accounts, login, sync across devices |
| Click any question to expand it into more | A database or any server-side storage |
| The inquiry tree stays visible as you go deeper | Shareable links |
| Clear loading state and plain-language errors | Rating or giving feedback on question quality |
| Works on a phone; keyboard navigable | Editing a generated question |

"It never answers them" is the load-bearing boundary. Without it the app drifts into being a
general chatbot.

## Decisions

### How questions are generated

A list of possible lines of inquiry (assumption, evidence, consequence, alternative,
stakeholder, definition, framing, precedent, incentive, failure mode, and others) lives
explicitly in a Python file. The model is given that list, works across it, and returns the
3–5 questions it judges strongest. Questions are returned unlabeled.

The list is written out in code rather than left implicit so it can be read, edited, and
explained — but it guides generation rather than constraining output.

**Rejected alternative:** returning exactly five questions, one per fixed category, each
labeled with its type. Testable, but formulaic — it produces the same five shapes every time
and substitutes a rigid taxonomy for the model's judgment about what actually matters in
context.

### What "a good question" means

Deliberately left open. This was the interesting part of the original app idea and it stays
that way. The consequence is a split that the specs need to respect:

- **Verification (automated):** 3–5 questions returned, each non-empty, distinct from one
  another, distinct from the seed, within a length bound. Checkable by tests.
- **Quality (human judgment):** whether the questions are actually insightful. Not
  automatable, and assessed by review rather than by the test suite.

No automated test can judge whether a question is good, and a metric claiming to would be
false precision. Naming the split is more honest than inventing a number.

### Depth

No limit. Expansion continues as far as a user wants to go.

Implication: at depth 10+, the model needs some ancestry to stay on topic, but passing the
entire chain grows the prompt without bound. Approach — pass the full chain from seed to
current question, and if it ever grows too large, keep the seed plus the most recent few
links. Bounds drift without capping depth.

Open for the mockup: an indented tree runs off the side of a phone screen at depth 15. The
data is unlimited; the display needs to handle deep chains differently from shallow ones.

### Persistence

None. A page refresh gives a clean start. Browser storage is permitted by the constitution
but is not core to the idea and carries its own failure cases.

## Stack

Python serverless backend, plain HTML/CSS/JS frontend, hosted on Vercel, question generation
via the Anthropic Claude API. The API key stays server-side — browser code is readable by
anyone who loads the page. Recorded in the constitution.

---

*Developed with the assistance of Claude, reviewed and edited by me.*
