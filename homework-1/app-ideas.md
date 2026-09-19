# App Ideas for Vibe Coding

**Matt Baxter — SEIS 606-01, Homework 1**

Eight web apps I might build in this course, ordered from easiest to hardest. Difficulty
is rated mostly by what the app *needs* rather than how clever it is: a static page is
easy, a page that remembers things is harder, and anything that needs a server, an
outside API, an AI model, or a scheduled job is harder still.

| Level | What it requires |
|---|---|
| 1 | Static page — HTML/CSS/JS plus a data file. Hosts free on GitHub Pages |
| 2 | Static page that remembers things in the browser. Still no server |
| 3 | A real backend — accounts, a database, data shared between users |
| 4 | Plus an outside service — maps, image generation, or a language model |
| 5 | Plus modeling, data pipelines, or scheduled ingestion |

---

## 1. Is It Toxic? — level 1

**What it does:** Search any plant, food, or household item and find out whether it is
dangerous to cats, with symptoms and severity.

**Why I want to build it:** I have a cat named Yoshi, and I have absolutely looked this
up mid-panic on a bad mobile site. The existing references are hard to search on a phone.

**Core features:** Instant search over a curated dataset; severity levels; symptoms to
watch for; works offline once loaded.

**Stack:** Static site, JSON dataset compiled from published toxicity references.

**Hardest part:** Source accuracy. The app needs a visible "not veterinary advice" line
and a cited source per entry, because being confidently wrong here has real consequences.

## 2. Superintelligence Quote Wall — level 1

**What it does:** A searchable, filterable collection of public statements about
superintelligence from AI lab leaders and researchers — filter by person, company, year,
or how aggressive the prediction is.

**Why I want to build it:** I assembled a version of this by hand for a paper I wrote on
superintelligence risk, and it was the single most-cited thing in it. These statements are
scattered across podcasts, blog posts, and interviews, and no one has centralized them.

**Core features:** Full-text search; filters; permanent source link and date on every
entry; shareable links to a single quote.

**Stack:** Static site over a hand-curated JSON file.

**Hardest part:** Verification. Every quote needs a primary source and a timestamp, and
paraphrases have to be excluded, or the whole thing is worthless.

## 3. Mood and Habit Tracker — level 2

**What it does:** Log mood twice daily, morning and evening, alongside habits like sleep,
exercise, meditation, or prayer. Shows trends over time and looks for relationships
between them.

**Why I want to build it:** Tracking this by hand never survives contact with a busy week,
and the interesting question — whether a habit actually moves anything — needs months of
consistent data to answer.

**Core features:** Fast two-tap daily entry; habit checklist; trend charts; export.

**Stack:** Static site with browser-local storage. Data never leaves the device, which is
a privacy guarantee and not just a shortcut.

**Hardest part:** Not lying with statistics. One person's daily self-reports produce
spurious correlations very easily. The app should refuse to display a relationship below a
minimum sample size and should show uncertainty rather than a clean number.

## 4. That's a Great Question — level 3

**What it does:** Give it a topic, a decision, or a claim, and it returns the most
insightful questions to ask about it — then lets you pick any one and break *it* down
further, going deeper down a branch.

**Why I want to build it:** I think asking the right question is most of the work in
thinking clearly, in technical work and everywhere else. What makes a question good is
context-dependent — revealing, relevant, uncomfortable — and exploring that space is
genuinely interesting to me.

**Core features:** Seed input; a generated set of questions; recursive drill-down; save a
question tree; rate questions so good ones can be studied.

**Stack:** Small backend holding the API key, calling a language model, plus a static
front end.

**Hardest part:** Language models are very good at producing *plausible* questions and
much worse at producing *insightful* ones. Left alone they generate "what are the risks?"
forever. The real work is grounding generation in an explicit taxonomy of question types —
assumption-surfacing, falsification, inversion, second-order effects, base rates — and then
finding an honest way to evaluate whether the output is actually any good.

## 5. Date Idea Generator — level 3–4

**What it does:** Set the constraints — time of day, budget, indoor or outdoor, food or
not, neighborhood, day of week, desired vibe — and get specific, real places to go.

