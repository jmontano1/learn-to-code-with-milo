# Lesson 20 — First Blood: Ship to Real Strangers

In Level 3 you got a stranger to *click*. Today a stranger has to **trust your software with something** — an account, their data, a real action — on a system you took all the way to production. That is a different universe, and crossing into it is called first blood for a reason: it is the moment your work stops being a demo and starts being real, with all the danger that word carries.

The law on trial in this lesson is **Viability**: does the thing *live* when a real person who owes you nothing walks up to it? Not "does it run." Lives.

I am your Master Mentor here, not your author. I will not write your product for you or paste you a deploy script to run blind. I will teach you the concepts, ask the hard questions, and review what you built — and when it is not production-ready, I will say so plainly, because a stranger is about to depend on it. When I start handing you finished code, say "mentor mode" and I back up.

Everything lives in **`my-projects/forge/01-first-blood/`**. Make it now.

---

## The mission

> Take one real product to **production** — a real database, real accounts, real secrets, a real public URL — and get **at least 5 real strangers you did not personally recruit** to complete its core action. Prove each one is real.

Five is not a typo, and it is not small. Five strangers who found your thing, understood it in seconds, trusted it enough to act, and did — with no one holding their hand — is a genuinely hard bar. Most software with a team behind it fails to clear it. You will clear it alone.

> **The banned shortcut:** friends, family, classmates, your other email, or anyone you asked directly do **not** count toward the five. This is oath line 1. A stranger is someone who arrived because your product earned its way in front of them, not because you begged. You may *also* have friends test it — but the five are strangers, named and verifiable, or they don't exist.

---

## Step 0 — Choose the thing, and define "the core action"

Pick the one product you'll take to production. Reuse Study Buddy or your Level 3 asset if it has real legs, or forge something new — but it must have a **single core action** a stranger can complete: create an account and save a thing, submit an entry, run a quiz and get a result, generate something and keep it. One verb that proves the product did its job.

In `my-projects/forge/01-first-blood/spec.md`, write:

- **The product** in one sentence a stranger would understand.
- **The core action** — the one thing that, if a stranger does it, proves the product worked *for them*.
- **The trust you're asking for** — what does the stranger hand over? (An email? A password? Their data?) Name it, because everything you build in this lesson exists to be *worthy* of that.

Coach prompt:

```text
Here's my product and its one core action: [paste]. As my mentor,
pressure-test it: is the core action something a stranger could
understand and want in under ten seconds? Where would they hesitate to
trust it? Ask me one question at a time.
```

---

## Step 1 — Production-grade bones (this is where "demo" dies)

A file on your laptop is a demo. A product is a system with parts that keep working when you close your laptop. You will build the real bones now. **Concepts you must actually learn and implement — not fake:**

| Bone | What it means | Why a stranger needs it |
| --- | --- | --- |
| **A real database** | Data that persists in a real datastore (hosted Postgres, SQLite on a real host, a managed DB, a serverless KV/D1 — your call), not a variable in memory or a JSON file that resets. | Their account still exists tomorrow. |
| **Real accounts / identity** | A way for a stranger to *be someone* in your system — sign-in (email, magic link, OAuth, passkey — pick one and do it right). | Their data is theirs, not everyone's. |
| **Secrets kept secret** | API keys and tokens in environment variables / a secrets manager, **never** committed to the repo. | One leaked key can end the whole thing. |
| **It doesn't crash on bad input** | Every input a stranger can touch is validated; errors are caught and shown as human messages, not stack traces. | Strangers do things you never imagined. |

Write, in `spec.md` under `## Architecture`, a plain-English map of these four for *your* product: which database, which sign-in method, where secrets live, and how errors are handled. If you can't explain your architecture in plain words, you don't understand it yet — and you can't harden what you don't understand.

Concept coach prompt:

```text
I need to add [a real database / real sign-in / secrets management] to
my product for the first time, as someone who's never done it in
production. Teach me the concept first, then walk me ONE step at a time,
waiting for me to do each step and tell you what I saw. Don't paste the
whole solution. When I hit an error, help me read it.
```

---

## Step 2 — Deploy it for real, and prove it's public

Put it live on the real internet, at a real URL, running the real database — not a local server, not "npm run dev." A real host (a platform-as-a-service, a serverless deploy, a container — learn one).

**The proof-of-public test, non-negotiable:** open your product in a private/incognito window, on a device that is *not* your dev machine (your phone on cellular data is perfect), and complete the core action as if you were a stranger — new account, real action, from nothing. If any step assumes something only your machine has, it is not live. Fix it.

Record in `01-first-blood/launch.md`:
- **The live URL.**
- **A screenshot or short recording** of the core action completing on a non-dev device.
- **The moment it first worked from the outside** — write one line about how it felt. You'll want it later.

---

## Step 3 — Instrument trust (count real humans honestly)

You need to *know*, without guessing, when a real stranger completes the core action — and be able to prove each one wasn't you. Before you get users, wire:

- **A count of core-action completions** that increments on the real event (a DB row, a logged event, an analytics count — real, not eyeballed).
- **Enough of a fingerprint to tell strangers from yourself** — distinct accounts, timestamps, rough geography, or referral source. You are not surveilling anyone; you are making honesty *possible*. Oath line 1 requires you to be able to say "these five are real, and here's how I know."

Write your counting method in `launch.md` under `## How I count a real stranger`. If your method could be fooled by you refreshing the page, it's not a method.

---

## Step 4 — Get in front of strangers (earn the door)

