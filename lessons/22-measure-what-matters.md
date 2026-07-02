# Lesson 22 — Measure What Matters 📣

Look at what you have shipped in the Launch Track so far: audience research, a competitor map, a voice guide, App Store copy, a real landing page, a content calendar with posts, and a keyword list. The campaign machine is built. This lesson answers the question every marketer must eventually face, and most avoid: **is any of it actually working?**

---

## What you'll learn

- How to pick **one goal metric** for the whole campaign — and why ours is *people who try GetAdvice*
- What **supporting signals** are (visits, taps, store views) and how they line up into a funnel
- How **UTM links** work — think of them as name tags on doors
- The **experiment log** discipline: hypothesis → change → result → decision, one row per experiment
- How to spot **vanity metrics** before they eat your week

---

## Why this matters

GetAdvice exists for people who feel intimidated by AI. The launch is not graded on how busy the team looks — it is graded on whether more of those people actually open the app and try it. You have been GetAdvice's feedback tester since day one, so you already know what that first *try* feels like. Now your job is to help cause more of them.

Here is the career part. A junior teammate who says "I posted five things this week" is ordinary. A junior teammate who says "I ran an experiment, here is what moved the number, here is what I would do next" is rare — and that is exactly the habit this lesson installs. It is one file and one discipline, and it changes how everything you have built gets judged: by evidence instead of by vibes.

---

## One number to rule the campaign

A campaign without a goal metric is a road trip without a destination — you can drive fast all day and end up nowhere.

Our goal metric is simple: **people who try GetAdvice.** Not people who liked a post. Not people who visited a page. People who actually got the app and opened it. Everything else you measure exists only to serve that number.

Everything else is a **supporting signal**. Picture the path one person walks:

```text
sees your post  →  visits the landing page  →  taps "Get the app"  →  views the store page  →  TRIES GETADVICE
```

That path is called a **funnel**, because at every step some people leak out. Supporting signals — visits, taps, store views — are the road signs along the way. They never replace the destination, but they tell you *where* people got lost. If lots of people visit your landing page and almost nobody taps the button, the page is the leak. If lots of people tap and few try, the leak is further down. Signals are for diagnosis. The goal metric is for judgment.

One honest note: you will be able to see some signals yourself (views on your own posts, visits and taps on your landing page), while others live with the team. That is normal on a real team — which is exactly why the next section matters.

---

## UTM links: name tags on doors

Imagine the landing page is a building with one big room and five doors. People stream in all day — but if every door looks the same from the inside, you have no idea which door is doing the work. Was it your video? The group chat? The poster in the hallway?

A **UTM link** fixes that by hanging a name tag on each door. It is nothing magical — just extra text stuck on the end of a normal link:

```text
https://getadviceapp.com/?utm_source=youtube&utm_medium=video&utm_campaign=launch-week
```

The page that loads is identical. But the visit arrives wearing a name tag that says exactly which door it came through. The three tags you will use:

| Tag | Question it answers | Example |
| --- | --- | --- |
| `utm_source` | Which place? | `youtube`, `instagram`, `groupchat` |
| `utm_medium` | Which kind of thing? | `video`, `post`, `bio-link` |
| `utm_campaign` | Which effort? | `launch-week` |

Two rules, and they are house rules for the whole launch:

1. **Never post a naked link.** An untagged link produces anonymous visitors, and anonymous visitors teach you nothing.
2. **Name things once, then never improvise.** Lowercase, hyphens, same words every time. `launch-week` and `Launch_Week` look like two different campaigns to a counting machine, and machines do not guess.

You do not need anyone's permission to make a UTM link — it is just text. But the tags are how *your* work stays visible inside the *team's* numbers. Tagged links are how a junior teammate's experiments show up with their name on them.

---

## The experiment log

Here is the discipline that separates marketing from noise. Every change you make to the campaign gets written down **before** you make it, as an experiment with four parts:

| Part | What it is | The test of a good one |
| --- | --- | --- |
| **Hypothesis** | Your prediction, with a number and a deadline | Could it turn out to be *wrong*? |
| **Change** | The one thing you did | One thing. Not three. |
| **Result** | What the numbers actually said | Filled in later. Never invented. |
| **Decision** | Keep, kill, or iterate | One word plus one sentence of why |

One row per experiment. That is the whole system.

The hypothesis is the part beginners fumble, so write yours in this shape: *"If I [change], then [signal or goal metric] will [move by how much] within [how long], because [reason from your audience research]."* If your hypothesis cannot be wrong, it is not a hypothesis — it is a wish.

