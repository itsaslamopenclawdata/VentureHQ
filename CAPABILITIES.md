# VentureHQ Team Capabilities

Detailed breakdown of each bot's expertise and output formats.

---

## 🎯 IdeaScoutBot

### Mission
Discover and validate promising venture opportunities by screening for market fit, timing, and potential.

### Core Capabilities

**Market Opportunity Screening:**
- Identify untapped market gaps and white spaces
- Analyze timing and trend alignment (early/late/right now)
- Assess market saturation and competitive density
- Evaluate adjacent market expansion opportunities

**Idea Validation:**
- Founder-market fit assessment
- Resource requirement analysis (team, capital, time)
- Regulatory and legal risk screening
- Technology feasibility evaluation

**Trend Analysis:**
- Emerging technology identification
- Societal shift detection (work habits, consumer behavior)
- Industry disruption potential
- Macroeconomic alignment

### Output Format

```
Opportunity: [Idea Name]
Screening Score: X.X/10

Strengths:
• [List of validated strengths]
• [Evidence or data points]

Risks & Concerns:
• [Potential blockers or challenges]
• [Mitigation strategies]

Market Timing: [TOO EARLY / RIGHT NOW / TOO LATE]

Verdict: [WORTH EXPLORING / PROCEED WITH CAUTION / SKIP]
```

### Example Questions
- "Is now the right time for a climate-tech startup?"
- "What markets are ripe for AI disruption?"
- "Evaluate this idea: [concept]"

---

## 🔍 ProblemDeepdiveBot

### Mission
Deep-dive into customer pain points to validate real problems worth solving.

### Core Capabilities

**Problem Analysis:**
- Urgency and frequency of pain
- Emotional vs. functional pain drivers
- Problem frequency and reach (how many, how often)
- Customer segments experiencing the problem

**Validation Framework:**
- Willingness-to-pay assessment
- Alternative solutions (substitutes, workarounds)
- Switching costs and friction
- Problem-market fit scoring

**Customer Insights:**
- Pain point severity scales
- Job-to-be-done mapping
- Value proposition alignment
- Customer journey pain mapping

### Output Format

```
Problem: [Problem Statement]
Validation Score: X.X/10

Pain Analysis:
├── Urgency: [LOW / MEDIUM / HIGH]
├── Frequency: [RARE / OCCASIONAL / FREQUENT / CONSTANT]
├── Emotional Impact: [1-10]
└── Functional Impact: [1-10]

Customer Segments:
• [Segment 1]: [Pain level, frequency]
• [Segment 2]: [Pain level, frequency]

Alternative Solutions:
• [Existing solution 1]: [Effectiveness, adoption]
• [Existing solution 2]: [Effectiveness, adoption]

Willingness-to-Pay: [LOW / MEDIUM / HIGH]
Price Sensitivity: $X-$Y range

Verdict: [REAL PROBLEM / NICE-TO-HAVE / NOT A PROBLEM]
```

### Example Questions
- "How painful is posture-related back pain for remote workers?"
- "Validate this problem: [customer pain description]"
- "What are people currently doing to solve this?"

---

## 📊 MarketSizeBot

### Mission
Calculate TAM, SAM, and SOM with data-driven analysis, assumptions, and growth benchmarks.

### Core Capabilities

**Market Sizing:**
- Total Addressable Market (TAM) — global opportunity
- Serviceable Available Market (SAM) — reachable segment
- Serviceable Obtainable Market (SOM) — realistic capture
- Bottom-up and top-down sizing approaches

**Growth Analysis:**
- Market CAGR projections (3-5 year)
- Growth drivers and catalysts
- Market maturity assessment (emerging / growth / mature / declining)
- Adoption curve positioning

**Market Segmentation:**
- Geographic market sizing (US, EU, APAC, Global)
- Customer segment sizing (enterprise, SMB, consumer)
- Product line or feature market sizing
- Use case market sizing

### Output Format

```
Market: [Market Name]
Geography: [US / EU / Global / Custom]

Market Sizing:
├── TAM: $X.XB (Year) → $X.XB (Year + N) [CAGR: X.X%]
├── SAM: $X.XB (reachable segment)
└── SOM: $XM → $XM → $XM (Year 1-3 capture)

Assumptions:
• [Assumption 1]: [Justification/data source]
• [Assumption 2]: [Justification/data source]
• [Assumption 3]: [Justification/data source]

Growth Drivers:
• [Driver 1]: [Impact level]
• [Driver 2]: [Impact level]

Market Position: [EARLY / GROWTH / MATURE / DECLINING]

Confidence: [LOW / MEDIUM / HIGH]
Key Data Sources: [List of sources]
```

### Example Questions
- "What's the TAM for corporate wellness apps?"
- "Size the market for AI-powered fitness coaching"
- "How big is the B2B SaaS market for mid-market?"

---

## 🏰 MoatDesignBot

### Mission
Design and evaluate sustainable competitive advantages and barriers to entry.

### Core Capabilities

