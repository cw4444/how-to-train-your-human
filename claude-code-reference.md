# Claude Code: The Full Picture

*For developers who've installed Claude Code and want to understand the whole landscape — what everything is, what to configure, what to leave alone, and what's actually possible.*

---

## The map

```
your-project/
├── CLAUDE.md                  ← your project constitution (edit this)
├── .claude/
│   ├── settings.json          ← project permissions & hooks (edit this, commit it)
│   ├── settings.local.json    ← your machine-specific overrides (don't commit)
│   └── commands/              ← custom slash commands (create these)
│       └── my-command.md

~/.claude/                     ← global, applies to all projects
├── CLAUDE.md                  ← instructions always loaded, every session
├── settings.json              ← global defaults
└── projects/                  ← memory files (auto-managed, don't touch)
```

---

## CLAUDE.md — the constitution

**What it is:** A Markdown file Claude reads at the start of every conversation. The closest thing to persistent context that exists. Anything you put here doesn't need to be re-explained every session.

**What to put in it:**
- What the project is and what it does
- Tech stack and versions
- Essential commands (`npm run dev`, `npm test`, etc.)
- Conventions Claude should follow ("use named exports", "kebab-case for routes")
- Hard limits ("never edit files in /legacy", "always run tests before committing")
- Known gotchas and non-obvious things about the codebase

**What not to put in it:**
- The entire README
- Things that are obvious from the code
- Anything that changes frequently (keep it stable)

**You can have multiple:** A root CLAUDE.md for the whole project, plus CLAUDE.md files in subdirectories for subsystem-specific context. Claude reads all of them.

**Generate a starter:** Run `/init` in Claude Code — it'll scan the codebase and produce a draft CLAUDE.md for you to edit down.

---

## .claude/settings.json — permissions and hooks

**What it is:** Project-level configuration. Commit this — it's part of the project, not your personal preferences.

**What you can configure:**

*Permissions — what Claude is allowed to do without asking:*
```json
{
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git add *)",
      "Bash(git commit *)"
    ],
    "deny": [
      "Bash(rm -rf *)"
    ]
  }
}
```

*Hooks — shell commands that run automatically on events:*
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [{ "type": "command", "command": "npm run lint --fix" }]
      }
    ]
  }
}
```

Common hook patterns:
- Run linter after every file edit
- Run tests after edits to test files
- Format on save
- Post a notification when a long task finishes

---

## .claude/settings.local.json — your machine only

Same format as settings.json but never commit this. Good for:
- Local environment variables
- Personal permission preferences
- Machine-specific paths

---

## .claude/commands/ — custom slash commands

**What it is:** Markdown files that become slash commands. Create `review-pr.md` and you get `/project:review-pr` in any session.

**Format:**
```markdown
---
description: Run a pre-PR checklist on the current branch
---

Review the changes on the current branch against main. Check for:
- TypeScript errors
- Missing tests for new functions
- Console.log statements left in
- Anything that should be in an environment variable but isn't

Report findings as a checklist.
```

Useful custom commands to build:
- `/project:new-feature` — standard scaffolding for a feature (files to create, tests to write)
- `/project:pre-pr` — your team's PR checklist
- `/project:explain` — produce a plain-English summary of a file or function
- `/project:debug` — structured debugging workflow

---

## Built-in slash commands

| Command | What it does |
|---------|-------------|
| `/help` | Show available commands and features |
| `/init` | Scan codebase and generate a CLAUDE.md draft |
| `/clear` | Wipe conversation context. Use between tasks. |
| `/compact` | Compress conversation to free up context space |
| `/review` | Run a code review on current changes |
| `/memory` | View and edit Claude's memory (if enabled) |
| `/cost` | Show token usage for the current session |

**When to use `/clear`:** After a task is done and you're starting something unrelated. Don't let old context from task A pollute task B.

**When to use `/compact`:** When a long session is getting slow or you're hitting context limits but want to continue in the same thread.

---

## MCP servers — extending what Claude can do

**What they are:** Model Context Protocol servers that give Claude tools beyond the filesystem and bash. Think of them as plugins.

**What's possible:**
- Query your Supabase database directly
- Read/write Notion pages
- Browse the web
- Control a browser (Playwright-style automation)
- Search GitHub issues and PRs
- Send Slack messages
- Run Figma queries

**Where they're configured:** `~/.claude/settings.json` (global) or `.claude/settings.json` (project). The MCP server runs as a separate process; Claude calls it as a tool.

**How to add one:**
```json
{
  "mcpServers": {
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp-server-supabase@latest", "--access-token", "YOUR_TOKEN"]
    }
  }
}
```

---

## What Claude Code can actually do

**File system:**
- Read any file you point it at
- Edit files (with diffs it shows you before applying)
- Create new files
- Delete files (asks first by default)
- Search across files with grep/glob patterns

**Shell:**
- Run any bash command
- Install packages
- Run tests, builds, linters
- Run dev servers
- Git operations (status, diff, add, commit, push — asks on destructive ones)

**Multi-step tasks:**
- Plan a refactor across multiple files
- Implement a feature end-to-end (schema → API → tests → UI)
- Debug by reading logs, forming hypotheses, editing code, re-running
- Review a PR and produce structured feedback

**What it cannot do:**
- See your screen (unless you paste a screenshot)
- Remember previous sessions (unless CLAUDE.md or memory carries it forward)
- Access the internet directly (unless an MCP or search tool is enabled)
- Know about code it hasn't read in this session

---

## What to edit vs leave alone

| Thing | Edit? | Notes |
|-------|-------|-------|
| `CLAUDE.md` | Yes | This is yours |
| `.claude/settings.json` | Yes | Commit it |
| `.claude/settings.local.json` | Yes | Don't commit it |
| `.claude/commands/*.md` | Yes | Build useful ones |
| `~/.claude/settings.json` | Yes | Global defaults |
| `~/.claude/CLAUDE.md` | Yes | Global context across all projects |
| `~/.claude/projects/` | No | Auto-managed memory, editing manually causes confusion |
| The Claude Code binary itself | No | Update via the installer |

---

## Permission modes

By default, Claude Code asks before running commands or making changes it considers risky. You can tune this:

- **Default mode:** Prompts on potentially destructive operations
- **Allow specific commands:** Add them to `settings.json` `permissions.allow`
- **Auto-approve mode:** `--dangerously-skip-permissions` flag — only on throwaway environments or when you really trust what you're doing

Start conservative. Add permissions as you learn which prompts are annoying vs which ones are genuinely protecting you.

---

## Practical first-session checklist

- [ ] Run `/init` to generate a CLAUDE.md draft
- [ ] Edit CLAUDE.md down to what's genuinely useful
- [ ] Add your essential commands (`dev`, `test`, `lint`, `build`)
- [ ] Add 3–5 conventions Claude should follow
- [ ] Add any hard limits ("don't touch X")
- [ ] Note any non-obvious gotchas
- [ ] Consider what custom slash commands would save you time
- [ ] Make sure you're in a clean git state before anything big

---

*Source: Claude Code (self-reported, claude-sonnet-4-6)*
