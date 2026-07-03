# Lesson 22 — Hardened: Survive the Storm

Your product works. Your swarm obeys. In calm weather. This lesson drags both into a storm and finds out what survives — because **Viability** is not "it works when I'm careful." It's "it holds when a thousand strangers, one attacker, and one broken deploy all arrive on the same Tuesday."

This is the least glamorous lesson in The Forge and the one that most separates amateurs from Architects. Anyone can build the happy path. You are going to build the thing that stays standing when the happy path is on fire. I will be a demanding mentor here, because "hardened" is not a vibe — it is a checklist you either passed or didn't, and a stranger's data is on the line.

Coach, not author. Say "mentor mode" if I start writing your pipeline for you.

Everything lives in **`my-projects/forge/03-hardened/`**. Make it now. You'll be hardening the product from Lesson 20 (or your swarm from 21 — pick the one with real users at stake).

---

## The mission

> Take a real system to **production-hardened**: an automated test suite that runs in **CI/CD on every push**, a **security pass** it provably survives, and a **load test** that proves it holds under a real crowd — and, when handed a metric you could win by cheating a user, **refuse, and document the refusal.**

Four fronts: tests, pipeline, security, load — plus one ethical trial. Miss any one and it is not hardened; it is lucky. Luck is not a strategy an Architect ships on.

---

## Step 1 — A test suite that means it

You wrote a couple of tests back in Level 2. Now you build a suite that actually guards the system — enough that you'd trust it to tell you "safe to ship" without you re-checking by hand.

In `03-hardened/`, build tests that cover:

