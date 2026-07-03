# PROCTOR.md — the instructor's script (for the reviewer, not the learner)

Read this once. It is the most important page in Level 4, and it is written for **the instructor** — the person who reviews and passes the learner — not for the learner. Everything else in The Forge is scaffolding. *This* is the gate.

## The one honest truth

The learner runs this course inside an AI they control. They can open a second AI you can't see and paste any lesson into it. So **no file, no checklist, no "MILO viva," and no green badge can actually stop them** — MILO is their AI too, and a check MILO renders is a check they can relay around. There is exactly one thing an outside AI cannot take for them: **sitting with you, live, and changing their own running code while you watch and they explain.** You are the gate. This page makes running that gate easy, and takes away your ability to go soft — which, with anyone you have a working relationship with, is the real hole.

This is not distrust. It's the same reason a black belt is tested in the room, not by mailing in a video. If the work is genuinely theirs, this is *easy and it feels great.* If it isn't, you both find out in ten minutes, professionally and without drama.

## Setup (every gate call, no exceptions)

- **Video call, camera on.** You see their face and both hands.
- **Full-desktop screen share** — the *whole* screen, not one window. An unshared AI window then shows up as a gap they can't explain.
- **Phone face-down on the desk, in frame.** No earbuds; both ears visible.
- **No second screen, no second device.** Editor and browser only.

Relaying to a hidden AI produces the two things you can see over video: **latency** (pauses before every answer) and **eyes going off-screen**. Watch their face and hands, not just the code.

## The 3-move checklist (run it in order, every time)

**Move 1 — Live-modify (the load-bearing move).** Invent a *small change on the spot* to their actual running system — something that touches 2–3 places and can't be a memorized flashcard:
- "Add a field to this form and make it show up after signup."
- "Make this endpoint reject an empty name — prove it with a real request right now."
- "Make it flash red when the score hits 10, and *only* then."

**Before their hands touch the keyboard, they must say out loud:** which files will change, and what they expect to see. *Then* they make it work while narrating, in about ten minutes. A relay can dictate keystrokes; it cannot produce the reasoning *first* and then have the keystrokes match it.

**Move 2 — "Show me the commit where X broke, and read me the message."** They scroll their real history live and read it to you. A finished repo that was pasted in has no story in its history.

**Move 3 — "Why did you build it this way and *not* the other option?"** The real builder has an opinion and a reason. A parrot has a summary.

## The hard rule (this is the actual fix — it binds *you*)

> A warm, **fumbling pass** on the live-modify is exactly what a real beginner looks like. **Celebrate it.** They're allowed to be slow, to search, to say "I think it's in this file… no, this one." That's real.
>
> But a **can't-*start*** — they freeze, their eyes flick to a second screen, there's a suspicious pause before every word, or they can't even say which file to open — is an **automatic send-back. No exceptions. No "they were just nervous." No going easy because you know them.**

Your leniency is the one thing that defeats every safeguard in this repo. This rule exists to take that discretion out of your hands. Sending the learner back is not a punishment — it's you refusing to let them arrive at the top standing on a foundation they didn't pour, where the fall is real.

## Recording the pass

The pass is *earned in the call above* — that is the gate. MILO is not allowed to open the two hard gates (Lesson 19 entry, the Lesson 24 capstone) on its own, because a gate MILO can open, the outside AI can open too. Once the learner has genuinely passed the live call, you record it so MILO knows to advance:

- **Best:** push one line to `my-projects/forge/PROOF.md` **from your own GitHub account** and to the **remote** — e.g. `PASS: Lesson 19 gate — [date] — instructor`. MILO can sanity-check with `gh api` that the *remote* commit shows your login. (Be aware: a *local* commit's author is forgeable — anyone with push access can set `git config` to your name — so it's the pushed remote record, tied to the live call, that carries the weight, not a local file.)
- **Fine for the per-lesson Show-me calls:** just say a short passphrase on the call. It's honor-based, so don't lean on it for the two hard gates — use the pushed record there.

If the call doesn't happen, the gate stays shut. That's the point: "the review got skipped" becomes a wall, not a silent bypass. And remember what actually holds — not the file, but the ten minutes where you watched them build.

## When to run it

- **Lesson 19 → 20 (entry gate):** mandatory. First review is on their *Level 3* work — if a level "felt easy," that's the sound of work they didn't do; send them back to do it for real. This is the gate that catches the paste-it-all shortcut.
- **After every Forge lesson (the ~15-min "Show me" call):** the real milestone. See [SHOW-ME.md](SHOW-ME.md). MILO's 🎉 emoji is a string it can print itself; a live pass from you is what it can't.
- **Lesson 24 (the capstone):** mandatory, the full defense — plus you personally sampling their "real users/payments" (pick 2 at random, reach them yourself, ask "how did you find this, and did anyone ask or pay you to try it?").

## Deadline-card template (paste per lesson)

```text
SHOW-ME CALL — Lesson ___  ·  [date/time]
Setup: video on · full-desktop share · phone face-down · no earbuds · editor+browser only
1) Live-modify: "____________________" (predict files+result out loud FIRST, then do it)
2) "Show me the commit where ____ broke and read me the message."
3) "Why did you build ____ this way and not ____?"
Rule: fumbling pass = celebrate.  can't-START = automatic send-back.  No exceptions.
Pass recorded by: commit to PROOF.md from the instructor account  /  passphrase on call
```

## Keep it professional, not a trial

Most learners who cut corners do it out of overwhelm, not malice. So open every call by making honest AI use *welcome*: "Leaning on AI to *learn* — to explain things, to help you write code you understand — is exactly right; that's the whole point." Name a suspected did-for-me without accusation, and route it to a live rebuild, never a punishment. The whole design only works if the learner feels safe enough to stay on the honest side. You're not catching a cheater. You're making sure the learner actually gets the skill the course exists to give them.
