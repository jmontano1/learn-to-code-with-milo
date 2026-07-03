# Lesson 11 — Memory For Your App

Here's an experiment. Open your Study Buddy from [lessons/10-logic-that-thinks.md](10-logic-that-thinks.md), play a round, get a great score... then hit refresh.

Gone. Every time. Why?

Remember the house: HTML is the structure, CSS is the paint, JS is the wiring. Your score lives in the **wiring** — in JavaScript variables. And wiring only holds electricity while the power is on. Refresh the page and you cut the power. Everything in the wires vanishes.

Today you give your house a **filing cabinet**: a place where things stay put even when the lights go off. By the end of this lesson, Study Buddy remembers your best score, how many times you've played, and when you last played — even after you fully close the browser.

---

## The two ideas you need

**1. localStorage — the filing cabinet.** Every browser gives each website a small storage space that survives refreshes, closed tabs, even a full shutdown. Two moves, that's the whole API:

| Move | What it does |
| --- | --- |
| `localStorage.setItem("key", value)` | Put something in the cabinet under a label |
| `localStorage.getItem("key")` | Take it back out by its label |

**2. JSON — the suitcase.** The cabinet has one strict rule: it only stores **text**. But your data is an object — a score, a count, a date, maybe a list. JSON is how you pack an object into a single string of text, like folding your clothes into a suitcase for a trip:

| Move | What it does |
| --- | --- |
| `JSON.stringify(myObject)` | Pack the object into a text string (suitcase zipped) |
| `JSON.parse(someText)` | Unpack the string back into a real object |

Pack before you store. Unpack after you retrieve. That's the whole dance.

---

## Your mission

Upgrade Study Buddy so it remembers. Here is the goal — the steps are yours to figure out.

**The app must save, and keep across a full browser close:**

- **Best score** — the highest score ever, not just the latest.
- **Attempts count** — how many rounds have been played, total.
- **Last played** — the date of the most recent round.
- **A history list** — one entry per finished round, with its score and date. (You'll need this for the challenge below.)

**Constraints:**

1. Everything lives under **one** localStorage key. Design one object that holds all four things, and pack/unpack it with JSON. Ten scattered keys is a messy cabinet.
2. Saving happens when a round **ends** — right where your lesson 10 logic already knows the final score.
3. Decide what your saved object looks like **on paper first**, before you write any code. Sketch it as a comment at the top of your script.

Before you start, open the browser console and play with the cabinet by hand: `setItem` a string, `getItem` it back, refresh, get it again. Thirty seconds of poking will teach you more than any paragraph.

---

## The edge case that separates builders from beginners

What does `localStorage.getItem` give you on someone's **very first visit**, when nothing has ever been saved?

Find out — check it in the console before writing another line. Your code must handle that answer without crashing. First visit is not an error. It's just an empty cabinet, and your app should treat it like one: start fresh, no drama.

---

## The challenge: a trophy room *(optional stretch)*

This one is a **stretch goal** — a second page, so it's a real step up. If your quiz already saves and loads correctly (best score, attempts, last-played, and the friendly empty state), you have already passed this lesson's core. Do the trophy room when you're ready for the challenge; it's worth it, but it's not required to move on.

Your site has a trophy room waiting: the **scores.html** placeholder you built in [lessons/09-a-site-with-rooms.md](09-a-site-with-rooms.md) — "Scores arrive in Lesson 11," it says. Time to fill it in.

**The goal:** scores.html reads the saved data from localStorage and shows the history in a real HTML table — one row per round, with the score and the date. Above the table, show the best score and total attempts.

**One rule for first-timers:** if there is no saved data yet, the page must NOT show a broken or empty table. Show a friendly message instead — something like "No rounds played yet. Go play your first one!" with a link back to the quiz.

Notice what's happening here: **two different pages sharing one memory**. The quiz page writes to the cabinet; the trophy room reads from it. That is a real app pattern, and you're about to build it.

---

## How to work with MILO on this

This is Level 2 — MILO coaches, you build. Paste something like this:

```text
I'm adding memory to my Study Buddy quiz with localStorage and JSON.
I want it to save best score, attempts count, last-played date, and a
history of rounds under one key. Don't write the code for me — ask me
questions until I can write it myself, then review what I wrote.
Start by asking me what my saved object should look like.
```

And when your code misbehaves (it will — that's the job):

```text
My save/load code isn't working. Here's what I expected, here's what
actually happened, and here's my code: [paste]. Don't fix it for me —
help me read the error and find it myself.
```

---

## Stuck?

Use these one at a time. Read a hint, go try again, come back only if you're still stuck.

1. **Hint 1:** The bugs in this lesson almost always live at the border between object-land and text-land. At every save and every load, ask: "right now, is this a string or an object?" The console and `typeof` will tell you.
2. **Hint 2:** Load has two paths: cabinet has something → `JSON.parse` it and use it; cabinet is empty → build a fresh starter object (best score 0, attempts 0, empty history). Write the empty path first. An `if` on what `getItem` returned decides which path you're on.
3. **Hint 3:** The rhythm at round-end is load → update → save: get the object out (or the fresh starter), push the new round into `history`, bump `attempts`, compare the new score against `bestScore` and keep the bigger one, set `lastPlayed` to today, then `setItem(key, JSON.stringify(theObject))`. For scores.html, loop over `history` and build a `<tr>` per entry.

---

## 🎉 Milestone: your app remembers

Structure, paint, wiring — and now a filing cabinet that survives the lights going off.

---

## Prove it

Show, don't feel. Check off every one:

- [ ] Play a round, **fully quit the browser** (not just the tab), reopen — best score, attempts, and last-played are still there.
- [ ] Play two rounds — attempts goes up by exactly 2.
- [ ] Score lower than your best — best score does **not** go down.
- [ ] Wipe the memory (ask MILO how to clear localStorage from the console), reload the quiz — it starts clean with no errors in the console.
- [ ] *(stretch — the trophy room)* Open scores.html — it shows one row per round with score and date, and a friendly empty state when there's no saved data yet.

---

## Save your work

Commit with a message that says what changed and why, like `Add localStorage memory and scores page to Study Buddy`.

---

## Next

Your app remembers. Now let's teach it to talk to the rest of the world: **[lessons/12-talking-to-the-internet.md](12-talking-to-the-internet.md)**.
