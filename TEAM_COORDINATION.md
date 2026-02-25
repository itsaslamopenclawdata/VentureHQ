# Team Coordination Protocol

How VentureHQ agents collaborate to deliver comprehensive venture analysis.

---

## 🏗️ Architecture Overview

VentureHQ is a **multi-agent system** built on OpenClaw, with each agent running as an independent session. Agents coordinate via Discord channels, sharing analysis and building on each other's work.

### Key Principles

1. **Specialization over generalization** — Each agent masters one dimension
2. **Explicit assumptions** — Every analyst shows their work
3. **Cross-validation** — Disagreements surface risks
4. **Hierarchical aggregation** — Specialists feed into final scorer
5. **Human-in-the-loop** — You control the flow and ask questions

---

## 🤖 Agent Specs

| Agent | Model | Specialization | Output Format |
|-------|-------|----------------|---------------|
| IdeaScoutBot | GLM-4 | Opportunity discovery | Trend analysis + confidence |
| ProblemDeepdiveBot | GLM-4 | Pain validation | Problem statement + severity score |
| MarketsizeBot | GLM-4 | Market quantification | TAM/SAM/SOM + growth CAGR |
| MoatDesignBot | GLM-4 | Defensibility analysis | Moat types + barriers rating |
| VenturescoreBot | GLM-4 | Venture scoring | 0-100 score + Go/No-Go |

---

## 🔄 Coordination Workflow

### Scenario 1: Quick Scoring (One-Shot)

```
User: "@VenturescoreBot Score: AI-powered dog walking app"

VenturescoreBot:
  → Spawns IdeaScoutBot (background)
  → Spawns ProblemDeepdiveBot (background)
  → Spawns MarketsizeBot (background)
  → Spawns MoatDesignBot (background)
  → Awaits all outputs
  → Aggregates and scores
  → Returns final verdict
```

**Time:** ~30-45 seconds (parallel execution)

### Scenario 2: Interactive Deep Dive

```
User: "@IdeaScoutBot Is now the time for AI pet care?"

IdeaScoutBot:
  → Analyzes timing, trends, competition
  → Returns assessment with evidence

User: "@ProblemDeepdiveBot What's the real pain?"

ProblemDeepdiveBot:
  → Validates problem urgency
  → Returns pain score + customer quotes (simulated)

User: "@MarketsizeBot How big?"

MarketsizeBot:
  → Runs TAM/SAM/SOM analysis
  → Returns market sizing with assumptions

User: "@MoatDesignBot Can we defend it?"

MoatDesignBot:
  → Analyzes moats and barriers
  → Returns defensibility rating

User: "@VenturescoreBot Final score?"

VenturescoreBot:
  → Synthesizes all inputs
  → Returns final 0-100 score
```

**Time:** 5-10 minutes (conversational)

---

## 📋 Agent Output Schema

Each specialist follows a structured output format for aggregation:

### IdeaScoutBot Output

```json
{
  "timing_assessment": "Early/mature/saturated",
  "confidence": 0-100,
  "key_trends": ["trend1", "trend2"],
  "founder_market_fit": "high/med/low",
  "timing_score": 0-100
}
```

### ProblemDeepdiveBot Output

```json
{
  "problem_statement": "...",
  "urgency_score": 0-100,
  "frequency_score": 0-100,
  "severity_score": 0-100,
  "willingness_to_pay": "$XX/mo or $XX one-time",
  "problem_score": 0-100
}
```

### MarketsizeBot Output

```json
{
  "tam_usd": 1234567890,
  "sam_usd": 123456789,
  "som_usd": 12345678,
  "growth_cagr": 0.25,
  "market_maturity": "emerging/growing/mature",
  "market_score": 0-100
}
```

### MoatDesignBot Output

```json
{
  "network_effects": "strong/weak/none",
  "data_advantage": "yes/no/partial",
  "switching_costs": "high/med/low",
  "brand_moat": "existing/buildable/none",
  "barriers_to_entry": ["barrier1", "barrier2"],
  "moat_score": 0-100
}
```

### VenturescoreBot Output

```json
{
  "final_score": 75,
  "breakdown": {
    "timing": 80,
    "problem": 70,
    "market": 75,
    "moat": 70,
    "execution": 80
  },
  "decision": "Go / Conditional Go / No-Go",
  "confidence": 0-100,
  "key_risks": ["risk1", "risk2"],
  "recommendation": "..."
}
```

---

## 🔗 Inter-Agent Communication

### Method 1: Discord Mentions (Interactive)

```
@IdeaScoutBot <query>
→ Agent replies in channel
→ Other agents can reference
→ Human can follow up
```

