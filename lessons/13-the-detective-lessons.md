# Lesson 13 — The Detective Lessons

Remember the feedback note you filed when GetAdvice froze? You described what you did, what you expected, and what actually happened. That was detective work. Today you switch sides: you are the one who *reads* the clues and finds the culprit.

Here is the mindset shift this lesson is about: **an error message is not the page yelling at you. It is the page handing you a clue.** Good coders are not people who never see errors. They are people who read them calmly.

Back to the house: when a light does not turn on, you do not repaint the walls. You check the wiring. The browser has a fuse box that shows you exactly which wire complained — and you are about to open it.

---

## Your detective toolkit

**Tool 1 — the console.** Open your Study Buddy page in the browser, right-click anywhere, choose **Inspect**, then click the **Console** tab. (Shortcut on a Mac: **Cmd + Option + J**.) Using Safari? First turn on the Develop menu (Safari → Settings → Advanced → "Show features for web developers"), then right-click → **Inspect Element** works — the shortcut above is Chrome's. This panel is where the browser reports every complaint from your wiring. Keep it open for this whole lesson.

**Tool 2 — error anatomy.** Every error answers three questions, in this order:

| Clue | Question it answers | Where to look |
| --- | --- | --- |
| **What** | What kind of problem is it? | The first words, e.g. `ReferenceError` |
| **Where** | Which file and line? | The right side, e.g. `quiz.js:12` |
| **Why** | What was the browser trying to do? | The rest of the message, in plain-ish English |

**Tool 3 — `console.log` as a flashlight.** A line like `console.log("score is", score)` prints a value to the console while your code runs. When you cannot *see* what a variable holds, shine the flashlight on it. Add a log, look, remove it when done.

---

## The detective loop

Every bug falls to the same four steps. No guessing sprees, no changing five things at once.

1. **Observe.** Read the error (what / where / why), or describe exactly what looks wrong.
2. **Hypothesize.** Say out loud: "I think the problem is ___ because ___."
3. **Test ONE change.** Change one thing. Only one. Reload. Look again.
4. **Repeat.** New clue? Back to step 1. Fixed? Case closed.

One change at a time is the whole discipline. Change three things and you will never know which one mattered.

---

## Coach mode: bring MILO the clue, not the code

New rule for this lesson: when you hit an error, paste the **error message** to MILO first — *not* your code. Reason together from the clue alone, like two detectives over a case file:

```text
I'm debugging on my own. Here is the error message only:
[paste the exact error]. Don't ask for my code yet and don't
give me the fix. Ask me questions until I can explain the
what, the where, and the why of this error myself. Then let
me propose a fix, and only review my reasoning.
```

If you can explain the error before showing the code, you have already done most of the detective work.

---

## The case files 🔍

Three broken snippets. Your job: make each one fail **on purpose**, read the clue, run the loop, and fix it. Work in a scratch page (`bugs.html` next to your Study Buddy files) or in a *copy* of your Study Buddy — never your only good version. Take the cases one at a time, console open.

**Case 1 — The vanishing variable.** Put this in a `<script>` tag and load the page:

```js
let score = 0;
function addPoint() {
  scor = scor + 1;
  console.log("Score is now " + score);
}
addPoint();
```

The console shows red. Read the what, the where, and the why before you touch anything.

**Case 2 — The quiz that shortchanges you.** No red error this time — the code runs, but the answer is *wrong*. These bugs need the flashlight.

```js
let results = [true, false, true, true]; // 3 correct answers
let score = 0;
for (let i = 1; i < results.length; i++) {
  if (results[i] === true) {
    score = score + 1;
  }
}
console.log("You scored " + score); // says 2 — it should say 3
```

Hypothesize which answers the loop actually checks, then prove it with a `console.log` *inside* the loop.

**Case 3 — The button that isn't there yet.** Put the script and the button in exactly this order on the page:

```html
<script>
  const startButton = document.getElementById("start-btn");
  startButton.addEventListener("click", function () {
    console.log("Quiz started!");
  });
</script>
<button id="start-btn">Start quiz</button>
```

Red error again. This one is sneaky: the code is "correct," but it runs at the wrong *moment*. Think about the order the browser reads the page, top to bottom.

Fix all three. For each, follow the rule: error to MILO first, code only if you are truly stuck.

---

## Stuck?

Escalate through these hints one at a time. Do not jump to hint 3 first — that is where the learning leaks out.

1. **Hint 1:** Every case is answered by one of your three tools. Case 1 and Case 3: read the error's what/where/why slowly. Case 2: the flashlight. Log `i` and `results[i]` on every trip through the loop and compare with what you expected.
2. **Hint 2:** Case 1 — the browser says it has never heard of some name; compare that name, letter by letter, with the variable you declared. Case 2 — where does `i` *start*, and which position is the first answer in the list? Case 3 — at the moment the script runs, does the button exist yet? What did `getElementById` hand back?
3. **Hint 3:** Case 1 is a spelling fix — the misspelled name appears **twice** on one line; fix both or the case isn't closed. Case 2 is a one-character change in the loop's starting line. Case 3 needs no new code — move one block so the wiring is connected *after* the thing it connects to exists.

---

## 🎉 Milestone: you read errors like clues

Three cases, three culprits, zero guessing sprees. That is real detective work.

---

## Prove it

Show, don't feel. You are done when you can check every box:

- [ ] You can open the DevTools console on any page without looking up how.
- [ ] Case 1 runs clean, and you can explain the bug in **one sentence** (what / where / why).
- [ ] Case 2 prints the right score, and you can explain the bug in **one sentence**.
- [ ] Case 3's button logs on click, and you can explain the bug in **one sentence**.
- [ ] You pasted at least one **error message** (not code) to MILO and reasoned it out together.
- [ ] You added a `console.log` flashlight to solve Case 2 — and removed it after.

Say your three one-sentence explanations to MILO and ask it to challenge anything fuzzy.

## Save your work

Commit your fixed case files with a message that names the crime, e.g. `git commit -m "Fix three bugs: typo, off-by-one, script-before-element"`.

## Next

You just read broken code you did not write — that is a superpower. Time to point it at healthy code: **[lessons/14-reading-strangers-code.md](14-reading-strangers-code.md)**.
