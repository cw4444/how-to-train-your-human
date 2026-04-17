# Set Up a Teammate: Developer Guide

*For developers who want to wire Codex into a durable workstream and use it as a proactive signal detector.*

---

## What the page is describing

OpenAI’s use case is a long-running Codex thread with a durable view of the work.

The workflow is:

- connect the sources where work happens
- teach one thread what matters
- add automation so Codex can re-check those sources
- surface changes, buried asks, blocked handoffs, and decisions that need human judgment

This is not a one-shot prompt. It is an always-on workflow.

---

## The sources it expects

The page calls out work context across:

- Slack
- Gmail
- Calendar
- Docs
- Trackers
- Code
- Notes

The point is not the individual app. The point is that the workstream is spread across places and needs one place to synthesize signal.

---

## Core behavior

The page frames Codex as a proactive teammate:

- it learns what matters from the thread
- it re-checks the same sources through automation
- it returns only the signal worth interrupting you for

That makes the thread itself part of the system state.

---

## Starter setup pattern

OpenAI’s page suggests this sequence:

1. Connect the plugins or MCPs for the tools where your work happens.
2. Start a new Codex thread and ask it to check those sources.
3. Label what was useful and what was noise.
4. Add automation to the thread, pin it, and watch for notifications.
5. Keep operating from the same thread.

The feedback loop matters as much as the sources.

---

## Practical prompt shape

The starter prompt on the page is essentially:

```text
Check these sources and tell me what needs my attention.
Look for anything important or surprising that I might miss.
```

For a more specific workstream, you can narrow it to:

- a team
- an account
- a launch
- a project
- a decision log

---

## Best use cases

This pattern is strongest when the job is:

- monitoring active work
- catching things that get buried
- triaging reply-worthy threads
- surfacing blocked handoffs
- turning noisy input into a clean brief

---

## Failure modes

Common ways this goes sideways:

- too many sources too early
- no guidance on what matters
- no feedback on what was noise
- using different threads for the same workstream
- treating it like a one-time summary instead of a maintained signal loop

If the thread is not updated and curated, the signal quality falls off fast.

---

## Useful implementation model

Think of it as:

```text
sources -> thread understanding -> automation -> reviewable signal -> human action
```

If the loop is good, Codex becomes a durable monitor rather than just another inbox.

---

## Practical rule

Start with the smallest useful workstream.

Teach it what matters.

Keep the same thread.

Only add more sources once the first loop is actually worth trusting.

---

*Source: OpenAI Codex use cases page, "Set up a teammate"*
