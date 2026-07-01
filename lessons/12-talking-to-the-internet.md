# Lesson 12 — Talking to the Internet

Your Study Buddy is smart now. It has rooms ([lessons/09-a-site-with-rooms.md](09-a-site-with-rooms.md)), logic ([lessons/10-logic-that-thinks.md](10-logic-that-thinks.md)), and memory ([lessons/11-memory-for-your-app.md](11-memory-for-your-app.md)). But it has one weakness: it only knows the questions **you** typed. Once you've played a few rounds, you know all the answers.

Today your app makes its first phone call to the outside world.

---

## What an API is

So far, every meal in your house was cooked in your own kitchen — your hardcoded questions array. An **API** is like a restaurant that delivers. You don't see their kitchen. You send an **order** (a request), written a specific way, and they send back **food** (data), packaged a specific way.

The restaurant you'll order from is called **Open Trivia DB**. It's free, and it serves quiz questions. Here is its order window:

```
https://opentdb.com/api.php?amount=5&type=multiple
```

Before writing any code, paste that URL into your browser. What comes back is **JSON** — data written in a shape JavaScript understands, all curly braces and quotes. Read it slowly. Find where the questions live. Find where the correct answer lives. You cannot cook with ingredients you haven't looked at.

---

## The one new tool: fetch

In your JS wiring, `fetch` is the phone. The honest, simplest shape of a call looks like this:

```js
const response = await fetch(url);
const data = await response.json();
```

Two new words, one plain meaning each:

| Word | What it really means |
| --- | --- |
| `await` | "This takes time — wait here until the answer comes back, then continue." |
| `async` | A label you must put on any function that uses `await` inside it. |

That's it. A call across the internet is not instant like your other code, so JavaScript makes you say, out loud, "I'm willing to wait here." That is the whole idea of `async`/`await`.

That snippet is all the syntax this lesson hands you. Wiring it into Study Buddy is your job.

---

## Your mission

Upgrade Study Buddy so that:

1. On load, it **fetches 5 real questions** from Open Trivia DB and runs the quiz with them.
2. The data from the API is **reshaped** to fit the question format your app already uses — don't rewrite your quiz logic to fit the API; make the API's data fit your quiz.
3. **If the fetch fails — or the server answers without questions** (no internet, API down, rate limit, error code) — the app does NOT break. It falls back to your local hardcoded questions **and tells the user**, in plain words, that it's running in offline mode.

Rule number three is not a bonus. In real apps, error handling is not decoration — it's the difference between "the app works" and "the app works when everything is perfect," which is a much smaller thing. The internet fails all the time. Plan for it.

Constraints:

- Keep your local questions array. It's your pantry for when the delivery doesn't come.
- No new libraries, no build tools. Just `fetch`, which every browser already has.
- The user should never see a blank screen or a dead app, no matter what the network does.

---

## One warning, on purpose

When your fetched questions first show up on screen, at least one of them will look **wrong** — strange codes where punctuation should be, something like `&quot;` sitting in the middle of a sentence.

That is not a bug in your code, and this lesson won't tell you what it is. It's a clue. Investigate it: read the raw JSON again, compare it to what's on screen, and ask MILO to explain what you're seeing — not to fix it for you. Detectives get a whole lesson next; consider this your warm-up case.

---

## Coach mode

When you get stuck — and this lesson is built so you will, at least once — do not ask MILO for the code. Ask for coaching:

```text
I'm upgrading my Study Buddy quiz to fetch 5 questions from
https://opentdb.com/api.php?amount=5&type=multiple and fall back to my
local questions array if the fetch fails. Don't write the code for me —
ask me questions until I can write it myself, then review what I wrote
and point at problems without fixing them.
```

And when you meet the strange `&quot;` characters:

```text
My quiz shows text like &quot; in the questions I fetched. Don't fix it.
Explain what this kind of text is called and why APIs send it, then let
me propose a fix and tell me if my idea would work.
```

---

## Test it like it will be used

A fetch that works on your fast home Wi-Fi proves almost nothing. Test the failure path on purpose:

- Turn off your Wi-Fi (or use airplane mode), reload the page, and watch what happens.
- Then turn it back on and reload again.

One more thing to know about this restaurant: **Open Trivia DB only takes one order per customer about every 5 seconds.** Reload too fast and the server answers — but with an error instead of questions. Wait a few seconds between reloads. And notice what that teaches you: a response that *arrives* is not automatically a *good* response. Check that the questions are actually there before using them, and fall back if they're not.

Both worlds must work. That's the assignment.

---

## Stuck?

Work through these in order. Give each one a real try before reading the next.

1. **Hint 1:** Your quiz already knows how to run from an array of question objects. The fetch's only job is to *produce that same kind of array*. Where in your code does the quiz currently get its array? That's the one place to change.
2. **Hint 2:** JavaScript has a way to say "try this risky thing, and if it throws an error, do this other thing instead." Ask MILO what `try` and `catch` do — concept only, no code — then write the fallback yourself inside the `catch`.
3. **Hint 3:** For the strange characters — the API sends text that is *HTML-encoded* (safe for web pages, ugly as plain text). `&quot;` is a `"` in disguise. One classic browser trick: put the encoded text into a throwaway HTML element and read it back out as plain text. Ask MILO to walk you through that idea step by step, with you typing.

---

## 🎉 Milestone: your app talks to the internet

Your house just made its first phone call — and it stays standing even when nobody answers.

---

## Prove it

Show, don't feel. Check each one off by actually doing it:

- [ ] Reload Study Buddy three times with internet on, **waiting at least 5 seconds between reloads** — you get **different questions** at least once, live from the API.
- [ ] The fetched questions display with **clean text** — no `&quot;`, no `&#039;`, no leftover codes anywhere on screen.
- [ ] Turn off Wi-Fi, reload — the quiz **still works** using your local questions, and a visible message says you're offline.
- [ ] You can explain to MILO, in your own words, what `await` is doing on your fetch line — and MILO agrees your explanation is right.

---

## Save your work

Commit with a message that says what changed and why, like `Add live trivia questions from Open Trivia DB with offline fallback`.

## Next

Something will still be quietly wrong somewhere — it always is. Time to learn how to hunt it: **[lessons/13-the-detective-lessons.md](13-the-detective-lessons.md)**.
