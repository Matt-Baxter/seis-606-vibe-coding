# App Ideas for Vibe Coding

**Matt Baxter — SEIS 606-01, Homework 1**

Six web applications I would be interested in building in this course.

## 1. Superintelligence Homepage

A centralized, continuously updated home for what is being written and predicted about
superintelligence and recursive self-improvement. Material on the subject is scattered
across research papers, news coverage, essays, podcasts, and video, with no single place
that collects it — and anything that does exist tends to freeze the moment its author
stops maintaining it.

The site would organize sources into sections for timeline predictions, research papers
and news, and video and podcast media, with an emphasis on work published from 2023
onward. The central design challenge is keeping it current: new sources would be brought
in automatically rather than added by hand, so the page reflects an active field instead
of a snapshot. A paper I wrote on superintelligence risk would be linked from the site,
though the site itself would cover the subject more broadly than that paper's focus on
existential risk.

## 2. MMA Fight Predictor

Enter two UFC fighters and receive predicted odds for a bout between them, along with a
clear favorite. This builds on a fight predictor I developed previously as a personal
project, with three specific improvements in mind: stronger predictive accuracy, better
underlying data, and proper handling of edge cases — most obviously rejecting matchups
between fighters in incompatible weight classes.

The more important improvement is transparency. My earlier version is effectively a black
box: it produces a number I cannot explain, even as its author. This version would be
built so that the reasoning behind any individual prediction is visible and traceable,
both because that makes it a better tool and because understandable code is a standard
this course expects.

## 3. Tattoo Simulator

Describe a tattoo concept and see it rendered visually, with variations across styles —
black and grey versus color, traditional versus neo-traditional, and so on. The problem
it addresses is the gap between an idea in your head and something concrete enough to
discuss with an artist, which is the hardest part of commissioning a tattoo.

A natural extension would be uploading a photo of your own body rather than using a
generic rendering. The value there is narrower than it first appears, but two cases
justify it: skin tone, which meaningfully changes how ink reads, and existing tattoos,
which constrain what will work alongside them.

## 4. That's a Great Question

Begin with a prompt, a seed idea, or a question, and receive the most insightful and
critical questions worth asking in response. Any returned question can then be expanded
into further questions, letting a user follow a line of inquiry deeper rather than
stopping at a first answer.

What makes a question the *right* question is deliberately left open, because it is
context-dependent — a good question is relevant, revealing, and often uncomfortable, and
what qualifies differs across technical, social, and philosophical settings. That
ambiguity is the interesting part of the project rather than a gap in it, and the
application would be a way to explore which properties actually make a question valuable.

## 5. Date Idea Generator

Set a few constraints — time of day, indoor or outdoor, budget, whether food is involved,
location, day of the week, and desired atmosphere — and receive specific recommended
places to go. Deciding where to go is a genuinely difficult problem that existing tools
handle poorly: they either rank restaurants by rating or offer generic suggestions,
neither of which answers the question actually being asked.

The application would draw on live location data through a mapping service so
recommendations are real, currently open, and nearby, rather than drawn from a static list.

## 6. Mood Tracker

Record your mood twice daily, morning and evening, and track how it moves over time. The
application would also track habits such as meditation, prayer, exercise, or sleep, and
surface any relationships between those habits and mood.

The value depends on making daily entry fast enough to sustain over months, since
meaningful patterns only emerge from consistent long-run data. It also depends on
presenting findings responsibly — self-reported data from a single person produces
apparent correlations easily, and the application should be careful not to overstate what
it has actually found.

---

*Developed with the assistance of Claude, reviewed and edited by me.*
