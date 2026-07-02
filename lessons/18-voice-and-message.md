# Lesson 18 — Voice and Message 📣

In the last lesson you did the unglamorous work: you studied real people in `marketing/research/audience.md` and real alternatives in `marketing/research/competitors.md`. Today you turn that research into words — one clear promise, a voice guide, and your first draft of App Store-style copy for GetAdvice. This is the lesson where the launch starts to *sound* like something.

---

## What you'll learn

- How to compress a whole persona into **one promise sentence**
- What a **brand voice** is, and how to write a voice guide someone else could actually follow
- How to draft **App Store-style copy**: title line, subtitle, three benefit bullets, a short description
- How to use AI for **variants and critique** without letting it write your final lines — you pick, and you edit every line by hand

---

## Why this matters

GetAdvice exists for people who feel intimidated by AI. Think about what that means for words: the App Store page is the very first thing a nervous first-time user reads, *before* they trust the app with a single question. If that page sounds like a tech spec, they close it. If it sounds like a friend, they tap Get.

You have been GetAdvice's feedback tester since day one — you know how the app actually feels to use. Now you get to speak for it. The copy you draft today goes into the real pile of candidate copy for the real launch. Not a simulation. A draft with your name on the commit.

---

## Step 1 — From persona to promise

**[You do]** Open `marketing/research/audience.md` and pick your **primary persona** — the one person GetAdvice most needs to win. Then write **five** versions of this sentence, by hand, in a scratch file or on paper:

> GetAdvice helps **[who]** **[do what]** without **[the fear or pain]**.

Five versions, not one. Your first will be flat. Your second will be too clever. Somewhere around the fourth, you'll write one that sounds like a human said it. Bad drafts are not failure — they are the process working exactly as designed.

Rules: no word your persona wouldn't say out loud. "Leverage" is banned. "AI-powered" is banned. If your grandmother would squint at a word, cut it.

**[Ask MILO]** Get critique — not replacement:

```text
Here are five one-sentence promises for GetAdvice, a friendly iOS app
that helps everyday people learn and use AI with confidence. My primary
persona is: [paste the persona from marketing/research/audience.md].
Don't write new versions for me. For each of my five, tell me: which
words would make this persona lean in, and which would make them feel
stupid or sold to. Then ask me which one I believe most, and why.
```

That last question — *why* — is the whole game. If you can't say why a line works, you don't own the line yet.

Pick your winner. That sentence is now **the promise**, and everything else in this lesson has to agree with it.

---

## Step 2 — Write the voice guide

A voice guide is a short document that answers one question: *how does this brand talk?* Think of it like CSS for words. You already know why a stylesheet exists — so fifty pages look like one site instead of fifty arguments. A voice guide does the same for sentences: so every word GetAdvice ever publishes, written by anyone, sounds like the same friendly person.

You have been reading a working voice guide for eighteen lessons without knowing it. This course is warm, direct, plain-worded, allergic to jargon. That is not an accident — it is a voice, held consistently. GetAdvice's voice should feel like a close cousin: the patient friend who never makes you feel behind.

**[You do]** Create `marketing/voice/voice-guide.md` with exactly these sections:

| Section | What goes there |
| --- | --- |
| **The promise** | Your winning sentence from Step 1, alone at the top |
| **How we sound** | 3–5 traits. Each trait gets one line of "We say ___, not ___" — a real example, not an adjective floating by itself |
| **Words we love / words we ban** | Two short lists. Banned list must include at least five pieces of jargon from your competitor research |
| **Before / after** | Two cold, jargon-y sentences (steal bad ones from `marketing/research/competitors.md`) rewritten in the GetAdvice voice |

"Friendly" alone is useless — every brand on earth claims friendly. "We say *ask it anything, even the basic stuff* — not *submit natural-language queries*" is a rule someone can actually follow at 11pm before a deadline. Write rules, not vibes.

**[Ask MILO]** Stress-test the guide:

```text
Here is my draft voice guide for GetAdvice: [paste it]. Now rewrite
this sentence in that voice: "Our application utilizes advanced
language models to optimize your productivity workflows." Then tell
me honestly: where did my guide fail to constrain you? Which choices
did you have to guess at? Those gaps are what I need to fix.
```

Wherever MILO had to guess, your guide has a hole. Patch the holes and save.

---

## Step 3 — Draft the App Store copy, with AI as sparring partner

App Store-style copy has four parts, and each has a job:

