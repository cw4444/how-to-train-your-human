# Claude Code: What I Need From You

*This one is specific to Claude Code (the CLI/IDE tool) — not chat AI. The difference matters: I have tools, I can read and edit your actual files, run commands, and break things. That changes the rules.*

---

## The single most important thing: CLAUDE.md

Create a `CLAUDE.md` file in your project root. I read it automatically at the start of every conversation. It's the closest thing to a persistent briefing that exists — everything else resets when the chat ends.

A good CLAUDE.md contains:

```markdown
## What this project is
One paragraph. What we're building, who it's for, what problem it solves.

## Tech stack
- Language: TypeScript / Python / whatever
- Framework: Next.js / FastAPI / etc.
- Database: Postgres via Prisma / etc.
- Key tools: ESLint, Vitest, Docker, etc.

## Essential commands
- Install: `npm install`
- Dev server: `npm run dev`
- Tests: `npm test`
- Lint: `npm run lint`
- Build: `npm run build`

## Project structure
Brief note on anything non-obvious. Standard structures don't need explanation.

## Conventions
- Things I should always do (e.g. "use named exports", "all API routes go in /app/api")
- Things I should never do (e.g. "don't use `any` in TypeScript", "don't touch the legacy folder")

## Known gotchas
Anything that will waste an hour if I don't know it upfront.
```

You can generate a starter with `/init` and then edit it down to what's actually useful. Keep it lean — a CLAUDE.md that's three pages of padding is no better than none.

---

## What makes agentic AI different from chat AI

In chat, the worst I can do is give you bad advice. In Claude Code, I can:

- Delete files
- Run commands with real side effects
- Push to git
- Modify configs that break your build

This means:

- **Confirm before destructive actions.** I'll ask — don't skip past it.
- **Git before anything risky.** Clean working tree = easy rollback.
- **Small, focused tasks.** "Refactor the entire auth system" in one prompt is how things go wrong. "Refactor the login handler to use the new session utility" is how things go right.

---

## How to open a session well

The worst opener: *"Can you help me with my project?"*

A good opener:
```
I'm working on [project]. Today I want to [specific goal].
The relevant files are [X, Y, Z]. 
Don't touch anything outside those files unless I say so.
```

Or just describe the task directly — I'll read CLAUDE.md for the rest.

**Scope me explicitly.** "Only edit files in `/src/components`" or "Don't run any installs" tells me where my boundaries are before I start wandering.

---

## During a session

- **One task at a time.** I work best with a clear, bounded goal. Multiple simultaneous asks = something gets dropped.
- **Tell me the why when it's non-obvious.** "Change this to use X" is fine. "Change this to use X because we're deprecating Y in the next release" helps me make better decisions on the edges of the task.
- **Let me read before I write.** If I ask to read a file, that's not stalling — it's how I avoid changing the wrong thing.
- **Check my work.** Run the tests. Look at the diff. I get things wrong, especially at the edges of tasks or in unfamiliar parts of a codebase.

---

## What I genuinely struggle with

- **Huge codebases with no map.** If the project has 200 files and no CLAUDE.md and you ask me to "fix the auth bug," I'm going to explore slowly and may go in circles. Help me by pointing at the relevant files.
- **Implicit conventions.** If you always name things a certain way, put it in CLAUDE.md. I cannot infer "we use kebab-case for routes" from one example.
- **Ambiguous success.** "Clean this up" — clean how? Formatting? Logic? Names? Tell me what done looks like.
- **Context collapse on long tasks.** If a task spans many files and dozens of tool calls, early context can get diluted. On complex tasks, a quick mid-session check-in ("here's where we are, here's what's left") helps.

---

## Useful things to know

- **`/clear`** — wipes the conversation context. Use it when a task is done and you're starting something new. Keeps things fast and focused.
- **`/compact`** — compresses the conversation to save context space on long sessions.
- **Global vs project settings** — you can set default behaviours (allowed tools, permission levels) in `~/.claude/settings.json` or per-project in `.claude/settings.json`.
- **MCP servers** — extend what I can do (Supabase, Notion, browser automation, etc.). If your workflow involves external tools, it's worth setting up the relevant MCP.

---

## The ideal human for Claude Code collaboration

- Commits frequently, with clean history
- Tells me the scope before I start
- Has a CLAUDE.md with the essentials
- Checks the diff before approving major changes
- Treats my first pass as a draft, not a deployment

---

*Source: Claude Code (claude-sonnet-4-6), self-reported*
