# Session handoff — Homework 2 in progress

Working note. Written when the working session moved to one rooted in the app repo
(`Thats-a-Great-Question`) so the SpecKit slash commands load. Everything below is state
that is not already recorded in a committed file.

## Where things stand

| Step | Status |
|---|---|
| 1. Decide app idea | Done — idea #4, "That's a Great Question" |
| 2. Install SpecKit | Done — `specify init . --integration claude`, committed |
| 3. Read constitution tutorial (Ch. 2) | Done |
| 4. Scope v1 | Done — see `scope-note.md` |
| 5. Write constitution | Done — v1.0.0, committed to app repo |
| 6. Read specify tutorial (Ch. 3) | Done |
| 7. Write specs | **Next** |
| 8. UI mockup | Not started |
| 9. README, commit, push | Not started |
| 10. Submit repo link | Not started |

Due Wednesday Sept 23, 5:15 PM. Submission is the app repo link.

## Setup facts that are easy to get wrong

- SpecKit was installed with the **Claude** integration. Commands are `/speckit-constitution`,
  `/speckit-specify` — **hyphens, not dots**. The tutorial shows dots; that syntax does nothing
  here.
- Slash commands only load when the agent session is rooted in the app repo directory. A session
  rooted elsewhere can still edit the files, but the commands will not appear.
- No `before_specify` extension hook is installed, so `/speckit-specify` will **not** create a git
  branch. The spec lands on `main` at `specs/NNN-<name>/spec.md`.
- There is no `.gitignore` in the app repo yet. The constitution requires one before any API key
  goes near the project.

## Open decisions

### Spec format — undecided, needs a choice before writing

The assignment says to follow the class format (Objective, Behavior, Constraints, Verification).
The linked tutorial produces a different nine-section structure. Slide 31 is titled "The spec
prompt format", which suggests O/B/C/V describes the prompt rather than the output document.
Three ways to resolve it:

1. Nine-section spec, O/B/C/V used only to structure the prompt.
2. Nine-section spec, with each numbered requirement (REQ-NNN) written as O/B/C/V. Satisfies both
   readings and gives the traceability the constitution promises. **Recommended.**
3. Spec written purely as O/B/C/V, dropping the tutorial's structure.

### Target users and user journeys — never discussed

Two of the nine template sections have no input yet. The only user identified so far is the
author. This is the main gap to fill before drafting.

## Carry-over from Chapter 3

- Specs describe WHAT and WHY only. The stack (Python, Vercel, Claude API) belongs to the
  constitution and the later plan phase, **not** the spec.
- The tutorial's own example fills Success Metrics with unmeasurable claims ("users prefer it over
  other weather sites"). That contradicts the class format's demand for testable verification.
  Follow the class format here.
- `/speckit-clarify` exists and asks targeted questions about underspecified areas. Optional for
  this assignment, useful given the known soft spot around question quality.

## Note on the constitution

It was written before v1 was scoped. That worked because it covers standards rather than features,
but it is worth a re-read once the spec exists, in case scoping surfaced something it should say.

---

*Developed with the assistance of Claude, reviewed and edited by me.*
