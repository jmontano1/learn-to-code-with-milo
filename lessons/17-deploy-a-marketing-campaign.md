# Lesson 17 — Deploy a Marketing Campaign

This is the hardest lesson so far. Read that as a promise, not a warning.

Every lesson before this had a safety net: it all lived on your computer, where the only judge was you. This one does not. Today you put something **live on the internet**, ask **real people** to do a **specific thing**, and **count** whether they did. You will set a number in advance and then find out, in public, if you hit it.

There is no partial credit for "it basically works." A campaign either moved a real human or it did not, and you will know exactly which. That is what makes it hard. It is also what makes it worth more than any lesson so far.

MILO is your coach here, not your author. You will ask it to question you, review you, and teach you concepts — **you** write the words, the code, and the plan. When a full answer starts to appear, say "coach mode, remember?" and it backs up.

Everything you build lives in one new folder: **`my-projects/launch/`**. Make it now.

---

## The mission

> Pick one real thing. Get **one real stranger** to do **one specific action** because of something **you** put on the internet — and prove it with a number.

Small is not the problem. Fake is the problem. One real signup you can name beats a hundred you made up.

---

## Step 0 — Pick your one thing, and your one person

**Pick the thing** you will promote. Choose ONE:

- **Study Buddy** — the quiz app you built in Level 2. Promote it to people who want to study smarter.
- **Your journey** — "I'm learning to code with AI in public." Promote a page where people can follow along.
- **GetAdvice** — MILO's real face on the App Store. Promote it to someone who'd actually use it.

**Now the hard part: pick your one person.** Not "students." Not "everyone." *One human you could name or picture completely.* A marketer's first law: if you write for everyone, you move no one.

Create `my-projects/launch/campaign-plan.md` and write your **audience of one** — 3–5 sentences:

- Who are they? (age, life, what their Tuesday looks like)
- What problem of *theirs* does your thing solve?
- Where do they already spend time online? (this decides your channels later)

> **Constraint:** the word "everyone" is banned from this file. If you catch yourself widening the audience to feel safer, you are doing the opposite of marketing.

Coach prompt to sharpen it:

```text
I'm defining the single target person for a marketing campaign. Don't
write it for me — interrogate my description one question at a time
until this person feels like a real, specific human, then tell me
where my picture is still vague.
```

---

## Step 1 — Choose the one number that matters (before you build anything)

This is the step people skip, and skipping it is why most campaigns teach nothing. You will pick your metric **now**, in writing, before a single button exists — so you cannot move the goalposts later.

Add a `## The one number` section to `campaign-plan.md` with exactly three things:

| Field | Rule |
| --- | --- |
| **Metric** | ONE thing you can actually *count*. A number, not a feeling. |
| **Target** | A specific figure you're aiming for. Be honest, not heroic. |
| **Deadline** | A real date, days away, not "someday." |

Good metrics are countable: *clicks to my page*, *people who tapped the button*, *replies to my email*, *signups*. Banned metrics: "awareness," "buzz," "going viral" — you cannot count those, so they cannot teach you.

Write it as one sentence you could text a friend:

> "By **[date]**, get **[target]** **[metric]** from my campaign for **[thing]**."

> **Constraint:** if your target is a number you're 100% sure you'll hit, it's too soft — raise it. If it terrifies you, it's too hard — lower it. Aim where you genuinely don't know the answer.

---

## Step 2 — The offer and the message

People do not act because your thing is good. They act because, for **three seconds**, you made them believe it was good *for them*. That belief is built from three pieces. Add a `## Message` section with all three:

| Piece | Rule | Bad → Good |
| --- | --- | --- |
| **Headline** | ≤ 10 words. Speaks to your one person's problem, not your features. | "Study Buddy: a quiz app" → "Stop re-reading. Start remembering." |
| **Value line** | One sentence: the promise, in their words. | "It has flashcards and scoring." → "Quiz yourself in 5 minutes and actually keep it." |
| **Call to action (CTA)** | **ONE** action. One verb. One button. | "Sign up, follow, and share!" → "Try one quiz." |

