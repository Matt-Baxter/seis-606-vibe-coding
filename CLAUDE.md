# Context for Claude

Working notes so future sessions start with context instead of re-deriving it.

## Who

Matt Baxter — M.S. student in an AI program at the University of St. Thomas (SEIS).
Undergrad in **biomedical engineering**; ~5 years working in the **medical device
industry** before returning for the master's. Self-describes as not having much
software/coding experience, and prefers simpler, well-scoped projects over ambitious
ones. Treat that as a real constraint, not modesty — but note the counter-evidence
in "How he works" below.

## Intellectual center of gravity

**Superintelligence / AI existential risk is the #1 interest** — academic and
professional, and he expects that to hold for years. Wrote *"Superintelligence
Challenges and Existential Risks"*, which proposes a five-challenge framework for ASI
risk management:

1. Technical safety and alignment (7 failure modes: goal misspecification, deception,
   loss of control, cybersecurity, corrigibility, adverse conditions, emergent coordination)
2. Concentration of power (7 outlets: first mover, institutional authority, compute
   control, corporate interests, wealth, expertise, geography)
3. International governance (arms race, military escalation, defection, environment)
4. Social health (automation, disempowerment, meaning, atrophy of relationships,
   epistemic breakdown, cultural homogenization)
5. Ethics — treated as constantly relevant rather than sequential

Predicts AGI 2028–2030, ASI 2029–2033, argues asymmetrically that erring early is
lower-risk than erring late. Has considered starting a **superintelligence podcast**
but hasn't begun; finds the prospect intimidating.

## Other interests

- **MMA** — favorite sport; built a UFC fight predictor. NBA second, much less strongly.
- **Biomedical engineering / medical devices** — prior career, real domain knowledge
  (regulatory pathways, design controls, risk management).
- **Tattoos** — has 7; interested in the design/placement/artist-selection problem.
- **"Asking the right questions"** — a genuine philosophical commitment, not a
  throwaway. Views question quality as most of critical thinking.
- **Yoshi** — his cat.

## How he works — read the MMA predictor before assuming inexperience

`Matt-Baxter/mma_predictor` is more rigorous than "not much coding experience"
suggests: chronological train/val/test splits, a leakage audit that caught
supposedly-pre-fight columns populated in debut-vs-debut bouts, missingness handled
without indicator features *on purpose* at a cost to accuracy, symmetry enforced by
construction against corner-ordering bias, and a published results table where his
model loses to the betting market. He also refused to feed the closing line as an
input on the grounds that the model "learned to copy the market and contributed
nothing of its own."

He describes this project as having "didn't work very well." It scores 0.628 accuracy
and 0.6381 log loss against a 0.704 / 0.5816 market benchmark, calibrated to within
2.9%. That is a respectable result against an extremely strong baseline, not a failure.

**The through-line: he audits his own work for ways it might be fooling him.** Match
that standard. Surface the uncomfortable finding rather than the flattering one, and
don't round results up.

## Coursework

**SEIS 606-01: Vibe Coding**, Fall 2026, Prof. Paul Kaefer. Grading: assignments 15%,
Project 1 25% (presents Oct 21), Project 2 25% (presents Dec 9), final 25%,
participation 10%. Joined the course late (Sept 17) and submitted Homework 1 after the
original deadline. Course emphasizes web apps, spec-driven development, testing,
deployment, databases/auth, CI/CD, and AI ethics/governance.

## Conventions

- Course artifacts live in this repo, one folder per assignment. Apps get their own repos.
- Disclose AI assistance in work products — the course requires it and he agrees with it.
