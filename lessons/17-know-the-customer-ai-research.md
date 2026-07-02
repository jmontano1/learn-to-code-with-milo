# Lesson 17 — Know the Customer: AI-Powered Research 📣

You're not a student following recipes anymore — you're a junior growth teammate on a real product launch, and this is the first real task every growth team does. Before anyone writes a headline, designs a page, or posts a single word, someone has to answer the oldest question in marketing: *who is this actually for?* Today, that someone is you.

---

## What you'll learn

- How to find and interview real people who feel intimidated by AI tools
- How to hand MILO messy raw notes and get honest patterns back
- The most important AI skill on this whole track: **challenging the output** instead of trusting it
- How to turn research into two short personas a whole team can build on
- How to do a competitor scan that's honest enough to be useful

## Why this matters

GetAdvice exists for one reason: a lot of everyday people feel intimidated by AI tools — they hear about AI constantly, they suspect it could help them, and they still don't open the apps. GetAdvice is the friendly voice-and-chat advisor built for exactly those people. But "people intimidated by AI" is a crowd, not a customer. If the launch guesses wrong about *who* they are and *why* they hesitate, every piece of marketing you build in lessons 18 through 23 is aimed at nobody.

Research is the cheapest work on a launch. Launching to the wrong audience is the most expensive mistake there is. You've been GetAdvice's feedback tester since day one — you know the app. This week you get to know its people.

---

## The work

### Step 1 — [You do] List five real people

Take ten minutes and write down five people you personally know who *could* use AI but don't — or who tried it once and backed away. An aunt who types questions into Google like full sentences. A coach who still prints schedules. A friend who says "AI is going to be huge" but has never opened a single AI app.

For each one, jot a single line: who they are, and your guess at why they hold back.

Those guesses matter — write them down before you talk to anyone. Research is only honest if you can compare what you *assumed* with what you *heard*.

### Step 2 — [You do] Write your interview questions yourself

Not MILO. You. If MILO writes your questions, you'll learn what MILO thinks is interesting, not what you need to know. Write 6–8 questions following three rules:

| Rule | Bad question | Good question |
| --- | --- | --- |
| Ask about the **past**, not the future | "Would you use an AI app?" | "Tell me about the last time you tried an AI tool. What happened?" |
| Ask **open**, don't lead | "Don't you find AI confusing?" | "What comes to mind when someone says 'AI'?" |
| Chase **feelings**, not features | "What features would you want?" | "What's the moment you gave up? What did that feel like?" |

People are terrible at predicting what they'll do and surprisingly honest about what they've done. Ask about last Tuesday, not about someday.

### Step 3 — [Ask MILO] Stress-test your questions

Now bring in your copilot — as a critic, not a ghostwriter:

```text
Here are the interview questions I wrote for people who feel intimidated
by AI tools. Don't rewrite them for me. For each question, tell me if
it's leading, closed, or vague — and explain why. I'll fix them myself.
```

Fix them yourself. Then run the prompt once more on the fixed set. Two rounds is plenty — perfect questions don't exist, and asked questions beat polished ones every time.

### Step 4 — [You do] Run three short interviews

Pick three people from your Step 1 list and talk to them. In person, on a call, over voice notes — whatever gets a real conversation. Ten minutes each is enough. Two habits separate good interviewers from bad ones:

1. **Follow the "why" trail.** When someone says "it just seems complicated," don't nod and move on. Ask "what specifically felt complicated?" The first answer is a headline; the third why is the truth.
2. **Let silence sit.** People fill quiet with the honest part.

Take messy notes — fragments, exact quotes, half sentences. Messy is fine; you have an AI teammate for exactly this. Save them to `marketing/research/interview-notes.md`.

⚠️ **Privacy rule — your repo is public.** First names or nicknames only. No last names, no phone numbers, no emails, nothing a stranger could use to identify your aunt. This is a real professional habit, not just politeness.

One more thing: your first interview will be a little awkward. A question will flop. You'll realize halfway through that you led the witness. Good — note it and adjust for interview two. Mistakes are part of the process; in research they're literally data.

### Step 5 — [Ask MILO] Find the patterns

Here's the prompt technique this lesson is really about. Feed MILO the raw material and ask for structure:

```text
Read marketing/research/interview-notes.md. These are raw notes from
three interviews with people who feel intimidated by AI tools. Find
patterns: things that show up in at least TWO of the three people.
For each pattern, quote the exact lines from my notes that support it.
No pattern without evidence.
```

That last line is doing heavy lifting. Notice the shape of this move — you'll reuse it for the rest of your life: **raw notes in, patterns out, evidence required.**

### Step 6 — [Ask MILO] Then challenge everything it said

Do not skip this step. It is the whole lesson.

