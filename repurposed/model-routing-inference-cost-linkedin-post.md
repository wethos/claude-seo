# LinkedIn Feed Post — Model routing

**Format:** LinkedIn feed post (English)
**Author voice:** Calin Muresan, first person
**Source:** "Model routing: the AI cost skill to hire for in 2026" — https://wise-step.ro/blog/model-routing-inference-cost/ (September 14, 2026)
**Image:** attach the blog hero (`seomachine/drafts/model-routing-inference-cost/hero.png`, 1200×630) or the chart "Four figures, four denominators"

**Alt hooks (swap into the first two lines to A/B test):**
- "You cut AI cost by 50%. Per what?" is now my favorite interview question.
- Picking an AI model used to be a vendor decision. In 2026 it's an engineering skill, and it shows up on the P&L.

---

## Post (copy from here)

Three companies published AI cost numbers in August. The easy summary: "open models cut the bill in half."

That's not what the sources say. And the gap is exactly what you should be hiring for.

Uber: cost per 1,000 model requests down ~34%. Cost per session down 52% from its June peak. Same post, two numbers.

AT&T: coding and some other advanced AI tasks up to 56% cheaper, with a measured 2% quality drop.

Pinterest: open models running at under 8% of the cost per transaction of comparable closed models.

Four figures. Four denominators. One direction.

The skill behind them has a name: model routing. Send each request to the cheapest model that clears the quality bar. Open-weight for simple, low-risk work. Frontier for hard reasoning.

What I took from reading the primary sources the way I would have as an engineer:

1. A cost figure without a denominator is not a result. Per request, per session, per transaction, and total spend can move in different directions in the same quarter.

2. It's three skills, not one. Routing and caching belong with platform and applied AI engineers. Post-training open models is a separate ML search.

3. No saving without an eval. AT&T's 2% is the kind of number a serious engineer brings with them.

4. You probably don't need a new "AI FinOps engineer" title. Uber's post describes cost levers built into engineering work and doesn't mention a separate cost team.

The interview question I'd start with:

"You cut AI cost by 50%. Per what?"

Strong candidates name the metric, the baseline, and what total spend did. Weak ones say "our bill went down."

"Model routing" is a new label, so it won't show up on CVs. You find it by asking.

Full breakdown, with the comparison table, the job-spec lines that work, and five screening questions:
https://wise-step.ro/blog/model-routing-inference-cost/

If you've moved workloads off frontier models: what did you measure quality against?

#AIEngineering #LLMOps #EngineeringLeadership #TechRecruitment #Hiring

---

## Link placement

You asked for the article link, so it's in the body. LinkedIn reach with in-body links varies by account; if reach matters more than clicks on a given week, test this instead:

1. Post without the "Full breakdown…" line and URL.
2. Add as first comment ~10 minutes after publishing: "Full breakdown with the comparison table, job-spec lines, and five screening questions: https://wise-step.ro/blog/model-routing-inference-cost/"

## Stats used (all verified against primary sources, September 14, 2026)

| Claim | Source |
|---|---|
| Uber cost per 1,000 requests ~34% below peak; cost per session −52% from June peak | Uber Engineering, Aug 27, 2026 — https://www.uber.com/gb/en/blog/efficient-software-factory/ |
| AT&T up to 56% on coding and some other advanced AI tasks; 2% quality decline | The Information via PYMNTS, Aug 20, 2026 — https://www.pymnts.com/news/artificial-intelligence/2026/att-slashes-ai-costs-by-adopting-model-routers-and-open-source/ |
| Pinterest cost per transaction under 8% of comparable closed models | Pinterest Q2 2026 earnings call, Aug 4, 2026 — https://www.fool.com/earnings/call-transcripts/2026/08/11/pinterest-pins-q2-2026-earnings-call-transcript/ |
| Uber post doesn't mention a separate cost team | Uber Engineering post (absence, stated as such) |

Omitted deliberately: the $0.30/$2.50 per-review prices (secondhand via The Pragmatic Engineer), the State of FinOps 98% stat, and the Romanian pay ranges. Each adds a number without strengthening the hook; they stay in the article.
