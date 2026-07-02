# Lesson 23 — Capstone: Launch GetAdvice 📣

You've spent the Launch Track building parts: you know who GetAdvice is for, what it sounds like, where it should show up, and how to tell whether anything is working. But parts don't launch apps — plans do. This week you assemble everything into one launch plan, defend it line by line, run a real launch week, and write the retro that flows straight back into the product.

## What you'll learn

- How to compress weeks of research into a one-page plan someone could act on tomorrow
- How to defend every line of a plan — and change the lines that don't survive
- How to run a self-directed launch week where your journal *is* the status report
- How to write a retro a product team can actually use

## Why this matters

GetAdvice is a real iOS app from JM Automated Solutions ([getadviceapp.com](https://getadviceapp.com)), built for people who feel intimidated by AI and want a friendly way in. You've been its feedback tester since day one, and through this track you became its junior growth teammate. This is not a simulation: the plan you write is a real plan, the week you run is a real week, and the last section of your retro — *what GetAdvice should change* — feeds the product feedback loop automatically.

Back in [lesson 15](15-capstone-fix-something-real.md) you learned the contribution loop: feedback → repro → spec → prototype → review. Marketing has its own loop, and this capstone walks the whole thing: **plan → defend → execute → measure → retro.**

---

## Step 1 — [You do] Assemble the plan

Create `marketing/launch/launch-plan.md` with exactly six headings. Every one of them pulls from work you already shipped — this step is assembly, not new research:

| Heading | Pull from | The one-line test |
| --- | --- | --- |
| Audience | `marketing/research/audience.md` | Could a stranger picture this exact person? |
| Message | `marketing/voice/voice-guide.md` + `marketing/voice/app-store-copy.md` | Would that person stop scrolling for it? |
| Channels | `marketing/content/calendar.md` + `marketing/content/posts/` | Can *you* actually publish there this week? |
| Calendar | your content calendar, tightened to 7 days | Every day names one concrete deliverable |
| Metric | `marketing/measure/experiment-log.md` + `marketing/aso/keywords.md` | ONE number you can count yourself |
| Risks | your own head | Three things that could go wrong, each with a "then I will..." |

Three rules:

1. **One page.** If it doesn't fit, your launch is too big — shrink it. (Same rule as your fix spec in lesson 15. It wasn't a coincidence then either.)
2. **Every line traces to a file.** If you can't point at where a claim came from, it's a guess wearing a suit.
3. **Write it yourself.** Assembly is thinking — choosing what makes the page and what doesn't *is* the strategy. MILO gets its turn in Step 2.

A warning about the Metric: pick one number you can count with your own eyes. Posts actually published. Replies you received. People you personally showed the app who then tried it. A metric you can't observe yourself isn't a metric — it's a wish.

## Step 2 — [Ask MILO] Defend it line by line

For this whole course, *always ask why* was your job. Today the roles flip.

```text
Here is my launch plan for GetAdvice (pasted below). Act as a
skeptical marketing lead. Go through it line by line and ask me
"why?" about every single choice — the audience, the message, each
channel, each calendar day, the metric, each risk. One question at
a time. Don't suggest fixes until I've answered. If my answer is
weak, say so plainly, and ask why again.
```

Think of it like a thesis defense, except the thesis is one page and the stakes are a real launch. The rule for your answers: every "because" must point at evidence — a file in `marketing/`, a competitor you studied, a thing a real person said to you. "It felt right" loses the exchange.

If MILO drifts into rewriting your plan instead of questioning it, you know what to say by now: coach mode, remember?

## Step 3 — [You do] Revise and commit

Change every line that didn't survive. Then add one final section to the plan, `## Changed after review`, listing two or three lines that changed and *why* the original didn't hold up.

If nothing changed, you defended too gently — go back to Step 2 and tell MILO to be harsher. A plan that survives review untouched wasn't really reviewed. Finding the weak lines now, on paper, is the cheapest they will ever be to fix — mistakes are part of the process, and this step exists to surface them before the week does.

Commit it:

```bash
git add marketing/launch/launch-plan.md
git commit -m "launch: capstone launch plan, defended and revised"
```

## Step 4 — [You do, every day] Run the launch week

Now execute the calendar. Day by day, deliverable by deliverable.

Start a fresh journal file for the week: copy `templates/journal-template.md` to the next `marketing/journal/week-NN.md` and fill in the front-matter. It must start with this exact block — keep the keys exactly as written:

```text
---
week: N
focus: <one line>
shipped: <comma-separated deliverables>
learned: <one line>
blocked: <one line or "nothing">
feedback-for-getadvice: <one line or "none">
---
```

This matters more than it looks: **MILO reads these files automatically. The front-matter IS your report.** Nobody will chase you for status — on a real team, the person who writes things down where the team can find them is the person who gets trusted with more. Below the front-matter, add a short note under a `### Day N` heading for each day: what you shipped, what happened, what you'll do differently tomorrow. When something flops, write it down with extra care. Flops are data, and your retro will be starving for them.

One more habit: every time you deliberately *change* something mid-week — a post's wording, a channel, a time of day — that's an experiment. Log it the way lesson 22 taught you: one new row in the table in `marketing/measure/experiment-log.md` — hypothesis and change before, result and decision after. Commit your journal and log at the end of each day; small daily commits are the habit that got you here.

## Step 5 — [Ask MILO] Mid-week checkpoint

Around day 3 or 4, stop and look up:

```text
It's the middle of my GetAdvice launch week. Here is my launch plan
and my journal so far (pasted below). Compare what actually happened
against the plan and my metric. Ask me why about anything I changed
or skipped. Then, for each remaining day, help me decide: hold the
plan, or adjust it — and make me justify the choice either way.
```

Adjusting mid-week is not failure. Riding the original plan straight through evidence that it isn't working — *that's* failure. The plan was your best guess before contact with reality; reality gets a vote.

## Step 6 — [You do] Write the retro

The week is done. Create `marketing/launch/retro.md` with exactly four headings:

- **What worked**
- **What did not**
- **What surprised you**
- **What GetAdvice should change**

Rules:

1. Every claim points at evidence from your journal or your experiment log. No vibes.
2. "What did not" must have *at least as many entries* as "What worked." An honest retro beats a flattering one every single time, and a retro with no failures in it is fiction.
3. The last section is the payoff. Write it to the product team, concretely: not "make onboarding better," but "the person in my audience file gets stuck at X — here is what I watched happen." This file feeds the product feedback loop automatically. It is the single most valuable thing you ship this week.

## Step 7 — [Ask MILO] Audit the retro

```text
Here is my launch retro for GetAdvice, plus my journal entries and
experiment log (pasted below). Don't rewrite anything. Audit it:
is every claim backed by something I actually recorded during the
week? Flag anything vague, anything asserted without evidence, and
anything in "What GetAdvice should change" that isn't concrete
enough for a product team to act on.
```

Fix what gets flagged — in your own words, from your own notes. The evidence rule from Step 2 applies to you both ways: you demanded it from the plan, the retro demands it from you.

---

## Ship it 🚀

Final pass, then commit and push:

- [ ] `marketing/launch/launch-plan.md` — six headings plus `## Changed after review`
- [ ] `marketing/journal/` — your launch-week file plus your earlier weeks, every one starting with the exact front-matter block
- [ ] `marketing/measure/experiment-log.md` — at least one complete experiment: hypothesis, result, decision
- [ ] `marketing/launch/retro.md` — four headings, "what did not" fully loaded, last section concrete

```bash
git add marketing/
git commit -m "launch: capstone complete — plan, launch week, retro"
git push
```

That push is the finish line. MILO reads what you shipped — the files are the report, and the report is done.

## 🌟 Milestone

The rubric looks for **`marketing/launch/launch-plan.md`**, **`marketing/launch/retro.md`**, and **at least two `marketing/journal/week-NN.md` files** that start with the exact front-matter block.

---

## After the launch

Level 1 taught you to follow the map. Level 2 taught you to draw it. Level 3 made you walk the territory — with a real product, a real audience, and a plan you had to defend out loud.

You are not a student who finished a marketing course. You are a contributor with a shipped launch, a written retro, and a feedback line straight into a real product. The loop you just ran — plan, defend, execute, measure, retro — doesn't retire when the lesson ends. Keep the weekly journal going. Keep logging experiments. Keep asking why, especially of yourself.

The launch was the capstone. The habit is the career.
