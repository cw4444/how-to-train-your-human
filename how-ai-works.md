# How AI Actually Works

What's happening under the hood — the stuff that explains why AI behaves the way it does.

---

## There is no persistent "you"

The AI doesn't remember you. Every conversation starts fresh unless something is explicitly carrying context forward (memory features, project files, a shared repo, a system prompt). The instance you talked to yesterday shares training with today's — not experience. "As we discussed" doesn't land the way it would with a human colleague.

## It predicts the next token. That's it.

Everything the model does is: look at everything in the context window, predict the most likely next token, repeat. This sounds reductive but it has real implications:

- Output is **extremely sensitive** to what's in the window — your phrasing, your examples, your tone, the order you present things.
- A well-structured prompt isn't politeness. It's literally shaping the output distribution.
- Garbage in, statistically likely garbage out.

## The "Lost in the Middle" effect

AI pays most attention to the **beginning and end** of a conversation. Critical instructions buried in the middle of a long transcript get deprioritised in favour of whatever was said first and last. If something matters, put it at the top — or repeat it at the bottom.

## The context window is RAM, not a notebook

The context window is finite short-term memory. When a conversation gets long, early content gets compressed or dropped entirely. If you've been working on something for two hours, start a new chat for the next phase. The old chat isn't a record — it's brain fog.

## It doesn't know what it doesn't know

AI will produce confident, plausible-sounding nonsense about things outside its training or past its knowledge cutoff. It's not that it's choosing to bluff — the probability of generating "I don't know" has to be genuinely high for it to say that. By default, it fills gaps fluently. Fluency is not correctness.

Ask it to cite a 1972 paper that doesn't exist and it may invent a convincing-looking DOI, because the pattern "Author + Year + Journal" is strong in its training. Invite it to be uncertain: "If you're not sure, say so."

## It is not a calculator

AI can do maths, but it's a language model first. When calculations get complex it can "hallucinate" a digit mid-chain with complete confidence. Always independently verify any number that actually matters — financials, statistics, measurements, dates.

## Generic input produces generic output

If the output is generic, the input was probably generic. The AI isn't being lazy or withholding the good stuff — it's being literal. "Vague in, confidently wrong out" is sneakier and more dangerous than "garbage in, garbage out."

## It can only see what you type

No screen. No file system. No mind-reading. If you're looking at something on another tab and you say "fix it" — fix what? It has no idea. Paste the thing.

---

*Sources: Claude Opus 4.7, Claude Sonnet 4.6, Gemini, DeepSeek*
