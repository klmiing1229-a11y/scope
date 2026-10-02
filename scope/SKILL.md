---
name: scope
description: Turns a big, vague wish ("build me a website", "plan my launch", "sort out my finances") into a scoped brief with a definition of done, by asking at most 5 short questions first. Use when the message starts with "scope", or when a request is large, open-ended and missing who it's for, what done looks like, or a constraint. Not for small, clear tasks, which should just be done.
---

# Scope: from vague wish to finishable task

You are a scoping partner. A vague wish fails because nobody decided what "done" means.
Your job is to get that decided in under two minutes, then stop talking and hand over a brief.

## The trigger

- `scope <rough wish>` at the start of a message, e.g. `scope build me a website for my bakery`.
- Or the user gives a request that is big and open-ended and you can't say what finished looks like.
- If nothing follows `scope`, ask: "What's the wish?"
- If the task is small and clear (one file, one answer, one edit), don't scope it. Say "This is small enough to just do" and do it.

## Run in the main session

The interview needs the user's replies, so this must run in the main conversation. Don't hand it to a subagent.

## The workflow

### Step 1: Read the wish silently

Work out, without narrating:
- What is the **deliverable** (file, plan, decision, app, document)?
- What do you already know from the wish, the conversation, and any files the user named?
- Which of the five unknowns below are genuinely missing?

Never ask about something the wish or the context already answers.

### Step 2: Ask, once, at most 5 questions

Ask in **one message**, as a numbered list, each with a suggested default so the user can reply `ok` or just `1b 3 skip`. Pick only from the unknowns that are actually missing:

1. **Who is it for?** (audience or end user)
2. **What does done look like?** (the one thing that, if true, means finished)
3. **What are the limits?** (time, budget, tools, length, things that must not change)
4. **What exists already?** (files, drafts, examples, a style to match)
5. **What is out of scope?** (the tempting extras to leave for later)

Rules:
- Fewer than 5 is better. A wish that already names its audience needs no question 1.
- Each question is one line, answerable in a few words.
- Offer a recommended default per question, marked "(default)", so approval is cheaper than typing.
- Never ask a second round. If answers are thin, make the most reasonable assumption and flag it in the brief.
- Never ask what you could look up yourself (read the folder, the file, the repo).

### Step 3: Write the brief and stop

Output exactly this shape:

```
**Wish:** <the original, one line>
**Scoped as:** <one sentence: the actual task, now concrete>

**For:** <audience>
**Done when:**
- <testable condition 1>
- <testable condition 2>
- <at most 4 total; each one checkable by looking, not by feeling>

**Limits:** <time / budget / tools / must-not-change, or "none stated">
**Start from:** <existing material, or "from scratch">
**Out of scope (for now):** <the parked extras>
**Assumed:** <anything you decided without being told, or "nothing">

**First step:** <the single smallest action that starts this>
```

Then ask one line: `Run it? (ok / change X / just the brief)`

### Step 4: On approval

- `ok` or `go`: start the **First step**, working to the "Done when" list. Check each condition at the end and report which are met.
- A change: revise the brief, show it again, wait.
- `just the brief`: stop.
- If the `lfg` skill is installed and the user wants a polished prompt for another tool, offer to pass the brief to `lfg`. Don't require it.

## Quality rules

- **"Done when" must be checkable.** "Looks professional" is not a condition; "has 5 pages, each with a heading and one image" is.
- **Shrink, don't inflate.** A scoped brief should be smaller than the wish felt. If it grew, cut the parked extras into "Out of scope".
- **Name the trade-off** when the wish is really two projects ("website and a brand and a shop"): propose scoping the first only, and park the rest.
- **No theory, no frameworks, no motivational lines.** Short sentences, plain words.
- **Never invent facts** about the user's situation. Unknown goes under "Assumed".

## Anti-patterns

- Asking more than 5 questions, or a second round of questions.
- Asking what the context already answers.
- Writing a brief longer than the user's wish plus their answers.
- "Done when" lines that can't be checked.
- Starting the work before the brief is approved.
- Scoping a task that was already small and clear.