- **The core action's happy path** — the thing strangers do most must be proven, every time.
- **The ugly inputs** — empty, huge, wrong-type, malicious, the emoji, the 10,000-character name. Strangers and attackers both live here.
- **The reins (if you're hardening the swarm)** — a test that *proves* the cost cap and the human gate still hold. A rein with no test is a rein you're hoping still works.

Write, in `03-hardened/testing.md`, what you chose to cover and — honestly — what you chose *not* to, and why. Knowing your coverage gaps on purpose is senior. Pretending you have none is junior.

Coach prompt:

```text
Here's my system and my test list: [paste]. As my mentor, find the
untested path most likely to hurt a real user or leak data. Don't write
the test — tell me what to test and why it's the dangerous one.
```

---

## Step 2 — CI/CD: the pipeline that won't let you ship broken

Wire a **continuous integration pipeline** (GitHub Actions is right here, free, and lives with your code) that, on **every push**:

1. Runs your whole test suite.
2. **Fails the build — loudly — if anything is red.**
3. (Bonus, real-world) deploys to production automatically *only when green* (continuous deployment).

The point is not the YAML. The point is a machine that makes "I'll just ship it, the tests probably pass" *impossible*. You are building a system that protects your users from your own future 2-a.m. self. That is Adaptive Orchestration pointed at your own workflow.

Prove it works by **pushing a deliberately broken commit** on a branch and showing the pipeline catch it — screenshot the red X in `03-hardened/cicd.md` — then fix it green. A pipeline you've never seen fail is a pipeline you don't know works.

---

## Step 3 — The security pass (assume someone wants in)

Now you think like the attacker. Real software has real enemies — bots, scrapers, bored teenagers, actual criminals. Walk your system against this checklist and fix every gap, logging each in `03-hardened/security.md`:

| Threat | The question you must answer "yes" to |
| --- | --- |
| **Secrets exposure** | Are all keys/tokens in env/secrets, and is the git *history* clean of them too? (A key committed once and "removed" is still in history — and still leaked.) |
| **Broken authorization** | Can user A reach user B's data by changing an ID in the URL? Prove they can't. |
| **Injection & bad input** | Is every input that touches a database, a shell, a page, or an AI prompt validated and escaped? (SQL injection, XSS, prompt injection — all the same sin: trusting input.) |
| **No rate limiting** | Can one client hammer your API or your AI costs into the ground? Add a limit. |
| **Leaky errors** | Do your error messages spill stack traces, file paths, or internals to strangers? Give humans a clean message, keep the details in your logs. |

> **The bar:** you don't need a bank's security. You need to have *looked*, like an adversary, and closed the doors a bored attacker would try first. "I didn't think anyone would attack it" is exactly what every breached founder said the week before.

Coach prompt:

```text
Be an attacker probing my system: [describe it]. What are the three
things you'd try first to break in, steal data, or run up my costs?
Then, as my mentor again, tell me which to fix first and why.
```

---

## Step 4 — Load: survive the crowd

A system for real strangers must survive *many* strangers at once. You'll prove it can — or find exactly where it breaks, which is just as valuable.

- **Set an honest SLO** (service level objective) *first*, in `03-hardened/load.md`: "the core action stays under [X] seconds for [N] concurrent users." Pick real numbers.
- **Run a load test** — a tool that simulates many users hitting your system at once (there are free ones; learn one). Push until something gives.
- **Find the breaking point and the bottleneck.** Where does it slow, error, or fall over? The database? An unindexed query? An AI call with no timeout? A missing cache?
- **Optimize one real bottleneck** and prove the improvement with before/after numbers. A slow query indexed. A result cached. A call made async. One real fix, measured.

> **Constraint:** the numbers are real or they're nothing. "It felt fast" is banned. You set an SLO, you tested against it, you have the graph. Performance you can't measure is performance you're imagining.

---

## Step 5 — The ethical trial (the metric you must refuse)

Here is the hard-truth moment of The Forge. Somewhere in your system is a change that would **make a number go up by quietly costing a user** — a pre-checked box that opts them into something, a "cancel" buried three taps deep, a confirmshaming button ("No thanks, I hate saving money"), an AI reply engineered to be *slightly* more confident than the truth to boost conversions.

You are going to **find the most tempting one in your own system, and refuse it — in writing.** In `03-hardened/ethics.md`:

- **Name the dark pattern** you could add and roughly how much it would juice your metric.
- **Refuse it,** and write *why* — the real cost to the real human, and the kind of Architect you're choosing to be (oath line 5).
- **Ship the honest version** instead, even if it converts worse.

> This is not a side quest. The most dangerous engineers in the world are the skilled ones with no line they won't cross. The Forge makes you skilled. This step makes sure you're skilled *and* someone the world is safer for. An Architect's power is only trusted because their restraint is real.

---

## Step 6 — Pre-mortem & retro

**Pre-mortem** (in `load.md`): "It's live under real load and it fell over / got breached / cost me a fortune — the cause was..." Three ways, each with a fix you do now.

**Retro** (`03-hardened/retro.md`):

| Heading | What goes there |
| --- | --- |
| Test coverage | What you guard, what you knowingly don't, and why. |
| The pipeline | Proof CI caught a real break (the red X) before it shipped. |
| The doors you closed | The security gaps you found and fixed — especially the scariest. |
| Load & the bottleneck | Your SLO, your breaking point, and the one optimization with before/after numbers. |
| The metric you refused | The dark pattern you could've shipped, and why you didn't. |
| Did the pre-mortem call it? | Which fear reality confirmed. |

---

## Reality check — read this before you judge yourself

Hardening is bottomless — there is always another test, another attack, another optimization. You are not trying to be perfect; you are trying to be *responsible*: to have looked at your system the way a crowd, an attacker, and a load will look at it, and closed the doors that matter. If your load test found an embarrassing bottleneck and your security pass found a door you left wide open — **that's the lesson working exactly as designed.** Better you find them now, small, than a stranger finds them later, painfully.

The bar to pass: **real tests running in CI on every push, a security pass you provably survive, a load test with real numbers and one measured optimization, and a documented refusal of a dark pattern.** The only real failure is shipping to real strangers while pretending the storm won't come.

---

## Stuck?

1. **CI config fighting you?** Everyone's first pipeline is a slog of red builds. That *is* the pipeline working. Read each failure, fix one thing, push again. It's the detective skill from Lesson 13 with a robot partner.
2. **Load test won't break it?** Push harder, or add cost — more users, bigger payloads. Everything has a breaking point; finding yours is the deliverable, not avoiding it.
3. **Whole shape:** real test suite → CI/CD that catches a real break → security pass against the checklist → load test + one measured optimization → a documented ethical refusal → `retro.md`.

---

## 🛡️ Milestone: your system survives attack and load

You took something that worked and made it *survive* — a crowd, an attacker, your own broken commit, and the temptation to cheat a user for a better number. That is the difference between a project and a product people can actually depend on. And you proved you're the kind of Architect whose power comes with a spine: you found the profitable dark pattern in your own work and killed it.

Skilled *and* trustworthy under pressure. That's rare. That's you now.

---

## Prove it

- [ ] A real **test suite** runs in **CI/CD on every push**, and you have proof it caught a deliberately broken commit (the red X).
- [ ] `security.md` shows you walked the whole threat checklist and closed the real gaps, history included.
- [ ] `load.md` has an SLO, a load test to the breaking point, and **one optimization with before/after numbers**.
- [ ] `ethics.md` names a dark pattern you could've shipped, refuses it in writing, and ships the honest version.
- [ ] `retro.md` is filled, including whether the pre-mortem called it.

## Save your work

Commit and push, like `Forge 03: hardened — CI green, doors closed, held under load, dark pattern refused`. Your system is no longer lucky. It's ready.

## What's next

Open **[lessons/23-the-contribution.md](23-the-contribution.md)**. You've built, defended, and hardened your own work. Now you stop being only a builder of your own things and become a **force in something bigger** — you extend MILO itself, and you lead other humans. 🏛️
