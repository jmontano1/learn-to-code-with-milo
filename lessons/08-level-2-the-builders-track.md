# Lesson 08 — Level 2: The Builder's Track

Stop for a second and look at what you just did.

You finished **all seven lessons** of Level 1. You built **two projects** with your own hands. You made **real git commits** — actual save points a real developer would recognize. And you filed **two real feedback notes** on a live app: [feedback-getadvice/notes/2026-07-01-app-froze.md](../feedback-getadvice/notes/2026-07-01-app-froze.md) and [feedback-getadvice/notes/2026-07-01-incorrect-info.md](../feedback-getadvice/notes/2026-07-01-incorrect-info.md). Those notes are not homework. They are contributions to a product people use.

Most people never get this far. You did it in one run. So here is your reward: **things get harder now.** On purpose. Welcome to the Builder's Track.

---

## What changes in Level 2

In Level 1, MILO handed you a recipe: step 1, step 2, step 3, done. That was right for then. But recipes teach you to *follow*. Builders learn to *figure out*.

| | Level 1 | Level 2 |
| --- | --- | --- |
| Instructions | Step-by-step recipes | A **goal** and some **constraints** — you find the steps |
| MILO's role | Writes code, explains each line | **Coaches** you — asks questions until *you* can write it |
| Finishing | "Did it work?" | A **Prove it** checklist of things you can *show* |
| When stuck | The fix was in the lesson | **Graduated hints** — vague first, nearly explicit last |

The house analogy still holds — HTML is the structure, CSS is the paint, JS is the wiring. But in Level 1 you assembled rooms from instructions. In Level 2 you get a floor plan and a toolbox, and *you* decide where the walls go.

---

## Coach mode: the most important prompt you'll learn

In Level 1 you pasted prompts that asked MILO to build things. From now on, you ask MILO to **coach**. Here is the pattern — learn its shape, because you will write your own versions of it constantly:

```text
I'm trying to [your goal]. Don't write the code for me — ask me
questions until I can write it myself, then review what I wrote.
```

Read that twice. Notice the three moves:

1. **State the goal** — what you're trying to build, in your own words.
2. **Set the boundary** — "don't write the code for me." You are protecting your own learning.
3. **Invite review** — MILO checks your work *after* you've done the thinking.

This feels slower than "just write it for me." It is. It is also the difference between owning a skill and renting one. A coach who does your push-ups for you is very efficient and completely useless.

MILO will honor the boundary — that's the deal. If you ever catch a full solution appearing anyway, say "coach mode, remember?" and it will back up.

---

## The road ahead

Level 2 has one running project and two special tracks.

**The Study Buddy arc (lessons 09–12).** You will build one app — **Study Buddy**, a quiz app — and grow it across four lessons. Each lesson builds on the last lesson's version, like a house going up floor by floor:

| Lesson | Study Buddy grows... |
| --- | --- |
| [09 — A Site With Rooms](09-a-site-with-rooms.md) | multiple pages that work together (structure) |
| [10 — Logic That Thinks](10-logic-that-thinks.md) | real quiz logic: right, wrong, score (wiring) |
| [11 — Memory for Your App](11-memory-for-your-app.md) | it remembers you between visits |
| [12 — Talking to the Internet](12-talking-to-the-internet.md) | it fetches fresh questions from the web |

**The detective lessons (13–14).** Then you switch hats. In [13 — The Detective Lessons](13-the-detective-lessons.md) you learn to hunt bugs on purpose, and in [14 — Reading Strangers' Code](14-reading-strangers-code.md) you open code you did not write and figure out what it does. Writing code is speaking; reading code is a whole second language.

**The capstone (15).** In [15 — Capstone: Fix Something Real](15-capstone-fix-something-real.md), you take **your own two GetAdvice feedback notes** — the froze bug and the incorrect-info one — and turn one of them into a real fix proposal. The notes you wrote today become the raw material for real work. That was the plan all along.

---

## Expect the struggle. It's the curriculum.

Here is the honest part: Level 2 is *supposed* to feel harder. There will be moments where you stare at a goal and think "I don't know where to start." That moment is not a sign you're failing. That moment **is the lesson**.

Struggling productively — sitting with a problem, trying something, being wrong, trying again — is the single skill that separates people who can code from people who once took a course. Every lesson has a **Stuck?** section with graduated hints: hint 1 is a nudge, hint 3 practically hands you the answer. Use them in order, and only when you've genuinely tried. Reaching for hint 1 after real effort is smart. Reaching for hint 3 first is just Level 1 with extra steps.

---

## Your warm-up challenge

No recipe. Here is the goal:

**Set up the Study Buddy project and take coach mode for a test drive.**

Constraints:

- Create a `study-buddy` folder inside `my-projects/`, with a short `README.md` in your own words: what the app will do and who it's for (hint: *you* are the user — what do you want to quiz yourself on?).
- Then pick the Level 1 topic you found hardest, and use the coach-mode pattern to ask MILO to quiz you on it — MILO asks, you answer, MILO tells you how you did.
- You write the prompt yourself. Don't copy the example above word for word — adapt it.

That's it. Figure out the steps.

---

## Stuck?

1. You already know how to make folders and files — you did it in every Level 1 project. Same moves, new destination.
2. For the coach-mode test drive, your prompt needs the three moves: goal, boundary, invite. Your goal here is "quiz me on [topic]," not "build me something."
3. Nearly explicit: create `my-projects/study-buddy/README.md`, write 3–5 sentences about your quiz app, then paste MILO a prompt like: "I'm trying to check I really understood [topic] from Level 1. Don't explain it to me — quiz me one question at a time, and after five questions tell me what I should review."

---

## 🎉 Milestone: you're on the Builder's Track

Level 1 taught you to follow the map. Level 2 teaches you to draw it.

---

## Prove it

- [ ] `my-projects/study-buddy/README.md` exists and says, in your words, what Study Buddy will do.
- [ ] You can show a conversation where you used a coach-mode prompt and MILO quizzed you instead of lecturing you.
- [ ] You can point to your two feedback notes in `feedback-getadvice/notes/` and say which one you'd pick for the capstone, and why in one sentence.
- [ ] You can say the three moves of a coach-mode prompt out loud without looking: goal, boundary, invite.

## Save your work

Commit with a message that says what actually changed — something like `Start Level 2: create study-buddy project`.

## Next

Time to give Study Buddy its rooms: **[lessons/09-a-site-with-rooms.md](09-a-site-with-rooms.md)**.