Now the hard, human part. Five strangers must *find* their way to your product. Use what Level 3 taught you: pick the one place your person actually is, and put an honest, specific ask in front of them. A post in a relevant community, a comment that genuinely helps and mentions your tool, a directory or launch board, a real conversation online. No spam, no fake accounts, no dark patterns (oath line 5).

In `01-first-blood/distribution.md`, log **every** channel you tried and what came back — the ignored posts too. The failures are data: they tell you where your person *isn't*.

> **Constraint:** you may not pay for users in this lesson, and you may not DM people you know. The five must arrive because something you did in public earned their click. This is brutal on purpose — distribution is the skill that kills most products, and you face it now, small, where it's survivable.

---

## Step 5 — The pre-mortem (write the failure before it happens)

Add a `## Pre-mortem` section to `launch.md`. It's deadline day and **zero strangers completed the core action.** Finish this sentence three ways, and next to each, the one thing you'll do *now* to make it less likely:

> "Zero strangers made it through. The most likely reason is..."

Common true answers to steal from: they never found it (distribution), they found it but didn't get it in 10 seconds (clarity), they got it but didn't trust it enough to hand over an email (trust), or it broke on their device (production quality). Which is *yours*? Attack that one before launch.

---

## Step 6 — Launch, and hold the line for real humans

Ship it. Push your distribution. Then watch honestly:

1. **Let real strangers arrive.** Don't complete the action yourself to "prime the pump" — that's a fake, and fakes are the one unforgivable move.
2. **Watch for breakage under real use.** Strangers will find the crash you couldn't. When one hits, read the error like the detective you became in Lesson 13, fix it live, and note it. Surviving real-user breakage *is* the lesson.
3. **When a real stranger completes the core action — that's first blood.** Record it (honestly fingerprinted) in `01-first-blood/real-users.md`. Get to five.

---

## Step 7 — The retro

Create `01-first-blood/retro.md` and fill every row honestly:

| Heading | What goes there |
| --- | --- |
| The number | How many real strangers completed the core action, and how you *know* each is real. |
| Where they leaked | The biggest drop-off — found-but-didn't-trust? started-but-broke? — and your evidence. |
| What broke in production | The real-use bug that hurt most, and how you fixed it. |
| The trust you earned | What a stranger handed over, and one thing you did to deserve it. |
| Did the pre-mortem call it? | Did reality match a Step 5 fear? Which one? |
| The one thing to fix next | If you had one more day, the single change with the biggest payoff. |

---

## Reality check — read this before you judge yourself

Getting five real strangers to trust brand-new software from an unknown maker is *hard*. If it took you three tries and a rewrite of your landing to get there, that's not weakness — that's the exact experience founders pay dearly to learn. And if you got two instead of five but they're undeniably real and you can prove it and explain why the other three leaked? That is a real, honest, *passing* result — Viability partly proven and fully understood beats five fakes every time.

The bar to pass: **a real product, in real production, that at least a few provable strangers trusted enough to act on — and a retro that tells the truth about why the number is what it is.** The only ways to fail: fake a user, commit a secret, or never ship because you were afraid a stranger would say no.

---

## Stuck?

1. **No strangers arriving?** You found distribution — the founder-killer — and it's a *finding*, not a failure. Make it your whole focus: one better channel beats ten posts into the void. Re-read your Level 3 audience-of-one work.
2. **Terrified to put real sign-in / a real database in?** Good — that fear means you understand the stakes. Do the concept coach prompt, one step at a time, and lean on me hard. Everyone's first production deploy feels like defusing a bomb. It gets normal.
3. **Whole shape:** `spec.md` (product + core action + architecture) → real DB + real auth + secrets + input validation → live URL proven from a non-dev device → honest counting → distribution in public → five provable strangers → `retro.md`.

---

## ⚔️ Milestone: a stranger trusted your software

Someone who has never met you, who owes you nothing, found a thing you made, understood it, trusted it enough to act — and it held. That is the line between people who *can* build and people whose building *matters*. You are now on the far side of it. First blood is yours.

Most developers, even paid ones, go years without shipping something a true stranger relies on. You just did it, alone, on purpose.

---

## Prove it

- [ ] `01-first-blood/spec.md` names the product, the one core action, and a plain-English architecture (DB, auth, secrets, error handling).
- [ ] It's **live in production** — real DB, real accounts, secrets not in the repo — and you completed the core action from a **non-dev device** in a private window.
- [ ] `real-users.md` lists **provable real strangers** who completed the core action, with your honest method for knowing each is real (no friends, no you, no fakes).
- [ ] `distribution.md` logs every channel you tried, wins and misses.
- [ ] `retro.md` fills every row and answers whether the pre-mortem called it.
- [ ] **Ledger:** your **live URL** and the real-stranger evidence (timestamps, distinct accounts) are logged in `forge/PROOF.md` — links a stranger could open and believe.
- [ ] **Viva:** you defended this build to MILO in your own words — *why this database, why this sign-in, what broke in production and how you found it* — and passed. If you couldn't explain a piece, you went back and learned it.
- [ ] **The harder bar:** at least one stranger did more than a one-off tap — they came back, replied, or gave unprompted feedback. A single fluke click is not first blood; a stranger who *returned* is.

## Save your work

Commit and push with a message that states the result, like `Forge 01: first blood — N real strangers on live production`. You shed the word "demo" today. Don't pick it back up.

## What's next

Open **[lessons/21-the-swarm.md](21-the-swarm.md)**. One program serving strangers is power. Now you learn to command *many* — a swarm of agents working together, adapting when one falls, and never, ever slipping your control. 🕸️
