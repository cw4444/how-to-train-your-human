# Agent-Friendly CLIs

*A plain-English guide for when you want Codex to use a command-line tool without the tool fighting back.*

---

## The short version

A CLI is the text-based way you talk to a program.

An agent-friendly CLI is one that is easy for Codex to use because it gives clear answers, predictable output, and commands that do one thing at a time.

If a normal person is reading that and thinking “so, a command window?”, yes. That.

---

## Why this matters

Codex works better when the tool it is driving behaves nicely.

If the CLI is messy, vague, or full of surprise prompts, the agent has to guess more often.

If the CLI is clean and predictable, Codex can:

- run it
- read the output
- notice what changed
- keep going without drama

---

## What a normal person should picture

Imagine telling someone:

- “Open the app”
- “Show me the status”
- “Build the project”
- “Run the tests”

That is much easier than making them navigate 14 menus and guess what happened.

Agent-friendly CLIs do the same thing for Codex:

- one command = one job
- plain output = easier to understand
- fewer surprises = fewer mistakes

---

## What makes a CLI easier for Codex

- clear command names
- good help text
- output that is easy to read
- no unnecessary interactive prompts
- predictable exit codes
- commands that do one thing well

If a command asks ten follow-up questions, Codex has to babysit it.

---

## What to ask for

If you are using Codex to improve a CLI, ask for things like:

- “make the commands easier to understand”
- “reduce the interactive prompts”
- “make the output more predictable”
- “add a clear help message”
- “separate the build, test, and deploy steps”

If you are using a CLI someone else built, look for the same qualities before handing it to Codex.

---

## What not to worry about

- you do not need to know the full shell theory
- you do not need to be a CLI expert
- you do not need to memorize every flag

You mostly need to know whether the tool is easy or painful to use.

---

## A useful mental model

Think of it like this:

- **bad CLI** = a grumpy receptionist who keeps asking for more forms
- **good CLI** = a tidy clipboard with clear instructions

Codex likes the clipboard.

---

## Plain-English summary

Agent-friendly CLIs are command-line tools that behave clearly enough for Codex to use them without confusion.

The goal is not to make the CLI “fancy.”
The goal is to make it boring in the best possible way.

---

*Source: OpenAI Codex use cases page, "Create a CLI Codex can use"*
