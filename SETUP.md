---
title: Setup
parent: Reference
nav_order: 3
---
# Setup — getting started 🛠️

This is a one-time setup to get you into the classroom.
After this, you mostly talk to **MILO**. You do these steps once.

> The big picture: **MILO** (Modular Intelligent Learning Orchestrator) is the tutor. **Claude Code** is the app this course assumes MILO lives in. **[GetAdvice](https://getadviceapp.com/)** is a real public app, and later you will practice writing clear feedback about it. The assumed setup is **Claude Code with a paid Claude plan (Pro or higher)**. If you don't have that, the fallback in [README.md](README.md) still lets you learn.

---

## Step 1 — Get the classroom onto your computer

This course is public. You clone it. There is no invitation to accept.

- **Easy way:** open your coding assistant and tell it:
  *"Please clone https://github.com/jmontano1/learn-to-code-with-milo and open it."*
- **Terminal way:**
  ```
  git clone https://github.com/jmontano1/learn-to-code-with-milo.git
  cd learn-to-code-with-milo
  ```

If you are already reading this file inside the project folder, this step is done.

## Step 2 — Install Claude Code and sign in

1. Go to the official page and follow the install steps for your computer:
   **https://claude.com/claude-code**
2. Sign in with a **paid Claude plan (Pro or higher)**. Claude Code is included with paid Claude plans (Pro, Max, Team, and Enterprise). The free Claude plan is chat on the web and in the apps. Current plans and prices are at **https://claude.com/pricing** — check that page, because they change.

> Tip: if you're comfortable with a terminal, a common install is
> `npm install -g @anthropic-ai/claude-code`, then run `claude`. If that means
> nothing to you, just follow the page above — it walks you through it.

**No paid plan yet?** Skip this step and use the fallback in [README.md](README.md). You can read every lesson with another assistant, or with a free chat, as long as you paste the starter message below so it reads `MILO.md`.

## Step 3 — Say hi to MILO

With the project open, paste this and press Enter:

```
Hi MILO! I'm new to coding. Please read MILO.md and be my tutor. Let's start with lesson 00.
```

Claude Code also picks up `MILO.md` through `CLAUDE.md` when a session starts. Other assistants need that pasted sentence, because they do not all load project notes on their own.

That's it. MILO greets you, asks your name, and starts teaching. From here on,
you just chat with MILO. 🌱

---

## If something goes wrong

- Nothing here can break your computer or lose work — everything stays inside the
  project folder.
- If a step is confusing, paste the error or the confusing part to your assistant
  and ask *"what does this mean?"*
- Still stuck? Ask the person who pointed you at this course, and show them the step you are on.
