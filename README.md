# “Results Center Project”
> _ElectionBuddy Coding Challenge_

## Purpose

We want to see **how you think, code, and communicate** by asking you to implement a focused feature slice of our domain. You’ll build a small Rails service that publishes election results in a *Results Center* style page/API. The exercise is **time‑boxed to \~4 hours**. Finish the *Core* section first; the *Extra Layers* are purely optional if you have remaining time.

---

## Scenario

> *“ElectionBuddy is rolling out a lightweight `Mini Results Center` for organizations that run just a handful of simultaneous votes.
> Your task is to add this capability to a stripped‑down Rails code base that already contains `Election`, `Question`, `Answer`, `Voter`, and `Ballot` models with seed data.”*

You will implement a single public endpoint and (optionally) a minimal HTML view. The endpoint should work for a small election but be designed so it can evolve for more complex ballot types, live updates, and auditing.

---

## Reference Materials

Check the [Wiki](https://github.com/electionbuddy/results-center/wiki) for some extra context and useful information!

---

## Using AI Assistance

Feel free to use **AI pair‑programming tools (ChatGPT, Copilot, etc.)**. During review we will look for:

* Evidence you understand and can explain any generated code.
* Cleanup of irrelevant or low‑quality suggestions.
* Thoughtful commit messages—avoid one huge “AI dump” commit.

Using AI is permitted and encouraged, but your judgment and editing will be visible in the git history.

---

## Repository / Setup & Tooling

1. **Fork** this repository to your GitHub account.
2. **Clone** your fork locally.
3. **Run** the project for the first time.
    - _The project contains a minimal Rails app with containerisation support. But feel free to use your preferred setup._
4. **Start** coding!


---

## Core Requirements (\~2 h)

| # | Deliverable | Why We Care |
| - | ----------- | ----------- |
| 1 | **`GET /results/:election_id`** JSON returning winners, total votes, and basic percentages for each question (simple plurality). | Demonstrates domain understanding & Ruby skills |
| 2 | Plain‑text or minimal HTML **public page** that consumes the same JSON. | Shows quick UI wiring |
| 3 | Unit spec(s) for the result calculator. | We value tested code |
| 4 | Short README (< 1 page) explaining architecture & trade‑offs. | Clear communication |

Focus on correctness and clarity; scope creep is the enemy.

---

## Extra Layers (choose any, total ≤ 2 h)

Pick what interests you—each layer is independent and progressively deeper.

**A. Strategy Pattern** — Extract vote‑counting into a pluggable `TallyStrategy` interface and add *Ranked‑Choice / IRV* as a second strategy.

**B. Results Center HTML** — Build a responsive view with percentages + a bar chart (Stimulus or plain JS).

**C. Live Updates** — Push partial results via ActionCable/WebSockets as ballots arrive.

**D. Audit Log** — Expose a timeline of result‑affecting events (ballot cast, question added).

**E. Performance** — Stress‑test with 100 k ballots (faker script) and optimise calculations.

Unfinished layers never penalise you—only completed work is evaluated.

---

## Submission

* Push your solution to a **public GitHub repo** (do **NOT** open a PR against ElectionBuddy).
* Include setup notes (`rails db:setup && rails s`, or `docker compose up`).
* Email the link to your recruiter contact.

---

## What We Evaluate

| Area        | Signals We Look For                                             |
| ----------- | --------------------------------------------------------------- |
| Correctness | Endpoint returns accurate winners (we run specs)                |
| Design      | Clear objects, single responsibility, SOLID mindset             |
| Tests       | Appropriate coverage and meaningful names                       |
| Git History | Small, descriptive commits                                      |
| Docs        | Easy to run and understand your decisions                       |
| Extras      | If you tackled layers beyond Core, is the implementation clean? |

---

## FAQ

* **“I only had 3 h and didn’t finish extras.”** No problem—focus on delivering Core well.
* **“Can I use AI tools like ChatGPT or Copilot?”** Yes! Review and refine AI output so it meets your standards (see *Using AI Assistance* above).
* **“Should I containerise with Docker?”** Encouraged. A one‑command `docker compose up` setup streamlines review.
* **“Do I need fancy UI?”** Functional beats pretty, but enhance if you like.
* **“What if something seems ambiguous?”** Note your assumption in the README and continue.

Good luck & have fun!

—
ElectionBuddy Engineering Team

