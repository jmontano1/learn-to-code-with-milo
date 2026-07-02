# Lesson 19 — Build the Landing Page 📣

You know who GetAdvice is for — you wrote it down in `marketing/research/audience.md`. You know how GetAdvice talks — you wrote the voice guide in [lesson 18](18-voice-and-message.md). Today the two halves of your training finally meet: the builder from Level 2 and the marketer from Level 3 sit down at the same desk, and they are both you.

You are going to design and build a **real, single-page landing page for GetAdvice** — structure, paint, and wiring, every word in voice.

---

## What you'll learn

- The anatomy of a landing page that actually works: **hero promise → three benefits → social proof → one call-to-action**
- **Mobile-first CSS** — building for the phone screen first and letting bigger screens be the upgrade
- The copy-first workflow real teams use: words before walls
- The **5-second stranger test**, the fastest quality check in marketing

## Why this matters

GetAdvice is a real iOS app in the middle of a real launch, made by a real company — JM Automated Solutions. Its whole reason for existing is that many people feel intimidated by AI, and GetAdvice is the friendly voice-and-chat advisor that meets them where they are. A landing page is often the **only** chance to say that before a stranger leaves. If the page is confusing, slow on a phone, or sounds like a robot wrote it, the person GetAdvice was built for closes the tab — and never finds out the app was built *for them*.

And there is a selfish reason too. Most marketers cannot build. Most builders cannot write. A landing page you **designed AND built** — where you can defend every word and every line of CSS — is a genuine portfolio piece. Interviewers notice.

---

## The rules of the page

Before you touch a file, the constraints. Level 3 gives you goals and constraints, not recipes — same deal as Level 2.

| Rule | Why |
| --- | --- |
| One page, one screen-flow, top to bottom | A landing page has one job. Extra pages are exits. |
| Exactly **one** call-to-action, repeated at most twice | Two buttons asking different things = a visitor asking "wait, which?" and leaving |
| Every sentence must pass your voice guide | The page speaks *as* GetAdvice. Off-voice words are bugs. |
| Mobile-first | Most strangers will meet this page on a phone |
| Plain HTML, CSS, and a little JS — no libraries | Your Levels 1–2 toolbox is enough, and you can explain all of it |
| **No invented proof.** No fake quotes, no made-up numbers, ever | This is a real product. Trust is the product. More below. |

---

## Build it

### Step 1 — [You do] Study the anatomy in the wild

