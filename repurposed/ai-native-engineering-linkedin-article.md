# LinkedIn Short Article — AI-native engineering

**Format:** LinkedIn article (short edition, ~870 words)
**Source:** "What is AI-native engineering, and how to hire for it" — https://wise-step.ro/blog/ (Calin Muresan, 3 June 2026)
**Suggested headline:** Your engineers ship more code than ever. Why are you shipping more bugs?
**Alt headlines:**
- The engineer stopped being the author. Most job specs haven't noticed.
- How to hire an AI-native engineer without being an AI expert
**Cover image:** the blog hero (Unsplash) or a plain text card: "40% context · 20% generation · 40% verification"
**Hashtags (place at the end, 3–5 max):** #AInative #EngineeringLeadership #TechRecruitment #Hiring #SoftwareEngineering

---

## Your engineers ship more code than ever. Why are you shipping more bugs?

Every engineering leader I talk to is living the same paradox.

AI writes more of their codebase than at any point in history. And yet: more incidents, more rework, more technical debt than two years ago. The New York Times gave it a name back in April — "code overload."

If AI writing everything were the answer, why are so many teams worse off?

Because most of them bolted AI onto a broken process. The teams pulling ahead made a quieter change. They redefined the engineer's job.

**That job now has a name: AI-native engineering.**

---

### What it actually means

AI-native engineering is building production software by **directing AI agents** through clear specs, strong context, and disciplined verification — instead of typing most of the code yourself.

The engineer stops being the author and becomes the orchestrator.

Two things worth being precise about:

**1. "AI-native" describes the workflow, not the product.**
An AI-native engineer might build a payments system or a logistics dashboard that contains zero AI. The AI-native part is *how* it gets built.

**2. It is not vibe coding.**
Andrej Karpathy's term captured something real in early 2025: non-engineers can now build working software just by describing what they want. That's genuinely useful, and it's categorically different from professional engineering.

Vibe coding produces something that runs.
AI-native engineering produces something that survives production, scales, and doesn't leak customer data.

Knowing how to code is still the entry ticket — because you cannot verify what you cannot understand. Without that, you're not orchestrating the AI. You're trusting it and hoping.

---

### Why "more code" is not "more productivity"

Here's the part most dashboards get backwards.

A **METR randomised controlled trial** found experienced open-source developers were **19% slower** using AI assistants on codebases they knew well. The cause: over-reliance without verification. They accepted suggestions that looked right, then lost the saved time — and more — untangling what the model got subtly wrong.

A **Stanford study** found developers using AI assistants wrote *less* secure code while feeling *more* confident it was secure.

Lower quality plus higher confidence. That's exactly how bad code reaches production.

So the bottleneck has permanently moved. It used to be writing. Now AI writes the first draft in seconds and the rate-limiting step is **proving that draft works, safely, at scale**.

An AI-native engineer knows this in their bones. Raw output is a starting point to be interrogated, not a finished product to be merged.

---

### The ratio that gives it away

Shah Rahman, who leads autonomous ML iteration for Ads at Meta, offers a rule of thumb for how AI-native work actually distributes:

**40% context and specs → 20% generation → 40% review and verification.**

Twenty percent. That's the generation. Most developers are shocked by how small it is.

That ratio, more than any tool, is what the work feels like now.

---

### How to hire for it (without being an AI expert)

You don't need to be an AI expert to screen for this. You need to probe for **judgment**, not tool familiarity. Anyone can list "Claude Code" on a CV.

**Three questions that actually work:**

**1. "Walk me through an evaluation you designed for AI-generated work."**
Strong engineers have built evals or test harnesses. A vague answer usually means they've watched videos, not shipped.

**2. "Tell me about a time you rejected what the AI produced. Why?"**
You want a specific story. Willingness to override the model is the clearest sign of real judgment.

**3. "How do you decompose a task before handing parts of it to an agent?"**
Listen for spec-first thinking, and a clear line between what they delegate and what they keep.

**Green flags:** pushes back on AI output and explains why · designs evals to verify work · decomposes before delegating · can explain code the AI wrote, line by line · measures impact in shipped outcomes.

**Red flags:** accepts whatever the model suggests · treats "it ran" as proof it works · hands agents huge fuzzy tasks · can't explain their own pull request · measures impact in lines of code.

That last one deserves a name. I call it **the productivity mirage** — equating volume with value. In an AI-native world that's actively dangerous, because volume is now free and verification is the scarce resource.

---

### One correction on the hype

You've heard the prediction — including from Mark Zuckerberg — that AI agents will operate as mid-level engineers by the end of 2026.

Partly right, mostly hype. Agents do handle a large share of routine implementation, and that share is rising. But "mid-level engineer" implies ownership, judgment and accountability — and that's precisely the part that doesn't transfer.

AI amplifies expertise. It doesn't replace it. The senior engineers we place get dramatically more out of these tools *because* they bring sharper judgment to the orchestration.

The engineer isn't becoming obsolete. The job is being rebalanced toward what AI can't do: systems thinking, domain depth, and the call on what to keep or kill.

Good news for anyone hiring. The fundamentals you always valued still matter — you're just selecting for them at a higher altitude.

---

**So when you write your next job spec, screen for the right thing.** The engineer who pushes back on the model, designs evaluations, decomposes problems, and measures impact in shipped outcomes. Then move quickly, because that person won't stay on the market long.

**What's the strongest signal you've seen in an interview that someone genuinely orchestrates AI rather than just uses it? Curious what's working for other hiring managers.**

---

## Link placement (test, don't assume)

Reach on LinkedIn varies by account — treat placement as an experiment, not a rule. Four options, in the order I'd try them:

1. **No link in the article body.** Add the full blog post as the first comment ~10 minutes after publishing.
2. **Featured section / profile link.** Zero reach cost, lower click-through.
3. **Delayed edit.** Publish clean, add the link 1–2 hours in.
4. **Direct in-body link.** Use when traffic matters more than reach — e.g. a campaign week.

Full post: https://wise-step.ro/blog/ · CTA page: https://wise-step.ro/contact/

## Stats used (all source-backed from the original)

| Claim | Source |
|---|---|
| 19% slower with AI on familiar codebases | METR RCT — https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/ |
| Less secure code, higher confidence | Stanford — https://arxiv.org/abs/2211.03622 |
| 40/20/40 time budget | Shah Rahman (Meta), via original post |
| "Code overload" | The New York Times, April |
| "Vibe coding" coined early 2025 | Andrej Karpathy |
| Mid-level-engineer prediction | Mark Zuckerberg |

Omitted deliberately: the $200k salary / doubled-postings / three-week figures are US staffing-analysis numbers. They'd read as European claims in a LinkedIn feed. Left out rather than mis-framed.