Think of MILO's pattern-finding like a metal detector on a beach: it beeps at buried treasure *and* at bottle caps, with equal confidence. AI is genuinely great at synthesis — and it will also happily find a "pattern" in two coincidences, because finding patterns is what it does. Your job is to dig and check. So push back:

```text
Now argue against your own list. Which of these patterns has the
weakest evidence? Which one might I be seeing just because I expected
to see it? Be blunt.
```

And for any pattern you're not sure about:

```text
You said "[pattern]." Quote the exact line from my notes that supports
it. If the support is thin, say so.
```

Kill anything that doesn't survive. Three strong patterns beat seven wobbly ones. This is *always ask why*, graduated from a learning habit into a professional weapon — the teammates who get good at AI aren't the ones who prompt best, they're the ones who challenge best.

### Step 7 — [You do] Write two personas → `marketing/research/audience.md`

A persona is a character sheet for a real slice of your audience — specific enough that when someone asks "would Carmen understand this headline?", the whole team pictures the same person. Build two from your surviving patterns:

```markdown
# Who GetAdvice is for

## Persona 1: "Cautious Carmen"  ← invent your own name
- **Who:** one line — life situation, tech comfort
- **What they want:** what AI could actually do for their life
- **What scares them off:** in their own words, from your interviews
- **What would make them try an AI app:** the unlock
- **Real quote:** "…" — an actual line someone said to you

## Persona 2: ...

## What I assumed vs. what I heard
Two or three sentences. Where were your Step 1 guesses wrong?
```

Write these yourself, from your evidence. Then — and only then — ask MILO to review: `"Here are my two personas. Which claims are backed by my interview notes, and which did I invent?"` If a detail came from your imagination instead of an interview, cut it or mark it as a guess. The difference between research and fiction is the quote.

### Step 8 — [You do] Scan the competition

Open the App Store and search the phrases *your interviewees* would type — "AI assistant," "learn AI," "AI for beginners," or whatever language actually came up in Step 4. Pick **three** apps that overlap with GetAdvice's mission. Then actually use each one for ten minutes, imagining you're one of your two personas. Would Carmen make it past the first screen?

Take notes on each: first impression, what it does well, where your persona would get stuck or give up.

### Step 9 — [Ask MILO] Play devil's advocate

You know GetAdvice better than almost anyone — which makes you biased. Balance it:

```text
Here are my notes on three competitor apps, plus what I think makes
GetAdvice different: [your notes]. Play devil's advocate. For each
"difference" I claim, tell me why a customer might not care, or why a
competitor already covers it. Then ask me the questions a skeptical
customer would ask.
```

If a difference survives that beating, it's real — and it becomes ammunition for every lesson that follows.

### Step 10 — [You do] Write `marketing/research/competitors.md`

```markdown
# Competitor scan — 2026-07-XX

## App 1: <name>
- **What it is:** one line
- **What it does well:** at least two honest things
- **Where GetAdvice is different:** different, not "better" — be specific
- **One thing we could learn from it:** steal like a professional

## App 2: ...
## App 3: ...

## The gap
Two or three sentences: after seeing all three, what space is
GetAdvice standing in that none of them fill? Tie it to your personas —
which one is being ignored by everybody else?
```

The honesty rule: if you can't name two things a competitor genuinely does well, you haven't looked hard enough. A scan that just trashes the competition is useless to a real team — the point isn't to feel good, it's to see clearly.

---

## Ship it 🚀

Time to put your research where the team can use it. From your repo:

1. Make sure your three files are in place: `marketing/research/interview-notes.md`, `marketing/research/audience.md`, `marketing/research/competitors.md`.
2. Commit each deliverable with a message that says what it is:

```bash
git add marketing/research/
git commit -m "research: 2 personas from 3 interviews + honest 3-app competitor scan"
git push
```

Remember how this team works: **MILO reads your committed files automatically.** The files *are* the report — nobody will chase you for status. Update this week's journal (`marketing/journal/week-01.md` if you are still in your first week): add `audience.md, competitors.md` to the `shipped:` line and write a real `learned:` line. Unshipped research is just a diary.

---

## 🌟 Milestone

The rubric looks for **`marketing/research/audience.md`** and **`marketing/research/competitors.md`** in your repo — personas with real quotes, a competitor scan with honest strengths.

---

## Prove it

- [ ] You interviewed three real people and your notes use nicknames only — nothing identifying in a public repo
- [ ] At least one pattern got **cut** in Step 6 because it didn't survive your challenge
- [ ] Both personas contain a real quote a real person actually said
- [ ] Your competitor scan names at least two genuine strengths per app
- [ ] You can answer, out loud, in one sentence: *who is GetAdvice for, and why hasn't anyone built for them?*

## Next

You now know who the customer is, what scares them, and what everyone else sounds like. [Lesson 18 — Voice and Message](18-voice-and-message.md) is where it pays off: you'll take Carmen's own words and build the voice GetAdvice uses to talk to her.
