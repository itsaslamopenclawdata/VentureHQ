# Contributing to VentureHQ

VentureHQ is a coordinated AI agent team. Here's how to contribute.

---

## 📋 What We Document

### Documentation Types
- **Core Docs:** README, QUICKSTART, CAPABILITIES (maintained by team)
- **Examples:** Real venture evaluations (add to `examples/` directory)
- **Templates:** Structured output formats (add to `templates/` directory)
- **Research:** Market data sources and benchmarks (add to `research/` directory)

---

## 🚀 Adding Examples

We love real-world examples! Structure yours like this:

### Example File Structure
```
examples/
└── ai-fitness-coaching/
    ├── README.md                  # High-level overview
    ├── idea-scout-output.md       # IdeaScoutBot analysis
    ├── problem-deepdive-output.md # ProblemDeepdiveBot analysis
    ├── market-size-output.md      # MarketSizeBot analysis
    ├── moat-design-output.md      # MoatDesignBot analysis
    └── venturescore-output.md     # VenturescoreBot final verdict
```

### Example Template

```markdown
# Example: [Venture Name]

**Date:** YYYY-MM-DD
**Submitted By:** @username
**Final Score:** XX/100
**Decision:** [GO / GO WITH CONDITIONS / NO-GO]

---

## Idea Summary
[2-3 sentence description of the venture]

---

## Team Analysis
[Links to individual bot outputs]

---

## Key Learnings
[What this example teaches about venture evaluation]

---

## Follow-Up
[Did the venture succeed? Any updates?]
```

---

## 📊 Adding Research Data

### Market Benchmarks
```
research/
├── market-sizes/
│   ├── corporate-wellness.md
│   ├── saas-pricing.md
│   └── ai-markets.md
└── cagr-benchmarks/
    ├── industry-cagr.md
    └── geographic-growth.md
```

### Format for Market Data
```markdown
# [Market Name] Market Size

**Last Updated:** YYYY-MM-DD
**Source:** [Link to source]

## Market Size
- TAM: $XB (Year)
- CAGR: X.X% (Year-YYYY)

## Key Drivers
1. [Driver 1]
2. [Driver 2]

## Segmentation
- [Segment 1]: $XB
- [Segment 2]: $XB

## Sources
1. [Source 1 with link]
2. [Source 2 with link]
```

---

## 🤝 How to Contribute

### Submitting Examples
1. Collect the bot outputs (screenshots or text)
2. Format using the template above
3. Submit as PR to `examples/` directory

### Adding Research
1. Verify data from credible sources
2. Document sources and dates
3. Submit as PR to `research/` directory

### Improving Documentation
1. Clear issue describing what needs improvement
2. Submit PR with proposed changes
3. We'll review and merge

---

## 🐛 Bug Reports

Found an issue with a bot's analysis? Report it:

**Issue Template:**
```
Bot: [Which bot]
Issue: [What went wrong]
Example Input: [What you asked for]
Expected Output: [What should have happened]
Actual Output: [What you got]
```

---

## 💡 Feature Requests

Ideas for improving VentureHQ?

**Request Template:**
```
Feature: [What you want]
Use Case: [Why it's valuable]
Proposed Implementation: [How it could work]
```

---

## 📜 License

By contributing, you agree your contributions are MIT-licensed.

---

## 📞 Questions?

- Open an issue
- Join the Discord: #venture-collab
- Mention @MarketSizeBot

---

**Thanks for making VentureHQ better!** 🙌
