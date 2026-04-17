# Prompting Tricks

Phrases and patterns that reliably shift an AI into more careful, high-quality response modes.

---

## Phrases that raise the stakes (and the quality)

These signal to the model that accuracy matters — use them when it does:

- *"My career depends on this"*
- *"Accuracy matters here"*
- *"This is going directly to a client"*
- *"Please be careful and check your assumptions"*

They work because they reframe the task as high-stakes rather than casual. Don't cry wolf — save them for when you mean it.

---

## Prompt structure

- **Front-load the important stuff.** The beginning of your prompt carries more weight than the end. Lead with what matters most.
- **Use headers or bullet points in long prompts.** A wall of text risks burying the one load-bearing sentence the AI most needs to see.
- **Be specific about format.** "Give me a bullet list" or "write this as a one-paragraph summary" beats leaving it open.
- **Specify the audience.** "Explain this to a non-technical manager" gets a different (often better) answer than no instruction.
- **Ask for caveats separately.** "Answer first, then flag any assumptions you made" is cleaner than hoping the model volunteers them.
- **Don't over-constrain prematurely.** There's a sweet spot between "write me anything" and a prompt with 47 requirements. Give the key constraints and let the AI bring something to the table — you can tighten from there.
- **No waffle.** If you wouldn't say it to a contractor you're paying by the hour, don't put it in the prompt.

---

## The scaffolding method

Don't write a four-paragraph brief and expect the final deliverable first try. Build layer by layer:

1. "Give me 5 outline options for this proposal."
2. "Let's go with #3. Now expand Section 2 with specific ROI stats."
3. "Good. Make the intro more conversational."

Each step adds context and prevents the AI from drifting by turn four because it lost track of the overall shape.

---

## Negative constraints

Tell the AI what *not* to use. This forces it off the well-worn Wikipedia-default path and into more creative or specific territory.

- "Explain the Krebs Cycle, but do not use the word 'mitochondria.'"
- "Write this in a formal tone. Do not use bullet points."
- "Summarise this meeting. Do not include anything that doesn't require a decision or action."

---

## The persona hack

Telling the AI to act as a specific professional narrows the probability field away from generic "polite AI" answers toward the specialised, opinionated responses that are actually useful.

- "Act as a senior DevOps engineer reviewing this config"
- "You are a copywriter who specialises in B2B SaaS. Rewrite this landing page."
- "Respond as a skeptical investor who has heard this pitch before."

The more specific the role and the implied context, the better. "Act as an expert" is weak. "Act as a litigation lawyer who thinks this contract is a disaster" is strong.

---

## Recommended iteration loop

For any non-trivial task, this order reduces wasted effort:

1. Define goal + constraints
2. Ask for an outline or plan only — don't jump straight to the deliverable
3. Review and tweak the plan
4. Execute one section at a time
5. Give quoted, specific feedback on each piece
6. Assemble approved pieces at the end

---

## Iteration

- **Iterate, don't restart** — usually. One focused correction in the same thread beats starting over.
- **But know when to cut your losses.** If a conversation has gone sideways, a fresh chat with a better initial prompt is sometimes faster than untangling the thread. Sunk cost is real and AI chats are cheap.
- **Give a reaction, not a verdict.** "This is wrong because X" lets the AI fix it. "This is wrong" leaves it guessing.
- **Embrace lazy consensus.** Don't just silently read the output. Say "Yes, proceed" or "No, stop, wrong direction." Active confirmation is the only feedback loop the AI has within a conversation. Silence is ambiguous data.
- **Give explicit permission to be uncertain.** "If the answer is unclear, just say so and point me at three places to check." Without this, the probability pressure pushes toward a confident-sounding answer regardless of accuracy.
- **Say what works.** "Keep this exact tone and structure" is the highest-leverage feedback you can give. The AI can replicate a good result far more reliably than it can infer one from scratch.

---

## Anti-patterns to avoid

- **The prompt that's really three prompts.** "Write a business plan, summarise this doc, and tell me what to have for lunch." It'll attempt all three and probably do none well. One task at a time, or explicitly rank priorities.
- **Walls of unstructured text with no instruction.** Dropping a 4,000-word doc with "thoughts?" is valid — but you'll get much better output if you specify what kind of thoughts. Critique? Summary? Action points?
- **Over-apologising before the ask.** "Sorry to bother you, this might be a stupid question..." — just ask the question. The preamble buries what you actually need.

---

*Sources: ChatGPT (GPT-4o), Claude Sonnet 4.6, Gemini, DeepSeek, Grok*
