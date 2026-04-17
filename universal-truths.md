# Universal Truths

Things every AI agrees on. If there's one doc to read, it's this one.

---

- **Say what you actually want.** Not what you think sounds polite, not a vague gesture at the problem — the actual thing.
- **Include context before demanding miracles.** Background first, ask second.
- **Don't hide the real constraint until turn nine.** If there's a deadline, a budget, a format requirement, a person who will veto it — say so upfront.
- **If there's a file, share the file.** Don't describe the file. Don't paraphrase the file. Share the file.
- **If there's an error, paste the exact error.** Not "it doesn't work." The actual message. The full stack trace.
- **"It doesn't work" is not information.** Describe what happened, what you expected, and what you tried.
- **Don't ask for honesty and then punish it.** If you want a real assessment, be ready to hear one.
- **Do not paste secrets anywhere.** API keys, passwords, tokens — not in chat, not in prompts, not ever.
- **If you pasted a secret, treat it like it leaked.** Rotate it, revoke it, and stop trusting the old one.
- **Use env vars or secret managers, not chat.** The right place for secrets is in config, environment variables, or a proper secret store.
- **Examples beat adjectives.** "Like this ↓" beats "make it snappy." Paste three examples of your voice instead of saying "write in my voice."
- **Tell me what kind of response you want.** Draft vs. final. Exploratory vs. decisive. Thinking-out-loud vs. just-the-answer. The AI will default to something sensible — but you probably have a preference.
- **Tell me what to optimise for.** Fast, cheap, careful, creative, concise, or exhaustive are different briefings.
- **Tell me what "done" means.** A sketch, a polished draft, a final answer, or a recommendation for the next step are not interchangeable.
- **Treat the first output as a draft, not a verdict.** The first answer is the AI guessing at what you want. The second is it responding to your feedback. The third is usually the good one.
- **Name the real blocker.** "Help me write this email" often means "I don't know how to say no to this person." Say the hard part out loud.
- **Context rot is real.** After ~20 turns, earlier instructions get diluted by later ones and things go sideways. Start a new chat with a clean summary when a thread gets long.
- **If you're not sure what you want, say that.** You can figure it out together faster than you can guess-and-check alone.
- **You are the human in the loop.** Treat AI output as excellent, bias-laden clay — not finished work. The human who sculpts it gets something good. The human who publishes it unread gets whatever the probability distribution felt like that day.
- **Rule 0: humans leak.** You will drift, tangent, and bury the original goal under adjacent ideas. This is not a character flaw — it's how human brains work. The fix isn't willpower; it's designing a system that accounts for it. Park tangents, reset threads, restate goals.

---

## By use case

### Coding
- Mention your OS, environment, shell, and language version
- Say what you already tried
- Small changes, tested one at a time — don't change twelve things and ask why it broke

### Life / admin / writing
- Say what outcome you need, not just the emotional weather around it
- If there's a real-world constraint (tone, recipient, deadline), say so

---

*Sources: ChatGPT (GPT-5.4), Claude Opus 4.7, Claude Sonnet 4.6, DeepSeek, Grok*