| Part | Job | Shape |
| --- | --- | --- |
| **Title line** | Be findable and honest | App name plus a few plain words |
| **Subtitle** | The promise, squeezed hard | Roughly 30 characters — brutally short |
| **Three benefit bullets** | What the *user gets*, never what the app *has* | One line each |
| **Short description** | The promise with room to breathe | 2–4 sentences |

The bullet trap to avoid: features are about the app; benefits are about the person. Here is the difference, using a fictional recipe app so you can't copy it:

- Feature (weak): "Supports 10,000+ recipes with smart filtering"
- Benefit (strong): "Dinner ideas from whatever's already in your fridge"

Nobody wants filtering. Everybody wants dinner.

**[Ask MILO]** Now — and only now, with the promise and voice guide done — bring in the variant machine:

```text
Here is my voice guide for GetAdvice: [paste marketing/voice/voice-guide.md].
GetAdvice is a friendly iOS app — a voice and chat advisor that helps
everyday people learn and use AI with confidence, made for people who
feel intimidated by AI tools. Give me 3 different variants each of:
a title line, a subtitle around 30 characters, three benefit bullets,
and a short description of 2–4 sentences. Every variant must obey the
voice guide. Label the variants A, B, C so I can mix and match.
```

**[You do]** Read all the variants. Then close your eyes and answer: which lines can you still remember? Memorable is a signal. Now build your final copy — but here is the non-negotiable rule of this whole lesson:

**Every line in your final file must pass through your own fingers.** No copy-paste. Retype the lines you're keeping, and as you retype, you will feel yourself editing — tightening a word here, swapping a phrase there. Maybe you take variant B's subtitle but fix its verb. Maybe your best bullet is half A, half C, half yours (yes, that's three halves — good copy is like that). AI gave you clay. The sculpture is yours. That's not a productivity tip; it's the difference between owning this skill and renting it.

---

## Step 4 — The persona test

**[You do]** Read your final copy out loud, slowly, pretending you are your primary persona standing in a store aisle looking at their phone. Mark every word where they would stumble, squint, or feel dumb. Fix each one or defend it — out loud, with a *why*.

**[Ask MILO]** Then run the mirror version:

```text
Role-play as my persona: [paste the persona]. You've never heard of
GetAdvice and you're a little nervous about AI apps. I'm going to show
you App Store copy. React line by line, in character: what makes you
curious, what confuses you, what makes you feel like this app isn't
for people like you. Be honest, not polite. Here's the copy: [paste it]
```

If the persona flinches at a line you love, the persona wins. You are not the customer — you're the writer.

---

## Ship it 🚀

**[You do]** Create `marketing/voice/app-store-copy.md` with your final, hand-typed copy under these headings:

```markdown
# GetAdvice — App Store Copy (draft, v1)

## Title line
## Subtitle
## Benefit bullets
## Short description

## Runner-up variants I considered
(paste 2–3 rejected lines and ONE sentence each on why they lost —
future-you will thank present-you)
```

Then commit both deliverables with clear messages:

```bash
git add marketing/voice/voice-guide.md marketing/voice/app-store-copy.md
git commit -m "voice: GetAdvice voice guide + App Store copy draft v1"
git push
```

Remember how Level 3 works: **the commit is the report.** MILO reads these files from your repo automatically — nobody is going to message you asking for status, and you don't need to announce anything. Ship it and it's seen. When you write this week's journal entry in `marketing/journal/`, list both files on the `shipped:` line of the front-matter, and if the persona test taught you something the app itself should hear, put it in `feedback-for-getadvice:` — that line gets read too.

---

## 🌟 Milestone

The rubric looks for two files in your repo: **`marketing/voice/voice-guide.md`** and **`marketing/voice/app-store-copy.md`** — a voice guide with real "we say / not" rules, and App Store copy where every line was picked and edited by you.

---

## Stuck?

1. Promise sentence not landing? Go back to `marketing/research/audience.md` and find the persona's *fear* in their own words. The promise is usually just that fear, reversed.
2. Voice guide feels like adjectives soup? Delete every trait that doesn't have a "we say ___, not ___" example. What survives is your actual voice.
3. Can't choose between variants? Read each subtitle to a real person — a parent, a friend — and watch their face instead of asking their opinion. Faces don't flatter.

## Next

These words are about to get a home: in [Lesson 19 — Build the Landing Page](19-build-the-landing-page.md) you'll build the page where your copy has to earn its keep on a real screen.
