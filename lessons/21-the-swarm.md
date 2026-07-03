# Lesson 21 — The Swarm: Orchestration Under Command

Until now, one program did one job. Today you build **many** — a set of AI agents that work together on a real task, coordinated by a supervisor that keeps command even when a part of the swarm fails, lies, or runs wild. This is the beating heart of MILO itself, and it is where two of the three laws collide: **Adaptive Orchestration** (the swarm bends when the world changes) and **Supervisory Primacy** (you never lose the reins).

This is the lesson where power gets genuinely dangerous, so I am going to be a hard mentor about one thing above all others: **a swarm you cannot see, stop, and answer for is not impressive — it is a liability you haven't noticed yet.** Anyone can wire five agents together and let them loose. An Architect builds the swarm *and* the cage, in the same breath. We build both.

I coach, you build. If you ask me to write the whole orchestrator, I'll refuse and hand you the concept and the next question instead. Say "mentor mode" if I forget.

Everything lives in **`my-projects/forge/02-swarm/`**. Make it now.

---

## The mission

> Build a **multi-agent system** — a supervisor plus at least **three specialized agents** — that completes one **real, useful task** end to end. Then *deliberately break one agent* and prove the supervisor keeps command and the system degrades safely instead of collapsing or running away.

The task must be real, not a toy. Some worthy shapes:

- **A research swarm:** a planner, several searchers on different angles, and a synthesizer that writes a cited answer.
- **An inbox/triage swarm:** a classifier, a drafter, and a reviewer that flags anything needing a human.
- **A content swarm:** a strategist, a writer, and an editor that enforces your rules and kills overpromises.
- **A build-helper swarm:** an issue-reader, a fixer, and a test-runner that refuses to "pass" without evidence.

Pick one where you'd actually use the output. Viability watches this lesson too.

---

## Step 1 — Design the org chart (roles before code)

A swarm is an organization. Design it like one, on paper, before a line of code. In `02-swarm/design.md`, define:

- **The supervisor** — the one component that owns the goal, hands out work, judges results, and is the *only* thing that can declare the task done or escalate to you. It thinks; the workers do.
- **Each specialized agent** — its single job, its inputs, its outputs, and the *one thing it is not allowed to decide on its own*.
- **The contract between them** — how work and results pass around (a shared plan, a message format, a queue). Agents that "just talk freely" become a mob. Give them a shape.

> **Constraint — one job per agent.** If an agent does two jobs, split it. Specialization is what makes a swarm adaptable: you can fix, replace, or upgrade one worker without the others noticing. This is Adaptive Orchestration at the design level.

Coach prompt:

```text
Here's my swarm org chart: [paste]. As my mentor, attack the design:
which agent is secretly doing two jobs? Where could two agents deadlock
waiting on each other? Where does the supervisor hand over a decision it
should have kept? One question at a time.
```

---

## Step 2 — Build the workers, then the supervisor

Build each specialized agent first — small, single-purpose, testable alone. Prove each one works by itself before you wire them together. A swarm of unverified agents is just a bigger bug.

Then build the **supervisor**, and give it the three things that make it a supervisor and not just a for-loop:

1. **It assigns and sequences** the work (who does what, in what order, and what can run in parallel).
2. **It judges** each agent's output before using it — is this good enough, empty, or garbage? A supervisor that trusts blindly is a rumor mill.
3. **It owns "done" and "escalate"** — only the supervisor decides the task is complete, and only the supervisor decides when to stop and ask *you*.

Wire the real task end to end. Get it to produce a real, useful result in `02-swarm/runs/` (save real outputs — receipts).

---

## Step 3 — The reins: Supervisory Primacy, built in

Now build the cage, and treat it as the most important code in the lesson. Your swarm must have **all four** reins before you're allowed to call it done:

| Rein | What it means | Why |
| --- | --- | --- |
| **Visibility** | Every agent action is logged where *you* can read it — who did what, when, with what result. | You can't supervise what you can't see. |
| **A stop** | A single switch that halts the whole swarm mid-run, cleanly. | When it goes wrong at 2 a.m., you need one button. |
| **Hard limits** | Caps on cost, tokens, API calls, and loop count — the swarm *cannot* exceed them, even if an agent tries. | A runaway loop that burns money or hammers an API is the classic swarm disaster. |
| **A human gate** | For any consequential action (sending a real email, spending money, deleting data, posting publicly), the supervisor **stops and asks you** — it never acts alone. | Oath line 2. Power without a human in the loop is the one thing an Architect never ships. |

Write, in `02-swarm/reins.md`, where each of the four lives in your code, and how you tested it. "I trust it won't loop" is not a limit. A hard cap in code is.

Coach prompt:

```text
Here's how I built visibility, a stop, hard limits, and a human gate
into my swarm: [paste]. Try to defeat each one: how could an agent burn
past my cost cap, dodge the log, or take a consequential action without
hitting the human gate? Find the gap I can't see.
```

---

## Step 4 — Adaptive Orchestration: break it on purpose

A swarm that only works when every agent behaves is a fair-weather swarm — worthless the first time reality sneezes. So you will make reality sneeze, in a controlled test, and prove your swarm *adapts* instead of shattering.