**Why I want to build it:** Deciding where to go is genuinely hard, and every existing
tool either lists restaurants by rating or gives generic advice like "go bowling." Neither
answers the actual question.

**Core features:** Constraint filters; ranked suggestions with hours and distance; save
and reject options; shareable shortlist.

**Stack:** Static front end plus a place-data API. Starting with OpenStreetMap's Overpass
API rather than Google Places, since it needs no billing account.

**Hardest part:** Map data knows a place is a restaurant. It does not know whether it is
good for a third date. Vibe has to come from a curated layer I build myself, with the API
supplying only hours and location.

## 6. Tattoo Simulator — level 4

**What it does:** Describe a tattoo idea and see it rendered in several styles — black and
grey versus color, traditional versus neo-traditional versus fine-line — so you can react
to something visual before committing.

**Why I want to build it:** I have seven tattoos, and the hardest part every time is the
gap between an idea in my head and something I can hand to an artist. Words are a bad
medium for this.

**Core features:** Text description; style variants side by side; placement preview;
export a reference sheet to bring to an artist.

**Stack:** Static front end, backend holding the image generation API key, with rate
limiting so a public demo cannot run up a bill.

**Hardest part:** Two things. Generated imagery costs money per request and is uneven in
quality for this specific task. And there is a real ethical question about AI-generated
art in a field that is fundamentally a human craft — so the app should be explicitly
framed as generating references for the conversation *with* your artist, never as a
substitute for one. Skin tone is the one strong argument for supporting real photo uploads,
since ink reads very differently across skin tones and most sample imagery ignores that.

## 7. Superintelligence Homepage — level 4–5

**What it does:** A single well-organized home for everything being written and said about
superintelligence and recursive self-improvement — research papers, news, essays, podcasts,
talks — that keeps itself current instead of freezing the day I stop updating it. Separate
sections for timeline predictions, research, and media, with sources tagged by stance so a
reader can see the actual spread of expert opinion rather than one slice of it.

**Why I want to build it:** This is the subject I care most about, and the material is
scattered across arXiv, company blogs, YouTube, and Substack with no center. I wrote a
paper on superintelligence risk that would be linked here, but the site itself should be
broader and less focused on existential risk than that paper was.

**Core features:** Browsable, searchable, filterable source library; timeline-prediction
tracker; automated ingestion of new material on a schedule; an admin review queue where I
approve or reject before anything publishes.

**Stack:** Database plus admin authentication, a scheduled job (GitHub Actions) pulling
from the arXiv API, YouTube, and RSS feeds, and a front end over the approved set.

**Hardest part:** Curation, not code. "Everything about superintelligence" is an unbounded
firehose, and a growing share of it is machine-generated filler. The editorial judgment is
the actual product, which is why ingestion feeds a review queue rather than publishing
straight to the site.

## 8. Glass-Box Fight Predictor — level 5

**What it does:** Enter two UFC fighters and get a predicted probability for each, along
with a clear account of *why* — which factors moved the number, in which direction, by how
much.

**Why I want to build it:** I built a fight predictor before, as a personal project. It
works reasonably: it beats an Elo baseline and is well calibrated, though it does not beat
the betting market, and I do not think it can without data that isn't public. The real
problem is that the model is opaque even to me. I can't explain any individual prediction.

The interesting finding is in my own results: a logistic regression on the same features
scores 0.6415 log loss against the neural network's 0.6381. That gap is small enough that
an interpretable model costs almost nothing in accuracy — so this version optimizes for
explainability rather than chasing a number.

**Core features:** Fighter search; predicted probabilities; per-prediction feature
attribution; every input traceable to its source; explicit input validation, including
rejecting matchups across incompatible weight classes.

**Stack:** Python model, exported so predictions run in the browser; static front end.

**Hardest part:** Honest evaluation. Fight data leaks in subtle ways — "pre-fight" averages
that quietly include the fight itself, missing values that encode the outcome. Preventing
that is most of the work, and it has to be tested rather than assumed.

---

## AI disclosure

I developed these ideas in conversation with Claude, which helped me pressure-test
feasibility, identify the hardest part of each, and sharpen the scope. The interests and
the selection are mine, and I reviewed and edited everything above.