Visit three landing pages for apps you actually like, plus [getadviceapp.com](https://getadviceapp.com). For each one, write four quick lines in your notes:

- **Promise:** what does the headline claim I'll get?
- **Benefits:** what three-ish good things does it show me?
- **Proof:** how does it make me believe (quotes, logos, numbers)?
- **Action:** what is the ONE thing it wants me to do next?

If you can't answer one of the four in ten seconds, that page has a bug. Note that too — other people's bugs are free lessons.

### Step 2 — [Ask MILO] Defend the order

```text
I analyzed 4 landing pages and noted each one's promise, benefits,
proof, and call-to-action. Here are my notes. Quiz me: ask me why
each element is ordered the way it is on the page, and what would
break if the order were reversed. Don't lecture — ask, then react.
```

That "why is it in this order" question is the whole lesson hiding in one prompt. Promise first because attention dies in seconds. Proof before the ask because strangers don't trust strangers. Always ask why — a layout you can't explain is a layout you copied.

### Step 3 — [You do] Words before walls

Grab the worksheet at [templates/landing-wireframe.md](../templates/landing-wireframe.md), copy it into your repo as `marketing/landing/wireframe.md`, and fill it in — **before writing any HTML**. Open `marketing/voice/voice-guide.md` and `marketing/research/audience.md` side by side while you write:

- **Hero promise:** one sentence, twelve words or fewer, in voice. Not what GetAdvice *is* — what the reader *gets*.
- **Three benefits:** take three real pains from your audience research and flip each into an outcome. "Feels intimidated by AI" becomes something like a benefit about asking anything without feeling judged — but in *your* voice guide's words, not mine.
- **Social proof:** here's the honest move. You have been GetAdvice's feedback tester since day one — that is true, so **your own one-line quote is real proof**. Write it. Then add two clearly-labeled placeholder slots ("More voices coming soon") for future testimonials. Placeholders are honest. Invented quotes are lies with nice fonts.
- **CTA label:** starts with a verb, four words max, and the button goes to [getadviceapp.com](https://getadviceapp.com).

Write every word yourself. This is the deliverable where "write it yourself" stops being a learning principle and becomes a legal-and-trust principle: it's a real product's public face.

### Step 4 — [Ask MILO] The voice check

```text
Here is the GetAdvice voice guide I wrote, followed by my draft
landing-page copy (hero, three benefits, proof section, CTA label).
Judge every line strictly against the guide. Flag anything that
breaks tone, uses jargon, or over-promises — and tell me WHY it
breaks, but do not rewrite it for me. I'll do the rewriting.
```

Expect flags. Getting flagged is not failing — it's the process working. Rewrite, run the check again, repeat until clean.

### Step 5 — [You do] Structure: the frame goes up

Now, and only now, HTML. Create `marketing/landing/index.html`. Same house you've built since Level 1 — structure first, paint second, wiring last. Frame it semantically:

```text
<header>  → hero: promise, subline, CTA button #1
<main>
  <section> → three benefits
  <section> → social proof (your real quote + labeled placeholders)
  <section> → final CTA (button #2, same action)
</main>
<footer>  → "GetAdvice · made by JM Automated Solutions" + link
```

One `<h1>` — the promise. Benefits get `<h2>`s. Don't reach for `<div>` where a real element exists; you learned why in Level 2 when you read strangers' code and blessed the ones that used honest tags.

### Step 6 — [Ask MILO] Mobile-first, concept only

```text
Explain mobile-first CSS and media queries to me with one tiny
example that is NOT a landing page. Concept only — do not write
my stylesheet. Then ask me two questions to confirm I've got it.
```

The short version you're about to hear: your base CSS styles the *narrow* screen, and a `@media (min-width: ...)` block adds changes for *wider* screens. Phone is the default, desktop is the enhancement — because that's the order your visitors arrive in.

### Step 7 — [You do] Paint, phone-first

Create `marketing/landing/style.css` and link it from your HTML. Base styles first, as if desktop didn't exist: a single column, comfortable text size, and a CTA button big enough to hit with a thumb — generous padding, full-width is fine. Then one media query (`min-width: 640px` is a sensible line) that lets the wide version breathe: maybe the three benefits become three columns, maybe the hero text grows.

Test at BOTH widths as you go — open your browser's responsive/device mode and flip between a phone width and full desktop. Your first mobile layout will break somewhere. Everyone's does. A squished button or overflowing headline isn't a verdict on you; it's the next thing to fix, and fixing it is the skill. Mistakes are part of the process.

### Step 8 — [You do] One touch of wiring

Add one small piece of JavaScript — Level-2 wiring, used with restraint. Good options, pick **one**:

- The hero rotates through three real example questions someone could ask GetAdvice (in voice!), changing every few seconds
- A gentle scroll from the hero CTA down to the final CTA section

If a script doesn't help a stranger decide, it's decoration. One touch. That's the discipline.

### Step 9 — [Ask MILO] The 5-second stranger test

```text
You are a busy stranger on a phone. You will "see" my landing page
for 5 seconds. Here is my full HTML and CSS. Answer ONLY from what
a visitor would see, top of page first: 1) What is this product?
2) Who is it for? 3) What am I supposed to do next? If any answer
is fuzzy, tell me which element failed me.
```

If MILO-the-stranger fumbles any of the three, fix the page and run it again. A landing page that needs explaining is a landing page that failed.

---

## Ship it 🚀

1. Commit the wireframe first — it's the design record: `git commit -m "landing: wireframe — copy in voice, one CTA"`
2. Commit the page: `git commit -m "landing: GetAdvice landing page — hero, benefits, real proof, mobile-first"`
3. Push.
4. Add one line to this week's journal (`marketing/journal/week-NN.md`) — and remember the front-matter block at the top (`week / focus / shipped / learned / blocked / feedback-for-getadvice`) is not decoration. **The front-matter IS the report.** MILO reads these files automatically; nobody is going to chase you for status, because your repo already answered.

---

## 🌟 Milestone

The rubric looks for **`marketing/landing/index.html`** in your repo, with a linked **`marketing/landing/style.css`** beside it — one page, one CTA, every word in voice.

---

## Stuck?

1. Staring at a blank hero? Read your voice guide's "we always sound like" line out loud, then finish this sentence as GetAdvice: "You can finally..."
2. Layout exploding on mobile? Delete your media query temporarily. Make the narrow version perfect alone. Only then add the wide version back — mobile-first means mobile *finished* first.
3. CTA feeling weak? Verbs beat nouns and outcomes beat features: "Learn more" is furniture; something like "Try your first question" is a door. Yours should be a door — in your voice, not mine.

## Next

You just did the thing most people on a launch team cannot do alone: you decided what a product's front door should say, and then you built the door. In [Lesson 20 — The Content Engine](20-content-engine.md), you start bringing people to it.