> **The killer constraint:** you get **one** CTA. Not two. The moment you ask for two things, most people do zero. If you have a second idea you love, that is a *darling*, and the professional move is to kill it. Write your killed darling at the bottom of the section under `### Darlings I killed` — proof you made the cut.

Coach prompt:

```text
Here are my headline, value line, and one CTA: [paste]. Don't rewrite
them for me. Poke holes: which words are about ME instead of my
reader? Where am I asking for more than one thing? Ask, don't fix.
```

---

## Step 3 — Build the landing page, and put it LIVE

Here is the technical heart. You will build a one-page site with the structure, paint, and wiring you already own — and then do the new, scary, real thing: **deploy it to the public internet** so a stranger can open it on their phone.

Build it in `my-projects/launch/landing/` — `index.html` plus its CSS and JS. It must have, in this order:

1. Your **headline** (the first thing visible — no scrolling to find it).
2. Your **value line**.
3. Your **one CTA** — a single, obvious button.
4. Proof the button *works*: it does one real thing (opens a link, reveals a signup, starts a quiz — your call).

**Hard constraints, non-negotiable:**

- **It must be live at a real URL.** Not a file on your laptop. Live. Ask MILO to coach you through publishing a static site free — **GitHub Pages** or **Cloudflare Pages**. Learn the concept, then do the steps yourself.
- **It must work on a phone.** Your one person almost certainly opens it on a phone. Open it on yours (or resize the browser narrow). If the button is tiny or the text overflows, it is not done.
- **It must load fast.** No giant images, no libraries you don't need. A slow page is a closed page.
- **One CTA on the page.** The same discipline as Step 2. One button that matters.

When it's live, paste the real URL into `campaign-plan.md` under `## Live URL`. If you cannot open that URL in a private browser window (logged out, like a stranger), it is not really live — fix that before moving on.

Concept coach prompt:

```text
I want to publish a static HTML page for free at a public URL, using
GitHub Pages (or Cloudflare Pages). Don't paste the whole setup. Walk
me one step at a time, wait for me to do each step and tell you what I
saw, and help me fix errors when I hit them.
```

---

## Step 4 — Write the campaign that points at the page

A live page nobody visits is a billboard in the desert. Now you write the words that send your one person there. In `my-projects/launch/posts/`, create:

- **`social.md`** — **three** short posts for **three** different places your person actually hangs out (from Step 0). Each post obeys its channel's real limits and vibe:

  | Channel | Real constraint that forces a decision |
  | --- | --- |
  | A short-text feed (X, Threads) | ~280 characters. Every word fights for its life. |
  | A visual/story feed (Instagram, TikTok caption) | First line is a hook or it's scrolled past. |
  | A text-to-a-person (WhatsApp, iMessage, a DM) | Sounds like a human, not an ad. One friend to another. |

- **`email.md`** — one short email: a subject line under 6 words, three sentences of body, your one CTA as a link. Real reviewers are busy; a long email is an unread email.

> **Constraint:** every asset drives to the **same one CTA** and the **same URL**. If your social post asks for one thing and your email asks for another, you have two campaigns and zero focus.

---

## Step 5 — The pre-mortem (write why it will fail — before it does)

Professionals do a strange, powerful thing before launch: they *imagine it already failed* and write down why. It kills blind spots while you can still fix them.

Add a `## Pre-mortem` section to `campaign-plan.md`. Finish this sentence three different ways:

> "It's the deadline. I got **zero** results. The most likely reason is..."

Then, next to each reason, write the one small thing you'll do *now* to make that reason less likely. This is not pessimism. It is how you find the crack before the water does.

---

## Step 6 — Launch, count, and tell the truth

Now the real part. There is no simulation of this step.