And hear this clearly, because it is the same principle that has followed you since Level 1: **mistakes are part of the process.** An experiment that fails and gets an honest *kill* is a success — you bought real knowledge with one week instead of five. The only failed experiment is the one whose result you fudged or never wrote down.

Your log lives at `marketing/measure/experiment-log.md`, and it starts with the same front-matter block as your journal — because MILO reads these files automatically. The front-matter IS the report. Nobody will chase you for status; the file speaks for you.

```markdown
---
week: N
focus: <one line>
shipped: <comma-separated deliverables>
learned: <one line>
blocked: <one line or "nothing">
feedback-for-getadvice: <one line or "none">
---

# GetAdvice experiment log

Goal metric: people who try GetAdvice.

| # | Date | Hypothesis | Change | Result | Decision |
| --- | --- | --- | --- | --- | --- |
| 1 | ... | If I..., then..., because... | ... | — | — |
```

Leave **Result** and **Decision** as `—` until the deadline passes. An empty cell is honest. An invented number is worse than useless — it poisons every decision built on top of it.

---

## Beware the vanity metrics

Some numbers go up and feel wonderful and mean almost nothing. Likes. Impressions. Follower counts. These are **vanity metrics**, and they are dangerous precisely because they feel like progress.

Think of it like applause outside a shop. Lovely sound. But the shop lives on people who walk through the door — and a like costs the liker half a second and commits them to nothing.

Here is the test, and it is just *always ask why* wearing a lab coat: **"If this number doubled tomorrow, would more people try GetAdvice?"** If you cannot draw the line from that number to the goal metric, the number is decoration. Enjoy it for a second, then look away.

---

## Do it now

1. **[You do]** Pick one real post from your `marketing/content/posts/` folder — one you have shipped or are about to ship. On paper or in a scratch file, sketch its funnel: where someone sees it, where the link takes them, what they tap next, where they end up. Mark the step where you honestly suspect people leak out.

2. **[Ask MILO]**

   ```text
   I'm the junior growth teammate on the GetAdvice launch. My goal metric
   is "people who try the app." Here is the funnel for one of my posts:
   [paste your sketch]. Ask me questions, one at a time, until I can name
   which supporting signal I'd watch at each step — then tell me which of
   my signals is closest to becoming a vanity metric, and why.
   ```

3. **[You do]** Build UTM links for the two channels where your posts actually live. Same base URL, same `utm_campaign`, honest `utm_source` and `utm_medium` for each. Write them into the bottom of your experiment log under a `## Links` heading so you never retype them by hand.

4. **[Ask MILO]**

   ```text
   Here are my two UTM links: [paste them]. Check them like a picky
   reviewer: naming consistency, lowercase, hyphens, and whether source /
   medium / campaign are used for the right jobs. Don't rewrite them —
   point at problems and let me fix them myself.
   ```

5. **[You do]** Create `marketing/measure/experiment-log.md` using the template above — a ready-to-copy version lives at `templates/experiment-log-template.md`. Front-matter first, goal metric line, table, and **row #1 — your first real experiment**. Write the hypothesis yourself, in your own words, before any AI sees it. Fill in Hypothesis and Change; leave Result and Decision as `—`.

6. **[Ask MILO]**

   ```text
   Here is the first hypothesis in my experiment log: [paste row #1].
   Attack it. Is it falsifiable? Does it name a number and a deadline?
   Is the change really ONE change? Is the "because" grounded in my
   audience research in marketing/research/audience.md, or is it a wish?
   Interrogate me until the row would survive a skeptical teammate.
   ```

7. **[You do]** Open this week's journal in `marketing/journal/`. From now on, every weekly entry gets a `## The numbers` section right under the front-matter: your goal-metric news if you have any, the supporting signals you can actually see, and one sentence about what they mean. If you have no data yet, write "no data yet" — that is a real measurement too. Small and true beats big and fuzzy, every single week.

---

## Ship it 🚀

Commit the real deliverables to the real paths — clear message, nothing clever:

```bash
git add marketing/measure/experiment-log.md marketing/journal/
git commit -m "measure: experiment log with first experiment planned, journal now reports numbers"
git push
```

Remember how this course works: MILO reads these files automatically. The front-matter is the report, the table is the evidence, and nobody will ever chase you for status — your repo answers before anyone has to ask.

---

## 🌟 Milestone

The rubric looks for **`marketing/measure/experiment-log.md`** — front-matter block on top, goal metric stated, and row #1 planned with a falsifiable hypothesis and a single change, with Result and Decision honestly left blank.

---

## Next

Next lesson, you pull every file in `marketing/` into one launch plan — and then we launch for real, in [Lesson 23 — Capstone: Launch GetAdvice](23-capstone-launch-getadvice.md). Your experiment log is about to become the most-read file you own.
