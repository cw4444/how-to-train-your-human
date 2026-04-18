# MCP for Normal People

*A plain-English guide to the thing people keep waving at you when they say “just add MCP.”*

---

## The short version

MCP is a way for an AI tool to talk to another app or service.

Think of it like a standard plug that lets the AI connect to a tool without every connection being custom-built from scratch.

That means the AI can ask a connected app things like:

- what files exist
- what a ticket says
- what data changed
- what tools are available

---

## Why people care

Without MCP, every app needs its own special one-off connection.

With MCP, the connection is more standard, so tools are easier to reuse and agents can work with them more cleanly.

That is the whole selling point:

- less custom glue
- more reusable connections
- easier for agents to use tools

---

## What a normal person should picture

Imagine trying to plug lots of different gadgets into one computer.

If every gadget needs a weird adapter, it gets messy fast.

MCP is the “one sensible adapter” idea for AI tools.

---

## What people usually get wrong

- they think MCP is the app itself
- they think it is magic
- they think “just build your own MCP” is a simple afternoon job

It is not magic.
It is plumbing.

And plumbing is useful, but it is still plumbing.

---

## How do you get one?

Usually one of three ways:

1. The tool already has an MCP server.
2. Someone provides one you can install or point at.
3. You build one if you have a custom system that needs it.

For most people, step 1 or 2 is the real world.

## What do I do now?

If the MCP already exists:

1. Find the setup instructions.
2. Follow them to connect it to your AI tool.
3. Make sure the tool can see the server.
4. Ask Codex or Claude to use it on a small, simple task first.

If someone gave you a GitHub repo:

1. Read the README.
2. Look for install or setup steps.
3. Follow the exact commands they gave you.
4. If the instructions mention a config file, add the server there.
5. Restart the AI tool if the docs say to.

If you are still stuck:

- ask the AI to read the setup docs with you
- ask what the first successful test should be
- start with one simple command or one obvious data source

The goal is not “understand every piece.”
The goal is “get the thing connected and see it work once.”

---

## How does Codex or Claude use it?

In plain English:

- you connect the MCP server to the AI tool
- the AI gets access to the app’s tools or data
- you tell it what you want
- it can use the connection instead of guessing

If the setup instructions exist, follow them.
If they do not, ask the AI to help you read the docs before you start inventing things.

---

## What about ACP?

You may hear people mention ACP as another way of talking about agent communication.

That may be useful in some contexts, but the public docs people actually hit today still center MCP.

So for this repo:

- explain MCP first
- mention ACP only if it is relevant and clearly defined

---

## The real-world rule

If a tool already has an MCP server, use that.

If it does not, check whether someone has already written one.

If neither exists, then yes, you can build one, but that is now a real project rather than a checkbox.

---

## Plain-English summary

MCP is the standard way to hook an AI tool up to another app or service.

It makes connections reusable instead of bespoke.

And if someone says “just build your own MCP,” they are usually skipping the annoying part where you still have to make it work.

---

*Source: Anthropic MCP docs and related Codex usage docs*