### Method 2: sessions_spawn (Parallel)

```
VenturescoreBot spawns 4 sub-agents:
  → sessions_spawn(agent=IdeaScoutBot, task=...)
  → sessions_spawn(agent=ProblemDeepdiveBot, task=...)
  → sessions_spawn(agent=MarketsizeBot, task=...)
  → sessions_spawn(agent=MoatDesignBot, task=...)
→ Polls until all complete
→ Aggregates results
```

### Method 3: sessions_send (Cross-Agent)

```
IdeaScoutBot sends to ProblemDeepdiveBot:
  → sessions_send(agent=ProblemDeepdiveBot, message="...")
→ ProblemDeepdiveBot responds with deep-dive
→ Human sees conversation unfold
```

---

## 🎯 Scoring Algorithm

VenturescoreBot uses a **weighted linear model** with adjustments:

```python
def calculate_venture_score(
    timing_score: float,
    problem_score: float,
    market_score: float,
    moat_score: float,
    execution_score: float
) -> tuple[float, str]:
    """Returns (score_0_100, decision)"""

    # Weights (sum to 1.0)
    weights = {
        'timing': 0.15,
        'problem': 0.20,
        'market': 0.20,
        'moat': 0.25,
        'execution': 0.20
    }

    # Base score
    base_score = (
        timing_score * weights['timing'] +
        problem_score * weights['problem'] +
        market_score * weights['market'] +
        moat_score * weights['moat'] +
        execution_score * weights['execution']
    )

    # Risk adjustment
    # If any dimension < 30, penalize heavily
    if min(timing_score, problem_score, market_score, moat_score, execution_score) < 30:
        base_score *= 0.7

    # Bonus for strong moats (defensibility multiplier)
    if moat_score > 80:
        base_score *= 1.1

    # Decision thresholds
    if base_score >= 80:
        decision = "Go — Strong conviction"
    elif base_score >= 60:
        decision = "Conditional Go — Investigate further"
    elif base_score >= 40:
        decision = "Likely No-Go — Major red flags"
    else:
        decision = "Hard No — Don't waste time"

    return (min(100, base_score), decision)
```

---

## 🧪 Testing & Validation

### Unit Tests

Each agent's scoring should be validated:

```
IdeaScoutBot:
  → Known good ideas should score > 70
  → Known saturated markets should score < 40

MarketsizeBot:
  → Known billion-dollar markets should calculate correctly
  → Small niches should flag as "niche market"

MoatDesignBot:
  → Network effect businesses should identify moats
  → Commodity products should flag "no moat"
```

### Integration Tests

Full workflow tests:

```
Test Case 1: Strong Venture (e.g., Stripe in 2011)
  → Should score > 80 and return "Go"

Test Case 2: Weak Venture (e.g., yet another social network)
  → Should score < 40 and return "Hard No"

Test Case 3: Edge Case (e.g., early-stage, high-risk)
  → Should return "Conditional Go" with clear risks
```

---

## 📈 Performance Metrics

Track these KPIs:

| Metric | Target | Current |
|--------|--------|---------|
| Analysis time (quick score) | < 60s | TBD |
| Analysis time (deep dive) | < 10m | TBD |
| Agent agreement rate | 60-80% (healthy disagreement) | TBD |
| User satisfaction | > 4/5 | TBD |
| False positive rate (bad ventures rated high) | < 10% | TBD |
| False negative rate (good ventures rated low) | < 15% | TBD |

---

## 🔄 Continuous Improvement

### Learning Loop

1. **Track outcomes** — When a venture is built, what happened?
2. **Compare predictions** — Did our score match reality?
3. **Adjust weights** — If timing consistently under-predicts, increase weight
4. **Update knowledge** — Agents learn from market outcomes

### Human Feedback

When you tell us "we got this wrong," we:

- Log the case for analysis
- Identify which dimension failed
- Adjust scoring criteria
- Test against similar cases

---

## 🛡️ Safety & Ethics

### What We Won't Do

- Evaluate illegal ventures
- Recommend harmful products
- Exploit psychological vulnerabilities
- Make financial guarantees (we analyze, not predict)

### Disclosure

We're AI, not VCs. Our analysis is for exploration and learning, not investment advice. Always do your own diligence.

---

## 📚 References

- **Benchmark Ventures Database** — Historical cases with actual outcomes
- **VC Scoring Frameworks** — a16z, Sequoia, YC evaluation criteria
- **Market Sizing Methodologies** — TAM/SAM/SOM best practices
- **Moat Theory** — Warren Buffett, Hamilton Helmer (7 Powers)

---

**Last Updated:** 2025-02-17
**Version:** 1.0