1. **Ship it.** Publish the page. Send the email. Post the posts — to real people, in real places. (No fake accounts. No counting yourself. Ever.)
2. **Watch the number.** However you can count it — GitHub Pages/Cloudflare has a visitor count, a link can show clicks, replies you can literally count in your inbox. Set your own honest way to count, and write it down.
3. **Wait for your deadline.** Do not peek and panic-edit every hour. Let it run.
4. **Write the retro.** When the deadline hits, create `my-projects/launch/retro.md`:

   | Heading | What goes there |
   | --- | --- |
   | The number | Your target vs. what actually happened. The real figures. |
   | What worked | One thing that clearly helped. How do you know? |
   | What didn't | One thing that clearly didn't. How do you know? |
   | The one change | If you ran it again tomorrow, the single thing you'd change. |
   | Did the pre-mortem call it? | Did reality match one of your Step 5 fears? Which? |

---

## Reality check — read this before you judge yourself

Most first campaigns miss their target. Many get **very** small numbers. That is not you failing; that is the base rate of the entire profession. Seasoned marketers launch things that flop, measure why, and launch again smarter. The measuring is the skill. The relaunching is the career.

So here is the actual bar for passing this lesson: **you shipped something live, you asked real people, you counted honestly, and you can explain the result.** Hit your target and it's a great day. Miss it and write a sharp retro, and you learned *more* — because a miss you understand is worth more than a win you can't explain.

The one and only way to fail Lesson 17 is to fake the number, or to never ship because you were afraid of the answer.

---

## Stuck?

1. Frozen at Step 0? Stop trying to pick the "best" thing — pick the one you'd be least embarrassed to show a friend, and name the *friend* as your one person. Real beats optimal.
2. Stuck on "publish it live"? That is a brand-new skill and it's supposed to feel weird. Do the concept coach prompt in Step 3 and go one step at a time. When you hit an error, paste the exact error to MILO — errors are normal, and reading them is the detective skill from Lesson 13.
3. Nearly explicit on the whole shape: `campaign-plan.md` (one person, one number+target+date, message, live URL, pre-mortem) + `landing/` (live, phone-friendly, one CTA) + `posts/` (3 posts + 1 email, same CTA/URL) + `retro.md` (target vs. reality). Build the plan first, the page second, the posts third, then launch. One folder, real internet, real people, honest count.

---

## 🎉 Milestone: you launched something into the world

You didn't just build — you got a real page onto the real internet, put a real ask in front of real people, named a number in advance, and told the truth about what came back. That is the loop every product, company, and creator runs forever. You just ran it once, for real, with your own hands.

Most people who can code never learn this. You did.

---

## Prove it

- [ ] `my-projects/launch/campaign-plan.md` has a specific **audience of one** (no "everyone"), a **metric + target + deadline**, a **message** (headline ≤10 words, value line, ONE CTA, killed darlings), a **live URL**, and a **pre-mortem**.
- [ ] `my-projects/launch/landing/` is **live at a public URL** you can open logged-out on a phone, with your headline, value line, and one working CTA.
- [ ] `my-projects/launch/posts/` has **3 channel-specific posts + 1 email**, all pointing to the **same CTA and URL**.
- [ ] You actually **shipped** it to real people and can say how you counted.
- [ ] `my-projects/launch/retro.md` compares **target vs. real result** and answers all five headings honestly.

## Save your work

Commit and push everything with a message that states the launch, like `Level 3: launch campaign for Study Buddy — live page + retro`. Then email a 4-line summary to **milo@jmautomated.com**: your one number and whether you hit it, your live URL, the one thing that worked, and the one thing you'd change. Four lines. Ship clarity.

## What happens after this

You launched once. Next you build the machine that launches, tests, and improves *itself*. **[Lesson 18 — The Growth Engine](18-the-growth-engine.md)** is advanced AI marketing: use AI to generate at speed, then run a pre-registered A/B experiment, count an honest funnel, and prove with real math whether the engine actually turned — or whether you just got busy. It is harder than this lesson, which is why it comes after it. Open it when your campaign here has run and you've written your retro.

After that, the loop is yours: build a thing, launch it, grow it as a measured engine, repeat. Open [roadmap.md](../roadmap.md), read **Stage 4** (the map for this Level 3) one more time, and notice that its last milestone has no finish line on purpose. Keep launching. Then teach someone else to, the way this repo taught you. 🚀
