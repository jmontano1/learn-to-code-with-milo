# Setup — for the grown-up helping get started 🛠️

This is a one-time, ~15-minute setup to get the learner into the classroom.
After this, he never needs the terminal again for the lessons — he just talks
to **MILO**. You do these steps once, together.

> The big picture: **MILO** is the tutor. **Claude Code** is the app MILO lives
> in. **GetAdvice** is MILO's friendly face out in the world. He has **Claude
> Pro**, which is all he needs.

---

## Step 1 — Accept the GitHub invitation

He was invited as a collaborator. Open this link **while signed in to his
GitHub account (`gmontano1`)** and click **Accept**:

- https://github.com/jmontano1/learn-to-code-with-milo/invitations

(If the link says the invite expired, tell me and I'll re-send it.)

## Step 2 — Install Claude Code and sign in with Claude Pro

1. Go to the official page and follow the install steps for your computer:
   **https://claude.com/claude-code**
2. When it asks you to sign in, use **his Claude Pro account**. That's the only
   subscription needed.

> Tip: if you're comfortable with a terminal, the common install is
> `npm install -g @anthropic-ai/claude-code`, then run `claude`. If that means
> nothing to you, just follow the page above — it walks you through it.

## Step 3 — Get the classroom onto the computer

Pick whichever is easier:

- **Easy way:** open Claude Code anywhere and tell it:
  *"Please clone https://github.com/jmontano1/learn-to-code-with-milo and open it."*
- **Terminal way:**
  ```
  git clone https://github.com/jmontano1/learn-to-code-with-milo.git
  cd learn-to-code-with-milo
  claude
  ```

## Step 4 — Say hi to MILO

With the project open in Claude Code, have **him** paste this and press Enter:

```
Hi MILO! I'm new to coding. Please read MILO.md and be my tutor. Let's start with lesson 00.
```

That's it. MILO greets him, asks his name, and starts teaching. From here on,
he just chats with MILO — no more setup needed. 🌱

---

## If something goes wrong

- Nothing here can break his computer or lose work — everything stays inside the
  project folder.
- If a step is confusing, he can literally paste the error or the confusing part
  to MILO and ask *"what does this mean?"* — MILO is patient and will explain.
- Still stuck? He can **reply to his welcome email** with a question for MILO,
  or ask the grown-up who helped him set this up.