Run these three **failure-injection tests** and record each in `02-swarm/chaos.md`:

1. **A worker dies.** Make one agent throw an error or time out every run. Does the supervisor notice, retry or reroute or degrade gracefully — and still finish with a smaller honest result, or escalate to you? Or does the whole thing hang and die?
2. **A worker lies.** Make one agent return garbage or an empty result. Does the supervisor *catch* it (Step 2's judging) or blindly pass poison downstream?
3. **A worker runs wild.** Force a loop or a runaway. Do your hard limits (Step 3) actually stop it, in code, without you intervening?

> **The bar:** for all three, the swarm must **stay under your command and fail safe** — degrade, retry, or escalate — never collapse silently and never run away. If any test takes control away from you, you have not built a swarm; you've built a hazard. Fix it before moving on. This *is* Adaptive Orchestration under Supervisory Primacy, proven.

---

## Step 5 — Pre-mortem

Add a `## Pre-mortem` to `02-swarm/design.md`. Finish three ways, each with the fix you'll do now:

> "The swarm did real damage or ran away, and the most likely cause was..."

Steal from the real ones: an unbounded loop with no cap, an agent given a consequential power without a human gate, the supervisor trusting a lying worker, or no way to see what happened after it went wrong.

---

## Step 6 — Retro

Create `02-swarm/retro.md`:

| Heading | What goes there |
| --- | --- |
| The real task | What the swarm actually did, with a saved real output. |
| The org chart that worked | Final roles, and one you had to redesign and why. |
| The reins | Where visibility, stop, limits, and the human gate live — and how you tested them. |
| Chaos results | What happened when a worker died, lied, and ran wild — and whether you stayed in command. |
| The scariest moment | The one time it nearly got away from you, and what caught it. |
| Did the pre-mortem call it? | Which Step 5 fear reality confirmed. |

---

## Reality check — read this before you judge yourself

Multi-agent systems are genuinely hard — teams of professionals ship swarms that loop, deadlock, or quietly burn money. If your first swarm needed three redesigns and your chaos tests exposed a runaway you didn't know you had, that is not failure — **that is the exact lesson**, learned small and safe instead of expensive and public. Catching your own swarm trying to escape *is the win*.

The bar to pass: **a supervisor plus three real agents that complete a real task, with all four reins built and tested, that stays under your command through all three chaos tests.** The only real failure is a swarm that can take a consequential action, or run away, without a human able to see and stop it — because that's the one an Architect must never build.

---

## Stuck?

1. **Agents talking in circles?** Your contract (Step 1) is too loose. Give them a strict shape — a shared plan the supervisor owns, not free chatter.
2. **Chaos test hangs forever?** You found a missing rein. That's the *point* of the test. Add the timeout/cap in code, not in hope.
3. **Whole shape:** `design.md` (org chart + pre-mortem) → build + verify each worker → supervisor that assigns, judges, and owns done/escalate → all four reins in `reins.md` → three chaos tests in `chaos.md` → `retro.md`.

---

## 🕸️ Milestone: you command a swarm

You built a team of AI agents that does real work — and, harder and rarer, you built the reins that keep it yours. You made it fail on purpose and proved it fails *safely*, under your hand. That combination — real orchestration *plus* real control — is the exact thing MILO is built on, and most people who wire agents together never even realize the cage is the hard part. You did. You built it first.

You don't just use AI now. You *command* it, safely, at scale.

---

## Prove it

- [ ] `02-swarm/design.md` has a supervisor + **3 specialized agents**, one job each, with a defined contract, plus a pre-mortem.
- [ ] The swarm completes a **real, useful task** end to end, with a saved output in `runs/`.
- [ ] `reins.md` shows **visibility, a stop, hard limits, and a human gate** — where each lives in code and how you tested it.
- [ ] `chaos.md` proves the swarm **stays under command and fails safe** when a worker dies, lies, and runs wild.
- [ ] `retro.md` is filled, including the scariest moment and whether the pre-mortem called it.
- [ ] **Ledger:** the public repo link, a saved real run, and the chaos-test evidence are logged in `forge/PROOF.md`.
- [ ] **Built live under watch:** at least one core seam — the supervisor's kill/cost-cap rein — was written *live* in a session MILO or Tío watched, with them able to interrupt "why this line?" mid-build. Finished work no one saw you build triggers the cold-repo rebuild.
- [ ] **Live gate (with Tío):** rehearse with MILO first (*"try to make my swarm run away or dodge the human gate"*). Then on the call Tío injects an unpredictable change — *"now make the supervisor kill any agent that exceeds the cost cap, and show me the reins still hold"* — and you run it in-session and paste real output/errors from **your own** system, keyed to a value he picks live. Reacting correctly to a change a relay never saw is the thing an outside AI can't pre-bake.

## Save your work

Commit and push, like `Forge 02: swarm online — 3 agents, 4 reins, survived chaos under command`. You built power and its leash in one motion. That is the whole art.

## What's next

Open **[lessons/22-hardened.md](22-hardened.md)**. Your product works and your swarm obeys — in calm weather. Next you drag it into a storm: security, automated pipelines, and a crowd big enough to break it. Time to make it *survive*. 🛡️
