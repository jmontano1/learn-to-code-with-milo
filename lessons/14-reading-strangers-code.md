# Lesson 14 — Reading Strangers' Code

Until now, every house you walked into was one you built. You knew where every wire ran because you ran it. Today you walk into a house wired by a stranger — and your job is to figure out where the electricity goes **without flipping every switch to see what turns on**.

This is the Stage 3 superpower from your [roadmap](../roadmap.md): open a file you did not write and explain what it does. Every real codebase you will ever touch — including GetAdvice — is mostly code somebody else wrote. Builders who can only read their own code stay small. You are not staying small.

Three missions today:

| Mission | What you do | What it trains |
| --- | --- | --- |
| 1. Read it cold | Explain the file below **without running it** | Reading wiring by eye |
| 2. Predict the break | Say what fails if one line is deleted | Reasoning, not guessing |
| 3. Wire it in | Add it to Study Buddy as a streak feature | Using strangers' code |

---

## The file: `streak.js`

Someone on the Study Buddy "team" (okay, it was MILO) wrote this streak counter. It tracks how many days in a row you have studied. Save it as `streak.js` next to your Study Buddy files from [lessons/12-talking-to-the-internet.md](12-talking-to-the-internet.md) — but **do not run it yet**.

```js
// streak.js — tracks how many days in a row you've studied.

const STREAK_KEY = "studyBuddyStreak";

// Reads the saved streak from localStorage.
function loadStreak() {
  const raw = localStorage.getItem(STREAK_KEY);
  if (!raw) return { count: 0, lastDay: null }; // nothing saved yet
  return JSON.parse(raw);
}

// Turns "right now" into a simple day stamp like "2026-07-01".
function todayStamp() {
  return new Date().toISOString().slice(0, 10);
}

// Call this once each time the user finishes a quiz.
// Returns the current streak count.
function recordStudySession() {
  const streak = loadStreak();
  const today = todayStamp();

  if (streak.lastDay === today) return streak.count;

  const oneDayMs = 24 * 60 * 60 * 1000;
  const yesterday = new Date(Date.now() - oneDayMs)
    .toISOString()
    .slice(0, 10);

  if (streak.lastDay === yesterday) {
    streak.count = streak.count + 1; // kept the chain going
  } else {
    streak.count = 1; // first day ever, or the chain broke
  }

  streak.lastDay = today;
  localStorage.setItem(STREAK_KEY, JSON.stringify(streak));
  return streak.count;
}
```

You already know every tool in this file. `localStorage` is your lesson-11 filing cabinet. `JSON.parse` and `JSON.stringify` came with it. Functions and `if` are old friends. What is new is only this: **you didn't write it.**

One quirk you may notice if you test in the evening: `todayStamp` uses universal time (UTC), so its "day" flips at UTC midnight, not your midnight. That is a real teammate-code quirk — spotting one is exactly the skill this lesson trains.

---

## Mission 1 — Read it cold

Open `streak.js` and a blank file called `my-explanation.md`. No running, no pasting it to MILO, no browser. Just your eyes and the code.

In `my-explanation.md`, write in plain English:

- One or two sentences per function: what it takes in, what it gives back, and when Study Buddy should call it.
- One sentence answering: **why does `loadStreak` have that `if (!raw)` line?** What situation is it protecting against?

A tip from every senior developer ever: when a line confuses you, "play computer." Grab paper, pick pretend values, and walk the code line by line, writing down what each variable holds. Slow is fine. Slow is the method.

---

## Mission 2 — Predict the break

Look at this line inside `recordStudySession`:

```js
if (streak.lastDay === today) return streak.count;
```

Someone chose to put that there on purpose. Your challenge, still without running anything:

1. Describe a real situation where a user makes that line matter. (Think about how many quizzes someone might finish in one day.)
2. Predict **exactly** what goes wrong if that line is deleted. Not "it breaks" — say what number the user sees and why. Play computer if you need to.

Write both answers into `my-explanation.md`. Only after you have committed to a prediction in writing may you test it in the browser console. A prediction you write down before checking is worth ten guesses checked first — that is the difference between reading code and skimming it.

---

## Mission 3 — Wire it into Study Buddy

Now make it real. **The goal:** when someone finishes a quiz in Study Buddy, the app records the study session and shows their streak — something like `🔥 3-day streak` — on the results screen. Reloading the page must not lose it.

**The constraints:**

- Do not change anything inside `streak.js`. Treat it like a teammate's file: you call it, you don't rewrite it.
- You decide where to load the script, where to call `recordStudySession()`, and where the streak appears on the page. That is structure (HTML), a touch of paint (CSS if you want), and wiring (JS) — all yours to figure out.
- Keep it to one call to `recordStudySession()` per finished quiz.

You have done every ingredient before: adding a `<script>`, calling a function at the right moment, putting text into an element. The new skill is composing them around code you only just met.

---

## Coach mode

Do not ask MILO to explain the file — that would do Mission 1 for you. Instead, make MILO the examiner. Paste this:

```text
I just read streak.js in my Study Buddy project and wrote my own
explanation of it. Don't explain the file to me. Quiz me instead:
ask me one question at a time about what each function does, what
the guard clauses protect against, and what breaks if the
"lastDay === today" line is removed. If I get something wrong,
don't give me the answer — ask a smaller question that leads me
to it. At the end, tell me which parts I understood well and
which I should reread.
```

If MILO's quiz exposes a gap, go back to the file, patch your understanding, and update `my-explanation.md`. That loop — read, get quizzed, reread — is exactly how professionals learn a new codebase.

---

## Stuck?

**Hint 1:** There are two early `return` lines in this file (developers call them guard clauses — a bouncer at the door who turns some situations away before the main logic runs). For each one, ask: "what situation gets turned away here?"

**Hint 2:** For Mission 2, play computer twice with the guard line deleted: a user finishes quiz #1 in the morning, then quiz #2 that same afternoon. On the second run, what is `streak.lastDay`? What is `today`? Are they equal to each other — and is `lastDay` equal to `yesterday`?

**Hint 3:** Without the guard, that second same-day run falls through to the `if/else`. `lastDay` is today, not yesterday, so the `else` branch runs. Look at what the `else` branch assigns to `count`, and imagine you were on a 12-day streak.

---

## 🎉 Milestone: you made a stranger's code work for you

You read a file you didn't write, predicted how it would break, and wired it into your own app without changing a byte of it. That is how professionals join a codebase.

---

## Prove it

- [ ] `my-explanation.md` exists, with a plain-English description of all three functions written **before** you ran anything.
- [ ] It contains your written prediction of what breaks without the guard line — plus one line saying whether the browser proved you right.
- [ ] You survived MILO's quiz and can answer "what does `recordStudySession` return?" without peeking.
- [ ] Study Buddy shows your streak after finishing a quiz, and the number survives a page reload.
- [ ] `streak.js` is byte-for-byte unchanged.

---

## Save your work

Commit `streak.js`, `my-explanation.md`, and your Study Buddy changes with a message that says what the feature does — something like `Add daily streak to Study Buddy (read + wired external module)`.

---

## Next

You can now read a stranger's code and make it work for you. Time to do it on a real app: **[lessons/15-capstone-fix-something-real.md](15-capstone-fix-something-real.md)**.
