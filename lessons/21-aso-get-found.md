# Lesson 21 — ASO: How Apps Get Found 📣

You've studied the audience, found the voice, written the copy, and built a landing page. The work is good — but good work that nobody finds might as well not exist. Today you learn how people actually discover apps, and you'll do real keyword research that feeds directly into the GetAdvice launch.

---

## What you'll learn

- How people really search inside the App Store (it's not like Google)
- How to brainstorm keywords with MILO, then cluster them into themes
- How to judge every keyword on two honest dials: **relevance** and **competition**
- How to work your best keywords into the copy from [lesson 18](18-voice-and-message.md) — without wrecking it
- How to storyboard the 5 screenshots that tell the GetAdvice story

This whole field has a name: **ASO — App Store Optimization**. It's the app-store cousin of SEO, and it's a genuine job skill.

---

## Why this matters

A huge share of app downloads start with a search typed straight into the App Store. And here's the thing about GetAdvice's audience: people who feel intimidated by AI have **never heard of GetAdvice**. Nobody types our name. They type their problem — "learn ai", "how to use ai", "ai for beginners" — and the App Store shows them a list.

If our listing doesn't speak the exact words those people type, we are invisible to the very people we built the app for. Your research today is not homework. It's the keyword map the real launch will lean on.

---

## How App Store search actually works (the honest version)

Before we optimize anything, let's be honest about the machine we're dealing with.

**People type problems, not brand names.** They're on a phone, thumb-typing two or three words, and autocomplete finishes their sentence. Short, plain, problem-shaped phrases win.

**Apple only searches certain fields.** The app **name** (30 characters max), the **subtitle** (30 characters max), and a hidden **keyword field** (100 characters, comma-separated) that developers fill in behind the scenes. The long description? Apple doesn't search it. The description exists to convince a *human* who already found you. That one fact should change how you write everything.

**There are no tricks.** Anyone who promises a hack to "rank #1 overnight" is selling something. ASO is slow, honest work: pick words real people type, where you actually have a shot, and say them naturally in your copy.

**Small apps can't win giant words.** GetAdvice will not outrank the biggest apps in the world for the word "AI" — and chasing that would be a waste of a launch. Think of it like a crowded farmers market: the stand that shouts "FOOD!" gets ignored, but the stand with a sign that says "fresh mango with chili, sliced while you wait" gets a line. Specific beats loud.

---

## The two dials: relevance and competition

Every keyword gets judged on two questions, in plain terms:

| Dial | The question it answers | How we estimate it for free |
|------|------------------------|------------------------------|
| **Relevance** | Would the person typing this be *happy* to land on GetAdvice? | Check it against `marketing/research/audience.md`. If it doesn't sound like our person, it's low. |
| **Competition** | Who already owns this search? | Type it into the App Store on your phone and look at the top 5 results with your own eyes. |

The honest rules:

- **High relevance + low competition = gold.** These are the small ponds where we can be the biggest fish.
- **High traffic + low relevance = useless.** Even if we somehow ranked, we'd attract people who open the app once, feel misled, and leave.
- **Relevance always wins the tie.** Ten downloads from people who needed exactly us beat a thousand from people who didn't.

We don't have expensive ASO tools, and we don't need them to start. The App Store's own search bar — autocomplete suggestions and the top results — is real data, free, sitting in your pocket.

---

## Do the research

Work through these in order. Notice the rhythm: you think first, then MILO helps. That order matters.

1. **[You do]** Reread `marketing/research/audience.md` and `marketing/research/competitors.md`. Then close them and write **10 search phrases yourself**, in the words our audience would type — not the words we use on the team. Write them before you ask MILO anything. Your own first pass is the whole point; if MILO goes first, you'll just nod along at its list.

2. **[Ask MILO]** Now widen the pool:

   ```text
   Read marketing/research/audience.md and marketing/research/competitors.md.
   Brainstorm 30 phrases our audience might type into the App Store search
   bar when they have the problem GetAdvice solves. Use their words, not
   marketing words. Include long, specific phrases, not just short ones.
   Don't evaluate them yet — just brainstorm. Here are 10 I wrote myself,
   so avoid repeating them: [paste your 10]
   ```

3. **[You do]** Merge your 10 and MILO's 30 into one list, then **cluster them into 4–6 themes** — groups like "learning AI from zero," "fear and confidence," "everyday AI help," "voice assistant." Naming the clusters yourself forces you to see the patterns.

4. **[Ask MILO]** Get a plain-terms evaluation:

   ```text
   Here are my keyword clusters: [paste them]. For each keyword, rate
   Relevance to GetAdvice (High/Medium/Low) and likely Competition
   (High/Medium/Low), and explain each rating in one plain sentence a
   junior teammate could check. GetAdvice is a friendly iOS app that
   helps everyday people learn and use AI with confidence, with a voice
   and chat advisor. Flag any keyword where you're guessing.
   ```

   Notice that last line. MILO can't see Apple's private search data any more than we can — asking it to flag its guesses keeps the research honest.

5. **[You do]** Field research. Open the App Store on your phone and type your 15 most promising keywords, one at a time. For each, write down two things: what **autocomplete** suggested (those suggestions are real searches by real people), and **which apps fill the top 5**. Huge household names in every slot? High competition. A mixed bag of small apps? There's room.

6. **[Ask MILO]** When a result surprises you, don't just record it — ask why:

   ```text
   When I search "[keyword]" in the App Store, the top results are
   [list them]. Why do you think these apps rank here? What does that
   tell us about whether GetAdvice could realistically compete on this
   phrase?
   ```

   Always ask why. A ranking you understand teaches you something; a ranking you just copy down teaches you nothing.

7. **[You do]** Pick your **shortlist: 10–15 keywords**, each with a one-line reason. Some of your early favorites won't survive the field research. Good — crossing out your own ideas is the research working, not the research failing. Mistakes are part of the process.

---

## Map keywords into the copy — for humans first

Open `marketing/voice/app-store-copy.md` from [lesson 18](18-voice-and-message.md). Your job now is to check where your shortlist words live in that copy — and to fix gaps *without breaking the voice you built*.

The one unbreakable rule: **never keyword-stuff.** Look at the difference:

- ❌ Stuffed subtitle: `AI chat learn assistant advisor help app` — robot soup. No human talks like this, Apple's reviewers dislike it, and the person we care about — someone already nervous about AI — bounces instantly.
- ✅ Natural subtitle: `Learn AI with a friendly guide` — a real sentence that happens to carry real search words.

The test is simple: **read it out loud.** If you'd be embarrassed to say it to a person, it doesn't ship.

8. **[You do]** Go through the copy line by line. Mark where each shortlist keyword already appears naturally, and where a high-value keyword has no home. Remember what Apple actually searches: the **title and subtitle carry the most weight** — those 60 characters are prime real estate. Then draft a proposed **keyword field**: your best shortlist words, comma-separated, 100 characters or fewer, no words already used in the title or subtitle (Apple doesn't reward repeats).

9. **[Ask MILO]** Pressure-test your mapping:

   ```text
   Here is our App Store copy from marketing/voice/app-store-copy.md and
   my keyword shortlist. Check my mapping: does the title + subtitle carry
   our strongest keywords naturally? Is anything starting to sound stuffed
   or robotic? Read every line as a nervous first-time user would. Suggest
   improvements, but keep the voice from marketing/voice/voice-guide.md.
   ```

---

## Storyboard the 5 screenshots

Screenshots are the most-viewed part of any listing, and the first two or three appear right in the search results — before anyone taps anything. They are not documentation. They're a five-panel poster that tells one story.

10. **[You do]** In markdown (described, not designed — no image tools today), storyboard 5 screenshots. For each one write: **what's on screen**, the short **caption text** overlaid on it, and **what it should make the viewer feel**. A story arc that fits GetAdvice:

- **Screenshot 1 — The promise.** The single biggest benefit, instantly clear. This one does the heavy lifting in search results.
- **Screenshot 2 — The voice advisor.** Show the friendliest thing we have: you can just *talk* to it.
- **Screenshot 3 — The chat.** A real, warm exchange that proves it's judgment-free.
- **Screenshot 4 — The transformation.** What life looks like once AI stops being scary — the moment of confidence.
- **Screenshot 5 — The invitation.** A simple, warm call to start.

No invented ratings, no made-up user counts, no fake awards. The story is strong enough told honestly.

---

## Ship it 🚀

Create `marketing/aso/keywords.md` in your repo with this structure:

```markdown
# GetAdvice — ASO Keyword Research

## 1. Brainstorm
(the full merged list — yours + MILO's)

## 2. Clusters
(4–6 named themes, keywords under each)

## 3. Evaluation
| Keyword | Relevance | Competition | What I saw in the App Store | Verdict |
|---------|-----------|-------------|------------------------------|---------|

## 4. Shortlist
(10–15 keywords, one-line reason each)

## 5. Copy mapping
- Title (≤30 chars):
- Subtitle (≤30 chars):
- Proposed keyword field (≤100 chars, comma-separated):
- Description notes: (where shortlist words appear naturally)

## 6. Screenshot storyboard
(5 screenshots: what's on screen, caption text, what it makes the viewer feel)
```

Fill it with your real research, then commit it:

```bash
git add marketing/aso/keywords.md
git commit -m "aso: keyword research, copy mapping, and screenshot storyboard"
git push
```

Remember how this team works: **MILO reads these files automatically.** The committed file *is* your report — nobody will chase you for status. And if you're closing out your week, log it in `marketing/journal/week-NN.md` with the usual front-matter block so your progress and any GetAdvice feedback flow through.

One more honest note: this file is a living document. Some of these keywords will turn out to be wrong once the app is in front of real searches, and you'll come back and revise. That's not failure — that's the job.

---

## 🌟 Milestone

The rubric looks for exactly one file: **`marketing/aso/keywords.md`** — committed and pushed, with all six sections filled in from your own research.

---

## Next

You've made a set of bets: these keywords, this copy, these screenshots. But marketing bets are only opinions until you measure them. In [Lesson 22 — Measure What Matters](22-measure-what-matters.md), you learn to run small honest experiments and keep score — so the launch runs on evidence, not vibes.
