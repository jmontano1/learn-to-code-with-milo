# PROCTOR.md — the mentor's script (this one's for Tío, not the learner)

Read this once. It is the most important page in Level 4, and it is written for **you, the mentor** — not the learner. Everything else in The Forge is scaffolding. *This* is the gate.

## The one honest truth

The learner runs this course inside an AI he controls. He can open a second AI you can't see and paste any lesson into it. So **no file, no checklist, no "MILO viva," and no green badge can actually stop him** — MILO is his AI too, and a check MILO renders is a check he can relay around. There is exactly one thing an outside AI cannot take for him: **sitting with you, live, and changing his own running code while you watch and he explains.** You are the gate. This page makes running that gate easy, and takes away your ability to go soft on him — which, with a nephew, is the real hole.

This is not distrust. It's the same reason a black belt is tested in the room, not by mailing in a video. If it's really his, this is *easy and it feels great.* If it isn't, you both find out in ten minutes, kindly.

## Setup (every gate call, no exceptions)

- **Video call, camera on.** You see his face and both hands.
- **Full-desktop screen share** — the *whole* screen, not one window. An unshared AI window then shows up as a gap he can't explain.
- **Phone face-down on the desk, in frame.** No earbuds; both ears visible.
- **No second screen, no second device.** Editor and browser only.

Relaying to a hidden AI produces the two things you can see over video: **latency** (pauses before every answer) and **eyes going off-screen**. Watch his face and hands, not just the code.

## The 3-move checklist (run it in order, every time)

**Move 1 — Live-modify (the load-bearing move).** Invent a *small change on the spot* to his actual running system — something that touches 2–3 places and can't be a memorized flashcard:
- "Add a field to this form and make it show up after signup."
- "Make this endpoint reject an empty name — prove it with a real request right now."
- "Make it flash red when the score hits 10, and *only* then."

**Before his hands touch the keyboard, he must say out loud:** which files will change, and what he expects to see. *Then* he makes it work while narrating, in about ten minutes. A relay can dictate keystrokes; it cannot produce the reasoning *first* and then have the keystrokes match it.

**Move 2 — "Show me the commit where X broke, and read me the message."** He scrolls his real history live and reads it to you. A finished repo that was pasted in has no story in its history.

**Move 3 — "Why did you build it this way and *not* the other option?"** The real builder has an opinion and a reason. A parrot has a summary.

## The hard rule (this is the actual fix — it binds *you*)

> A warm, **fumbling pass** on the live-modify is exactly what a real beginner looks like. **Celebrate it.** He's allowed to be slow, to Google, to say "I think it's in this file… no, this one." That's real.
>
> But a **can't-*start*** — he freezes, his eyes flick to a second screen, there's a suspicious pause before every word, or he can't even say which file to open — is an **automatic send-back. No exceptions. No "he was just nervous." No "he's family."**

Your kindness is the one thing that defeats every safeguard in this repo. This rule exists to take that discretion out of your hands. Sending him back is not a punishment — it's you refusing to let him arrive at the top standing on a foundation he didn't pour, where the fall is real.

## Recording a pass MILO can't forge

MILO is **not allowed** to open the two hard gates (Lesson 19 entry, and the Lesson 24 capstone) — because a gate MILO can open, the outside AI can open too. Only you can pass him, and you do it in a way his AI can't fake:

- **Strong form:** commit one line to `my-projects/forge/PROOF.md` **from your own GitHub account** (login `jmontano1`) — e.g. `PASS: Lesson 19 gate — [date] — Tío`. His AI cannot commit as you. MILO is told to check for *your* committer login and refuse to advance without it.
- **Lighter form:** say a short passphrase on the call that he pastes into MILO.

If the call doesn't happen, the gate stays shut. That's the point: "he forgot to call his uncle" becomes a wall, not a silent skip.

## When to run it

- **Lesson 19 → 20 (entry gate):** mandatory. First viva is on his *Level 3* work — if a level "felt easy," that's the sound of work he didn't do; send him back to do it for real. This is the gate that catches exactly how he cheated.
- **After every Forge lesson (the ~15-min "Show me" call):** the real milestone. See [SHOW-ME.md](SHOW-ME.md). MILO's 🎉 emoji is a string it can print itself; *your grin* is the reward it can't.
- **Lesson 24 (the capstone):** mandatory, the full defense — plus you personally sampling his "real users/payments" (pick 2 at random, reach them yourself, ask "how did you find this, and did anyone ask or pay you to try it?").

## Deadline-card template (paste per lesson)

```text
SHOW-ME CALL — Lesson ___  ·  [date/time]
Setup: video on · full-desktop share · phone face-down · no earbuds · editor+browser only
1) Live-modify: "____________________" (predict files+result out loud FIRST, then do it)
2) "Show me the commit where ____ broke and read me the message."
3) "Why did you build ____ this way and not ____?"
Rule: fumbling pass = celebrate.  can't-START = automatic send-back.  No exceptions.
Pass recorded by: commit to PROOF.md as jmontano1  /  passphrase on call
```

## Keep it love, not a trial

He cheated out of overwhelm, not malice. So open every call by making honest AI use *welcome*: "Leaning on AI to *learn* — to explain things, to help you write code you understand — is exactly right; that's the whole point." Name a suspected did-for-me without accusation, and route it to a warm live rebuild, never a punishment. The whole design only works if he feels safe enough to stay on the honest side. You're not catching a cheater. You're making sure your nephew actually gets the thing you're giving him.
