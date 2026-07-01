# Lesson 09 — A Site With Rooms

Welcome to your first real build on the Builder's Track. You read the new rules in [lessons/08-level-2-the-builders-track.md](08-level-2-the-builders-track.md): from now on you get the **goal**, not the recipe. You figure out the steps. MILO coaches; you build.

Here is the project you will grow for the next four lessons: **Study Buddy**, a quiz app you can use to study anything. Today you build its shell.

So far every page you built was a one-room house. Everything — welcome text, buttons, all of it — lived in one `index.html`. Real apps are houses with **rooms**: separate pages, each with one job, connected by hallways so you can walk between them.

| House part | Website part | In Study Buddy |
| --- | --- | --- |
| A room | One `.html` page | Home, Quiz, Scores |
| The hallway | The nav (links on every page) | How you move between them |
| One paint bucket | One shared `styles.css` | Every room painted from the same bucket |

That last row is the big idea of this lesson. You could give every page its own styles — but then changing your app's color means repainting three rooms, one by one, and hoping they match. Coders call the better way **DRY**: Don't Repeat Yourself. Write the paint recipe **once**, and let every room use it.

---

## Your mission

Build the Study Buddy shell as a multi-page site. Here is the spec — the what, not the how.

**The folder** (inside `my-projects/`):

```
study-buddy/
├── index.html
├── quiz.html
├── scores.html
└── styles.css
```

**The pages:**

| File | Its job | Must show |
| --- | --- | --- |
| `index.html` | The front door | A title, one sentence saying what Study Buddy is, and the nav |
| `quiz.html` | The quiz room | A heading, a line like "Questions arrive in Lesson 10", and the nav |
| `scores.html` | The trophy room | A heading, a line like "Scores arrive in Lesson 11", and the nav |

**The rules:**

1. The **nav appears on every page** and links to all three pages.
2. Links between pages are **relative** — they point to a neighbor file by name, not to a full web address.
3. There is exactly **one stylesheet**, `styles.css`, and **every page loads it**. No `<style>` blocks hiding inside pages.
4. At least **two visible rules** live in `styles.css` — one that styles the nav, one that styles something else you choose — so you can prove the shared paint works.
5. Every piece of code is **typed by you**. You already know the tags this needs from lessons 02–04. This is you discovering you can combine them.

That is the whole spec. Read it twice, then start.

---

## How to work with MILO now

At Level 2, MILO is your coach, not your builder. When you want help, ask for **questions**, not code. Like this:

```text
I'm building a multi-page site: index.html, quiz.html, scores.html,
one shared styles.css, and a nav that appears on every page.
Don't write the code for me. Ask me questions, one at a time,
until I can write it myself. Then review what I wrote and tell me
what's solid and what's shaky.
```

And when you finish, ask for a review the same way:

```text
Here are my four Study Buddy files: [paste them]. Don't rewrite
anything. Point at what works, what's fragile, and one thing a
more experienced builder would do differently. Let me make the
changes myself.
```

If MILO starts handing you finished code anyway, stop it and repeat the rule. Holding that line is part of the training.

---

## Stuck?

Use these in order. Try again after each one before reading the next.

1. **Hint 1:** A link to a file sitting in the same folder is much simpler than a link to a website. No `https`, no slashes. Think smaller.
2. **Hint 2:** You already own both tools this lesson needs. The `<a>` tag from lesson 02 can point its `href` at a neighbor file's name. The `<link rel="stylesheet">` line from lesson 03 works in the `<head>` of *any* page — not just the first one you ever put it in.
3. **Hint 3:** Each page's `<head>` gets the same one-line stylesheet link pointing at `styles.css`. The nav is the same small block of three `<a>` links near the top of each page's `<body>`. Yes — typing that nav three times feels like repeating yourself, and your DRY alarm should be ringing. Good instinct. Sit with the itch; the cure for repeated *HTML* is a real technique with a real name, and it's waiting for you beyond this track. Today, DRY-ing the **styles** is the win.

---

## 🎉 Milestone: Study Buddy has its rooms

One house, three rooms, one paint bucket — and you drew the floor plan yourself.

---

## Prove it

Walk through this checklist in your browser. Every line is something you can **show**, not feel.

- [ ] The `study-buddy` folder contains exactly the four files from the spec.
- [ ] Open `index.html` in the browser. Using only nav clicks, you can reach `quiz.html` and `scores.html`.
- [ ] Start on `quiz.html` instead. Nav clicks still reach both other pages. Same from `scores.html` — no dead ends, from any room.
- [ ] The browser's address bar changes as you move — proof you are switching pages, not scrolling one page.
- [ ] Change **one** rule in `styles.css` (say, the nav's background color). Reload all three pages. All three change. One paint bucket, whole house.
- [ ] Search your three `.html` files: no `<style>` blocks anywhere.

If any box will not check, that is not failure — that is the lesson. Read what the browser is actually doing, form a guess, and take the guess to MILO with the coach prompt.

---

## Save your work

Commit the `study-buddy` folder with a message that says what you built — for example `study-buddy: multi-page shell with shared nav and one stylesheet` — not `stuff` or `changes`.

---

## Next

Your house has rooms and paint, but the quiz room is empty. Time to wire in a brain that can ask questions and judge answers.

Go to **[lessons/10-logic-that-thinks.md](10-logic-that-thinks.md)**.