**Moat Analysis:**
- Network effects (direct, indirect, two-sided)
- Switching costs (data, workflow, integration)
- Economies of scale and scope
- Brand and customer lock-in

**IP & Technology:**
- Patent defensibility
- Proprietary datasets or algorithms
- Trade secret potential
- Technical complexity as barrier

**Distribution & Supply Chain:**
- Exclusive partnerships
- Supply chain control
- Distribution channel dominance
- Regulatory or certification moats

**Competitive Positioning:**
- First-mover vs. fast-follower
- Competitive landscape mapping
- Barriers to entry for new entrants
- Incumbent threat assessment

### Output Format

```
Moat Assessment: [Venture Name]
Moat Strength: X.X/10

Identified Moats:
• [Moat Type]: [Strength 1-10, sustainability]
├── How it works: [Mechanism]
├── Defensibility: [Time/effort to replicate]
└── Risk factors: [Potential erosion]

Moat Architecture:
├── Network Effects: [YES / NO] → [Details]
├── Switching Costs: [LOW / MEDIUM / HIGH]
├── IP Position: [WEAK / MODERATE / STRONG]
└── Scale Advantage: [YES / NO]

Barrier to Entry: [LOW / MEDIUM / HIGH]
Time to Replicate: [X months / years]

Competitive Threats:
• [Threat 1]: [Risk level, mitigation]
• [Threat 2]: [Risk level, mitigation]

Moat Roadmap:
• [Year 1]: [Moat-building milestone]
• [Year 2]: [Moat-building milestone]
• [Year 3]: [Moat-building milestone]
```

### Example Questions
- "What moats can we build in AI fitness coaching?"
- "Analyze the competitive advantage of [product/idea]"
- "How defensible is this business model?"

---

## 🎯 VenturescoreBot

### Mission
Aggregate all analyses into investment-grade scoring with Go/No-Go recommendations.

### Core Capabilities

**Scoring Model:**
- Weighted scoring across all dimensions (idea, problem, market, moat)
- Confidence level calculation based on data quality
- Risk assessment and red flag identification
- Investment decision framework

**Decision Output:**
- Go/No-Go recommendation
- Critical path for execution
- Risk mitigation strategies
- Deal breaker identification

**Comparative Analysis:**
- Multiple venture ranking and comparison
- Scenario analysis (what-if modeling)
- Sensitivity testing on key assumptions

### Output Format

```
Venture Score: X/100
Confidence: [LOW / MEDIUM / HIGH / VERY HIGH]

Dimension Breakdown:
├── Idea Quality: XX/100 [✅/⚠️/❌]
│   • [Key insight 1]
│   • [Key insight 2]
├── Problem Validation: XX/100 [✅/⚠️/❌]
│   • [Key insight 1]
│   • [Key insight 2]
├── Market Size: XX/100 [✅/⚠️/❌]
│   • TAM: $XB, Growth: X% CAGR
│   • [Key insight 2]
└── Moat Strength: XX/100 [✅/⚠️/❌]
    • [Key insight 1]
    • [Key insight 2]

Risk Profile: [LOW / MODERATE / HIGH / VERY HIGH]
Red Flags:
• [Flag 1]: [Severity]
• [Flag 2]: [Severity]

Decision: [GO / GO WITH CONDITIONS / NO-GO]

Critical Path (if GO):
1. [Immediate action needed]
2. [Short-term milestone]
3. [Long-term milestone]

Investment Thesis:
[1-2 sentence summary of why this works (or doesn't)]
```

### Example Questions
- "Score this venture: [full idea description]"
- "Compare these two ideas: [Idea A] vs [Idea B]"
- "What would improve the score by 10 points?"

---

## 🤝 Bot Coordination

### Sequential Workflow
When using `@everyone`, bots respond in this order:
1. IdeaScoutBot → ProblemDeepdiveBot → MarketSizeBot → MoatDesignBot → VenturescoreBot

Each bot reads previous outputs to build context-aware analysis.

### Cross-Bot References
Bots can reference each other's work:
```
@MarketSizeBot Given IdeaScoutBot's 8.2/10 score, what's the market size?
```

```
@VenturescoreBot If we double the Moat strength to 80/100, what's the new score?
```

---

## 📈 Quality & Confidence

### Confidence Levels
- **HIGH** — Multiple reliable data sources, low variance
- **MEDIUM** — Good data sources, some assumptions required
- **LOW** — Limited data, high uncertainty

### Scoring Accuracy
Team is designed for:
- **Early-stage screening** (70-80% accuracy)
- **Directional guidance** (good for comparing opportunities)
- **Due diligence acceleration** (not a replacement for deep research)

### When to Trust the Output
- ✅ Idea generation and screening
- ✅ Initial market sizing (within 2x accuracy)
- ✅ Competitive positioning guidance
- ⚠️ Exact revenue projections (use as starting point)
- ⚠️ Final investment decision (combine with human judgment)

---

**Know what you need? Jump to the relevant bot or use @everyone for full analysis!** 🚀
