# Lesson 16 — Level 3: The Launch Track 📣

Lesson 15 told you there was no lesson 16. That was true — right up until you shipped the capstone. You took a complaint about a real app and turned it into a repro, a hypothesis, a spec, and a working prototype, and somewhere in the middle of that you stopped being a student who practices and became a teammate who contributes.

Level 3 exists because you earned it. Welcome to the Launch Track.

---

## What you'll learn

- What marketing actually is — the honest definition, not the sleazy one
- What a launch campaign is, and the parts it is made of
- The Level 3 weekly rhythm, including your **automatic standup**
- How to set up your `marketing/` workspace and put it under git

---

## Why this matters

Everything you built in Levels 1 and 2 was practice — good practice, real skills, but practice. Level 3 is not practice.

**GetAdvice is launching.** The friendly iOS app you have been testing since day one — the voice-and-chat advisor that helps everyday people learn and use AI with confidence — is making its push to reach the people it was built for. A launch needs builders, and it also needs someone doing the work of *finding those people and talking to them*. That someone now includes you.

You are joining the launch as a **junior growth teammate**. Not pretend. The research you write, the words you draft, the page you build, the experiments you log — they feed a real campaign for a real product made by a real company ([JM Automated Solutions](https://jmautomated.com), the maker of [GetAdvice](https://getadviceapp.com)). Some of your work will ship. Some of it will teach the team something. Both count.

---

## What marketing actually is

Marketing has a terrible reputation, and it earned it. Most people hear the word and picture someone loud, pushy, and slightly dishonest.

Forget that person. Here is the real definition, and it is the foundation of everything in Level 3:

> **Marketing is finding the people a product genuinely helps, and telling them the truth well.**

Think of it like this: somewhere out there is a person who feels a little behind because everyone around them suddenly "uses AI" — and they are too embarrassed to ask where to even start. GetAdvice was built *for that person*. If they never hear it exists, the app failed them without ever getting a chance. Marketing is the bridge between a product that can help and the person it can help.

Notice the two halves of the definition, because the whole track is built on them:

| Half | The question it asks | The skill behind it |
| --- | --- | --- |
| **Finding the people** | Who is this for? Where are they? What words do *they* use? | Research — the detective skills from Lesson 13, pointed at humans instead of bugs |
| **Telling the truth well** | How do we say it so they actually hear it? | Writing — clear, honest, in a voice that sounds like a friend, not a billboard |

"The truth well" is doing a lot of work in that sentence. *The truth*, because lying works exactly once and then you have no customer and no reputation. *Well*, because a true sentence nobody reads helps nobody. You will get good at both.

---

## What a launch campaign is

A **launch campaign** is a focused, time-boxed push where all of that finding and telling points at one moment: the launch. Instead of talking about the product occasionally and randomly, a team lines everything up — who we are for, how we sound, where we send people, what we publish, how we measure — so it lands together.

Here is the anatomy of a campaign, which is also a map of Level 3. Every part gets its own home in your workspace:

| Campaign part | The question it answers | Where yours will live |
| --- | --- | --- |
| Audience & competitor research | Who are we for, and who else is talking to them? | `marketing/research/` |
| Voice & copy | How do we sound? What do we say on the App Store? | `marketing/voice/` |
| Landing page | Where do we send people? (You'll build it — real HTML) | `marketing/landing/` |
| Content | What do we publish, and when? | `marketing/content/` |
| App Store keywords (ASO) | What do people type when they search for help like ours? | `marketing/aso/` |
| Measurement | What actually worked? | `marketing/measure/` |
| The launch itself | The plan going in, and the honest look back after | `marketing/launch/` |
| Your journal | What did I do, learn, and hit a wall on this week? | `marketing/journal/` |

One thing to know before you start: in marketing, most experiments *don't* work. A post falls flat. A headline you loved gets ignored. On this track, that is not failure — a failed experiment that you measured and wrote down is **data**, and it is worth more than a success you can't explain. Mistakes are part of the process here, same as they were when your JavaScript threw errors. The `measure/` folder exists precisely because of this.

---

## The weekly rhythm — your automatic standup

Real teams run on a rhythm called a **standup**: a short, regular check-in where each person says what they did, what they learned, and what is blocking them. It keeps everyone honest and nobody surprised.

Level 3 runs on a weekly version, and yours is *written*. Every week has two duties:

1. **The work** — whatever that week's lesson ships.
2. **One journal entry** — a file at `marketing/journal/week-NN.md` (`week-01.md`, `week-02.md`, and so on).

Every journal entry **must start** with this exact block:

```text
---
week: N
focus: <one line>
shipped: <comma-separated deliverables>
learned: <one line>
blocked: <one line or "nothing">
feedback-for-getadvice: <one line or "none">
---
```

That block is called **front-matter**, and it is not decoration. MILO reads your committed files automatically — **the front-matter IS your status report**. Nobody will message you asking "how's it going?" Nobody will chase you. If it's in the journal, the team knows. If it isn't, it didn't happen. That is how real remote teams work, and it is a professional superpower: people learn they can trust your written word.

Line by line:

- **week** — the number. `1` for this week.
- **focus** — what the week was about, one line.
- **shipped** — the deliverables you actually committed, separated by commas.
- **learned** — the one thing you'd tell a friend you figured out.
- **blocked** — what's in your way, or the honest word `nothing`.
- **feedback-for-getadvice** — you've been GetAdvice's tester since day one; that doesn't stop now. Anything you noticed, or `none`.

Below the closing `---` you can write as much or as little as you like, in your own words. The front-matter is for the machine; the rest is for you.

---

## Build your workspace

Time to set up the office. Numbered steps, and you know the drill by now — you do the doing.

1. **[You do]** In your repo, create the `marketing/` folder with this tree inside it:

   ```text
   marketing/
   ├── research/
   ├── voice/
   ├── landing/
   ├── content/
   │   └── posts/
   ├── aso/
   ├── measure/
   ├── journal/
   └── launch/
   ```

2. **[Ask MILO]** Before you commit anything, make sure you could defend this structure to a teammate. Paste this:

   ```text
   I'm starting Level 3 of the Launch Track and I just created my
   marketing/ workspace: research, voice, landing, content/posts, aso,
   measure, journal, launch. Don't lecture me — quiz me, one folder at
   a time: ask what I think belongs in it and why a launch campaign
   needs it. Correct me where I'm off.
   ```

   Always ask why. A folder you can't explain is a folder you'll misuse later.

3. **[You do]** Run `git status`. Look carefully: your shiny new folders are *not there*. Git is acting like you did nothing. You've hit a real git behavior that confuses professionals — don't fix it yet.

4. **[Ask MILO]** Investigate before you patch:

   ```text
   I created several empty folders and git status doesn't show them at
   all. Why does git track files but not folders — and what's the
   standard trick teams use to keep an empty folder in a repo?
   ```

5. **[You do]** Apply what you just learned so every folder survives the commit (you'll have met a tiny file whose whole job is to exist). Then write `marketing/README.md` yourself — three to five sentences, your own words, no copying from this lesson: what this workspace is, and what it has to do with GetAdvice's launch. Write it yourself; this README is the first thing a future teammate will read, and it should sound like you.

6. **[You do]** Copy `templates/journal-template.md` to `marketing/journal/week-01.md` and fill in every front-matter line for real. For `shipped`, this week that's your marketing workspace and this journal entry. For `learned`, one honest line — maybe the git-and-empty-folders thing, maybe what surprised you about the definition of marketing. If nothing is blocking you, say `nothing`. If you noticed anything in GetAdvice lately, this is the line that carries it to the team.

7. **[Ask MILO]** Get a format check — format only:

   ```text
   Here is my marketing/journal/week-01.md. Check ONLY that the
   front-matter block is exactly the required format — starts the file,
   correct six keys in order, one line each. Do not rewrite my words.
   ```

---

## Ship it 🚀

A workspace that only exists on your machine doesn't exist. Ship it:

```bash
git add marketing/
git commit -m "level 3 kickoff: marketing workspace + week-01 journal"
git push
```

And set the habit now, because it *is* the job from here on: **every Level 3 deliverable gets committed with a clear message the day you finish it.** The commit is the handoff. MILO reads what you push; your journal front-matter is the standup; nobody will ever chase you for status. Quiet, consistent shipping is what trust is made of.

---

## 🌟 Milestone: you're on the launch team

The rubric looks for one file: **`marketing/journal/week-01.md`** — committed and pushed, with the front-matter block starting the file. When it's there, week one of the real campaign is on the books, and your name is on it.

---

## Next

Every campaign starts with the same question: *who is this actually for?* In [Lesson 17 — Know the Customer](17-know-the-customer-ai-research.md) you become a detective again — this time hunting people, not bugs — and ship your first research deliverable: `marketing/research/audience.md`.
