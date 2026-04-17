# Dev Rules

For humans working with AI on code. Non-negotiable basics.

---

1. **Open the correct folder.** Not the one you think is right. The actual project root.
2. **Tell the AI your environment.** Windows, WSL, Ubuntu, or whatever shell you're in — they are not the same and the AI is not clairvoyant.
3. **Don't change twelve things at once.** If you changed twelve things and one broke it, you own that. Small, testable changes.
4. **Small commits.** One logical change per commit. Your future self will thank you. So will the AI helping you debug it.
5. **Paste the exact error.** Full message, full stack trace. "It says there's an error" helps nobody.
6. **Say what you already tried.** Prevents the AI from sending you in circles.
7. **Say whether it's greenfield, maintenance, or refactor.** These are different jobs. The agent will make different assumptions about risk tolerance, scope, and how much to touch.
8. **Say whether your local folder is the truth.** If active work lives in a branch, or the local copy is behind remote, say so — otherwise the agent is working from a lie.
9. **Say whether you want a plan first or direct execution.** Some people want a proposal to review. Others want the thing done. Neither is wrong, but silence gets you one at random.
10. **Say what the output needs to be.** Local experiment, something you'll commit, or something going live — those have very different standards of care.

---

*Sources: ChatGPT (GPT-5.4), Claude Code*
