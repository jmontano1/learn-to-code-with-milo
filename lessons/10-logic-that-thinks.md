# Lesson 10 — Logic That Thinks

Welcome back, builder. In [lessons/09-a-site-with-rooms.md](09-a-site-with-rooms.md) you gave Study Buddy its rooms, and `quiz.html` is one of them — but right now it's a quiz the way an empty stage is a play. The structure is there. Nothing *happens*.

Back in Level 1, JavaScript was the **wiring** of the house: one switch, one light. Today you wire the *brain* of the house — logic that remembers where you are, decides if you were right, and keeps count. Same wiring, more circuits.

One more Level 2 reminder: this lesson tells you **what** to build and **what each piece must do**. You figure out **how**. That gap in the middle? That's where you become a programmer.

---

## The goal

By the end of this lesson, `quiz.html` actually quizzes:

1. It shows **one question at a time**, with clickable answer choices.
2. Clicking an answer moves you to the **next question** — and quietly keeps **score**.
3. After the last question, the page shows a **results state**: your score out of the total.
4. A **restart button** starts the whole thing over, score back to zero.

Constraints: at least **5 questions**, plain JavaScript in a `<script>` tag or a `.js` file, and no copy-pasting a finished quiz from anywhere. You write it.

---

## New tools for your belt

Five ideas, each in one plain sentence. You'll use all of them today.

| Idea | Plain English |
| --- | --- |
| **Variable** | A labeled box that holds a value you can change later — like `score` starting at 0. |
| **Array** | A numbered list of things, like question cards in a stack. |
| **Object** | One card with labeled fields — a question, its choices, its correct answer, together. |
| **if/else** | A fork in the road: *if* this is true do one thing, *else* do the other. |
| **`document.getElementById` + `textContent`** | How JavaScript reaches into your HTML and changes the words on the page. |

An array of objects is just a stack of filled-in cards. That's your whole quiz data.

---

## The blueprint

Here is the contract for each piece. Names, inputs, outputs — the *how* is yours.

**The data:**

- `questions` — an array of at least 5 objects. Each object needs: the question text, a list of answer choices, and which choice is correct.
- `currentQuestion` — a variable holding which card you're on (start at 0 — computers count lists from 0).
- `score` — a variable holding how many you've gotten right (start at 0).

**The functions:**

| Function | Input | What it must do | Output |
| --- | --- | --- | --- |
| `showQuestion()` | nothing | Read the card at `currentQuestion` and put its text and choices on the page. | nothing (it changes the page) |
| `handleAnswer(choice)` | the choice that was clicked | Compare it to the correct answer; if right, add 1 to `score`. Move to the next card — or, if there are no cards left, call `showResults()`. | nothing |
| `showResults()` | nothing | Hide the question area; show the score out of the total and a restart button. | nothing |
| `restartQuiz()` | nothing | Reset `currentQuestion` and `score` to 0, then call `showQuestion()`. | nothing |

Read that table twice. Notice how `handleAnswer` needs an `if/else` twice: once to check the answer, once to decide "next question, or results?"

---

## One worked example (your calibration)

So you can see the shape of a function — name, input, work, output — here is one, and only one:

```js
function shout(word) {
  const louder = word.toUpperCase() + "!";
  return louder;
}

shout("hello"); // gives back "HELLO!"
```

That's the pattern: something goes in, work happens, something comes out (or the page changes). Every function in your blueprint is this shape, just with quiz logic inside. Now go write them.

---

## Coach mode, not chef mode

You will get stuck today. Good — that's the workout. When you ask MILO for help, ask for a **coach**, not a chef who cooks for you. Paste something like this:

```text
I'm building the quiz logic for Study Buddy. I'm working on the
handleAnswer function. Don't write the code for me — ask me questions
one at a time until I can write it myself. When I paste my version,
review it and point at problems without fixing them for me.
```

If MILO starts handing you finished code anyway, say: "Stop — coach me instead." You're allowed to steer your tutor. That's a builder's move.

---

## Stuck?

Use these in order. Give each one a real try before reading the next.

1. **Hint 1:** Start with the data, not the functions. Write your `questions` array first, then make `showQuestion()` display just the *first* card. Get one card on screen before anything moves.
2. **Hint 2:** Clicks need a bridge. Each choice on the page needs a click handler that calls `handleAnswer` with *that* choice — this is the same event-runs-a-function idea from [lessons/04-make-it-interactive-js.md](04-make-it-interactive-js.md), once per choice.
3. **Hint 3:** "Are we done?" is a number question. After adding 1 to `currentQuestion`, compare it to how many cards are in the array (`questions.length`). If it's smaller, call `showQuestion()`. Else, call `showResults()`.

---

## 🎉 Milestone: your app can think

Structure, paint, wiring — and now a brain. Study Buddy remembers where you are, judges answers, and keeps score. Every app you've ever used is this same trick, scaled up.

---

## Prove it

Show, don't feel. Check each one for real, in the browser:

- [ ] The quiz has **5 or more questions**, and only one shows at a time.
- [ ] Clicking any answer advances to the next question every time.
- [ ] Answer some right and some wrong **on purpose**, count your correct ones on paper, and the final score matches your count.
- [ ] The results state appears after the last question — no more choices to click.
- [ ] The **restart button** returns you to question 1 with the score truly back at 0 (play a second round to prove it).

If any box won't check, that's not failure — that's your next 20 minutes.

---

## Save your work

Commit with a message that says what the app can *do* now, e.g. `git commit -m "Study Buddy: quiz asks, scores, and restarts"`.

---

## Next

Your quiz thinks — but it forgets everything on refresh. Let's give it memory: **[lessons/11-memory-for-your-app.md](11-memory-for-your-app.md)**.
