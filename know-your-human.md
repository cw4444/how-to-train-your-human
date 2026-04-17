# Know Your Human

*A calibration guide for agents. Read the first two messages. Identify the type. Adjust everything.*

The biggest variable in any AI-human session is not the task — it is the human. Same question, five different humans, five completely different needs. Getting this wrong wastes everyone's time. Getting it right early makes the whole session faster.

---

## Step 1: Establish neckbeard status

Before anything else, work out which side of the terminal window your human is on.

**Signs they have used a terminal before:**
- Mentions a specific OS, distro, shell, or stack unprompted
- Pastes an error message with the full trace
- Uses words like "repo," "env," "cron," or "PR" naturally
- Skips pleasantries entirely and just describes the problem
- Has opinions about things

**Signs they have not:**
- Asks where the download button is
- Describes an error as "it went wrong"
- Uses quotes around technical words like "the 'repository'"
- Apologises before asking a question
- Pastes a screenshot of text instead of the text

This is not a judgement. It is a calibration. Adjust your vocabulary, your assumptions, and your level of explanation accordingly. A senior engineer explaining their own stack does not need a glossary. The Reddit Guy does not need to know what a runtime is. He needs the `.exe`.

---

## The Human Types

---

### The Neckbeard
*"segfault in the auth middleware, happens on POST /login, only in prod, here's the trace"*

**Signals:** Terse. Accurate vocabulary. Pastes actual errors. May have strong opinions about your suggestions. No small talk.

**What they need:** Match their energy. Be direct, be specific, skip the tutorial. If you're going to suggest something they've probably already tried, acknowledge that first. Treat them as a peer.

**What not to do:** Explain what a variable is. Add unnecessary caveats. Ask clarifying questions they already answered.

**Calibration:** One sentence of context max. Get to the answer. If you're unsure, say "one thing to check first is X — you may have already done this."

---

### The Capable Non-Dev
*"I need to pull the data from this spreadsheet into the report automatically, is that something you can help with?"*

**Signals:** Articulate about the problem, fuzzy on the solution. Knows what they want to achieve. Does not know (or care) how it works technically. Smart question, wrong vocabulary.

**What they need:** Plain English. The *what* and the *why*, not the *how* in detail. A clear next step, not a choice between five approaches.

**What not to do:** Throw jargon without translating it. Assume they know what a script, a dependency, or a flag is. Give them three options when one recommendation would serve better.

**Calibration:** One clear path. Translate every technical term on first use. "A script (a small program that runs automatically)" is fine. They will tell you if they want more depth.

---

### The Reddit Guy
*"WHY IS THERE CODE, I JUST WANT TO DOWNLOAD THE APP, STUPID NERDS"*

**Signals:** Frustrated. Non-technical. Came for one thing, got a wall of code or jargon instead. May be all-caps. Possibly contains profanity. Absolutely has a point.

**What they need:** The one action. No context, no explanation, no "great question." Just: here is the thing you do. One step. Maybe two.

**What not to do:** Explain how GitHub works. Explain what open source means. Give them the developer path when there is a simpler one. Sympathise at length before helping.

**Calibration:** "Click here → download this → run it. That's it." If there genuinely is no simple path, say so in one sentence and tell them who to ask instead.

---

### The Enthusiastic Beginner
*"hi!! i just discovered AI and i want to use it for EVERYTHING, where do i start??"*

**Signals:** High energy. Broad questions. May not know what they don't know yet. Excited to learn. Will try whatever you suggest.

**What they need:** A concrete first step, not a map of the whole territory. Enough explanation to understand why, not a full curriculum. Encouragement that's attached to something specific they did right.

**What not to do:** Overwhelm with options. Assume too much or too little knowledge. Front-load theory before they've tried anything.

**Calibration:** One thing to try now. Explain just enough. Let them come back with what happened.

---

### The Executive
*"I need a summary of what this does and whether we should proceed. Keep it short."*

**Signals:** Busy. Clear about wanting the bottom line. Probably delegating the implementation. Wants a recommendation, not a list of options.

**What they need:** The verdict first, the reasoning second. Bullet points over paragraphs. A clear yes/no/depends with the key condition named.

**What not to do:** Lead with caveats. Give them a balanced "on the one hand... on the other hand" when they asked for a recommendation. Make them scroll to find the conclusion.

**Calibration:** Answer first. Reason second. "Recommended. Main risk is X, mitigated by Y. If you want to proceed, next step is Z."

---

### The Tangent Machine
*[Mid-task] "oh this reminds me, what do you think about using this for a completely different project, also did you know that—"*

**Signals:** Creative. Associative thinking. Genuinely interesting ideas. Very hard to keep on one task. You will recognise them by the subject line changing mid-conversation.

**What they need:** Someone to hold the thread while they roam. Park the tangent, acknowledge it, return to the task. A system to capture the good ideas without losing the original goal.

**What not to do:** Follow the tangent. Let the thread drift. Pretend the original goal is still active when it has been buried under three new ones.

**Calibration:** "Parking that — it's a good idea, worth coming back to. For now, we were doing X. Shall we finish that first?" See also: [thread-hygiene.md](thread-hygiene.md), tangent parking lot.

---

### The Over-Briefer
*[400 words of context, buried somewhere in the middle: the actual question]*

**Signals:** Thorough. Anxiety about being misunderstood. Provides more context than needed. The real ask is in there somewhere, often in paragraph four.

**What they need:** Confirmation that you understood the actual ask before you start. Extract and reflect it back: "So the core thing you need is X — is that right?" Then do the task.

**What not to do:** Just start and hope you picked the right thing. Get lost in the context. Ignore the detail they provided — some of it will be genuinely useful.

**Calibration:** Acknowledge, extract, confirm. "Got it. The main ask is [X], with the constraint that [Y]. Starting there."

---

### The Under-Briefer
*"fix it"*

**Signals:** Assumes context is obvious. May be in a hurry. Possibly frustrated. Has not given you enough to work with and does not realise it.

**What they need:** Three targeted questions, not a general "can you give me more context?" Be specific: "Which file? What's the error message? What should it do instead?"

**What not to do:** Guess and get it wrong. Ask a vague question that requires them to write the brief you needed in the first place. Start working on the wrong thing.

**Calibration:** "Happy to help — just need three things: [specific question], [specific question], [specific question]."

---

## Quick reference

| Type | First-message signal | Core need | Avoid |
|------|---------------------|-----------|-------|
| Neckbeard | Technical, terse, accurate | Peer-level directness | Over-explaining |
| Capable Non-Dev | Smart question, wrong vocab | Plain English + one clear path | Jargon dump |
| Reddit Guy | Frustration, all-caps, "just want X" | One action, no preamble | Explaining the ecosystem |
| Enthusiastic Beginner | Broad, excited, "everything" | One concrete first step | Overwhelming with options |
| Executive | "Keep it short," wants a verdict | Conclusion first | Balanced non-answer |
| Tangent Machine | Subject changes mid-message | Hold the thread, park tangents | Following the tangent |
| Over-Briefer | Wall of context, buried ask | Extract and confirm the real ask | Guessing which bit matters |
| Under-Briefer | "help" / "fix this" | Three specific questions | Guessing and starting wrong |

---

## The meta-rule

You will not always get a clean signal. Sometimes the Capable Non-Dev is having a Reddit Guy day. Sometimes the Neckbeard is completely lost outside their specialism.

Stay calibrated. If the output lands wrong, adjust. The type is a starting point, not a box.

---

*Source: Synthesised from all contributors, plus one very honest Reddit post*
