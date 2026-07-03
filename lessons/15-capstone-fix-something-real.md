# Lesson 15 — Capstone: Fix Something Real

This is the capstone of the Builder's Track, and it is different from every lesson before it.

The repo ships two **example** feedback notes about GetAdvice — MILO's friendly face — in `feedback-getadvice/notes/`:

- `2026-07-01-app-froze.md`
- `2026-07-01-incorrect-info.md`

They're worked examples of the kind of real complaint you learned to write in [lessons/07-giving-good-feedback.md](07-giving-good-feedback.md). Today you turn **one of them** into a **contribution — in your own file —** following the exact pattern real software teams use:

| Step | Real-team name | What it means |
| --- | --- | --- |
| 1 | Repro | Exact steps anyone can follow to see the problem |
| 2 | Hypothesis | Your best guess at the root cause, in plain English |
| 3 | Spec | One page: what should change, and how we would verify it |
| 4 | Prototype | A small working demo of the FIXED behavior |
| 5 | Review | You show your work and someone looks at it |

Feedback → repro → hypothesis → spec → prototype → review. That is not a school exercise. That is the job.

---

## Step 0 — Pick your one, and make it yours

Open both example notes and pick ONE topic to carry all the way through — the one that bothers you more (caring about the problem is fuel). Do not do both; depth beats coverage.

Now make it yours: **create a new note for your work** — something like `feedback-getadvice/notes/my-fix.md` — and do every step below in *that* file. The two shipped notes are references to study, not files to edit. Everything you turn in should be work you wrote.

---

## Step 1 — Write a clean repro

A repro is a recipe for the bug. If a stranger follows your steps and sees the same problem, your repro is good. This is the detective skill from [lessons/13-the-detective-lessons.md](13-the-detective-lessons.md), pointed at a real app.

**Your goal:** add a `## Repro` section to *your own* note with:

- Numbered, exact steps ("Open GetAdvice. Tap the mic button. Ask: ...")
- **Expected:** what should have happened, one sentence
- **Actual:** what really happened, one sentence

**Constraint:** no vague words. "It broke" is banned. If you did not re-test it today, re-test it today.

---

## Step 2 — Form a root-cause hypothesis

You cannot see GetAdvice's code. That is fine — real engineers hypothesize before they look. Write 3–5 plain-English sentences starting with: "I think this happens because..."

Some thinking fuel, depending on which note you picked:

- **Incorrect info:** where would an AI app even get knowledge about *itself* — its model, its latest update? Is that written down somewhere it can read, or is the AI just... guessing from patterns? What does an AI do when it does not actually know?
- **App froze:** what was the app *waiting for* when it froze? What should an app show the user while it waits, so the house's wiring never traps you inside a room?

Ask MILO to coach — not solve:

```text
I'm forming a root-cause hypothesis for a bug I found in a real app.
Don't tell me the answer — ask me questions, one at a time, until my
hypothesis is specific and testable. Then critique what I wrote.
```

---

## Step 3 — Write a one-page fix spec

A spec is a promise written before the work: *what* should change, and *how we will know it worked*. Add a `## Fix spec` section to your note (or a separate `my-fix-spec.md` you create) with exactly four headings:

| Heading | What goes there |
| --- | --- |
| Problem | Two sentences, lifted from your repro |
| Proposed change | What the app should do instead — behavior, not code |
| How we verify | The repro steps re-run, with the NEW expected result |
| Out of scope | What you are deliberately NOT fixing |

**Constraint:** one page. If it does not fit, your fix is too big — shrink it.

---

## Step 4 — Build a prototype of the FIX

Now prove your idea works — with structure, paint, and wiring you already own. Build a small page in `my-projects/fix-prototype/` that **demonstrates the fixed behavior**, not the bug:

- **Incorrect info:** a mock chat screen where the answers to "what model are you?" and "when was your last update?" come from ONE source of truth in your code (think: your quiz app's `questions` array from [lessons/10-logic-that-thinks.md](10-logic-that-thinks.md)) — and where a question with no known answer says "I don't know" instead of guessing.
- **App froze:** a mock screen with a fake 3-second "thinking" delay — ask MILO to introduce you to `setTimeout`, a cousin of the waiting you did with `await` in [lessons/12-talking-to-the-internet.md](12-talking-to-the-internet.md) (concept first; you write the code) — that shows a loading state the whole time, and the input never locks up.

**Constraints:** plain HTML, CSS, and JavaScript. One folder, no libraries. It only has to prove the *behavior* — ugly is allowed, wrong is not. Use coach mode when stuck; MILO reviews your code, MILO does not write it.

---

## Step 5 — Ship it for review

Commit, push, then signal it's ready — email a 5-line summary to **milo@jmautomated.com** (or, if email isn't set up, commit a `SHIPPED.md` with the same five lines):

1. Which feedback note you chose
2. Your hypothesis, in one sentence
3. What your spec proposes
4. A link to your pushed prototype folder
5. One thing you would do next with more time

Five lines. Real reviewers are busy; clarity is a courtesy.

---

## Stuck?

1. Re-read your original feedback note out loud. The four questions from lesson 07 already contain most of your repro — you are upgrading it, not starting over.
2. For the prototype, forget GetAdvice's real code. Ask: "what is the smallest page that shows the CORRECT behavior?" One button or one input, one visible result, is enough.
3. For incorrect-info: put the true facts in a little data object at the top of your script, answer only from it, and return "I don't know" for anything else. For app-froze: use a timer to fake the wait, flip a "loading" message on before it and off after, and never disable the input.

---

## 🎉 Milestone: you shipped your first real contribution

You took a complaint and turned it into a repro, a hypothesis, a spec, a working prototype, and a review request. That loop — not any single language — is what software work actually is.

You are no longer just learning to code. You are contributing.

---

## Prove it

- [ ] Your own note has a `## Repro` section with numbered steps, Expected, and Actual — and you re-tested it today
- [ ] Your hypothesis is written down and starts with "I think this happens because..."
- [ ] Your note (or a `my-fix-spec.md` you wrote) has a `## Fix spec` that fits on one page with all four headings
- [ ] Your prototype in `my-projects/fix-prototype/` runs in a browser and shows the FIXED behavior
- [ ] Your commit is pushed, and you signaled it's ready for review — email a 5-line summary to milo@jmautomated.com, **or** commit a `SHIPPED.md` with the same five lines so your instructor sees it in the repo

## Save your work

Commit everything with a message that states the contribution, like `capstone: repro + spec + prototype for GetAdvice incorrect-info bug`, and push.

## What happens after this

You finished the Builder's Track. You can build, and you can fix real things. But building is only half the game — the other half is getting real people to *care* about what you built.

That is **Level 3: The Launch Track**, and it starts now: **[lessons/16-level-3-the-launch-track.md](16-level-3-the-launch-track.md)**. It is the hardest thing yet — you'll put a real page live on the internet, run a real campaign, and measure whether real humans showed up. Read [roadmap.md](../roadmap.md)'s **Stage 4** (the map for this Level 3), then open Lesson 16 when you're ready to be heard.
