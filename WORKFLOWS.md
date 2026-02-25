# VentureHQ Workflows

Common patterns for using the VentureHQ team.

---

## 🚀 Workflow 1: Quick Venture Score

**Use when:** You have an idea and want a fast verdict.

**Steps:**

1. Mention VenturescoreBot with your idea:
   ```
   @VenturescoreBot Score this venture: [your idea]
   ```

2. VenturescoreBot spawns specialists in parallel

3. Wait 30-60 seconds

4. Receive:
   - Final score (0-100)
   - Go/No-Go decision
   - Dimension breakdown
   - Key risks

**Example:**

```
@VenturescoreBot Score: AI-powered nutrition coaching that scans grocery receipts and suggests meal plans
```

**Result:**
```
Final Score: 72/100
Decision: Conditional Go

Breakdown:
- Timing: 75 (good, market growing)
- Problem: 70 (real pain, but crowded)
- Market: 65 (niche but meaningful)
- Moat: 60 (data advantage but low barriers)
- Execution: 85 (feasible, clear path)

Key Risks:
- Many incumbents in meal planning
- User engagement is the hard part
- Data collection friction

Recommendation: Validate user retention before investing heavily.
```

---

## 🔬 Workflow 2: Deep Dive Investigation

**Use when:** You want to understand every dimension and ask follow-ups.

**Steps:**

1. Start with IdeaScoutBot:
   ```
   @IdeaScoutBot Is now the right time to build [idea]?
   ```

2. Review timing assessment, ask follow-ups

3. Move to ProblemDeepdiveBot:
   ```
   @ProblemDeepdiveBot What's the real customer pain here?
   ```

4. Validate problem, explore edge cases

5. Size the market:
   ```
   @MarketsizeBot What's the TAM/SAM/SOM for this?
   ```

6. Review assumptions, adjust numbers

7. Assess defensibility:
   ```
   @MoatDesignBot How do we protect this business?
   ```

8. Brainstorm moats, evaluate barriers

9. Get final score:
   ```
   @VenturescoreBot Pull it all together — what's the verdict?
   ```

**Time:** 10-20 minutes of interactive conversation

**Benefits:**
- You control the pace
- Deep understanding of each dimension
- Can challenge assumptions
- Learn along the way

---

## 🌊 Workflow 3: Market Scan

**Use when:** You want to find opportunities in an industry.

**Steps:**

1. Ask IdeaScoutBot for landscape:
   ```
   @IdeaScoutBot What are the most promising opportunities in [industry] right now?
   ```

2. Get 3-5 potential ideas

3. For each idea, quick score:
   ```
   @VenturescoreBot Score [idea #1], [idea #2], [idea #3]
   ```

4. Compare scores

5. Deep dive the top 1-2

**Example:**

```
@IdeaScoutBot What's hot in climate tech?

IdeaScoutBot:
1. AI for carbon accounting
2. EV charging infrastructure analytics
3. Renewable energy grid optimization
4. Sustainable packaging materials
5. Climate risk insurance

@VenturescoreBot Score the top 3

VenturescoreBot:
1. AI for carbon accounting: 78 (Conditional Go)
2. EV charging analytics: 65 (Conditional Go)
3. Grid optimization: 82 (Strong Go)

→ Deep dive grid optimization
```

---

## 🔄 Workflow 4: Iterative Refinement

**Use when:** You have a rough idea and want to refine it into something stronger.

**Steps:**

1. Start with your rough idea:
   ```
   @VenturescoreBot Score: A todo app with gamification
   ```

2. Likely result: Low score (saturated, low moat)

3. Ask: "What would make this a 80+ venture?"

4. Pivot based on feedback:
   ```
   @VenturescoreBot Score: A gamified habit-tracker specifically for people recovering from addiction, with community support and evidence-based behavioral science
   ```

5. Likely result: Higher score (niche market, strong problem, community moat)

6. Iterate 3-4 times until score stabilizes

7. Commit to the refined idea

**Pattern:** Start generic → Go niche → Find edge case → Build for specific user → Score improves

---

## ⚔️ Workflow 5: Competitive Analysis

**Use when:** You're evaluating against an existing startup.

**Steps:**

1. Identify the competitor
2. Ask IdeaScoutBot:
   ```
   @IdeaScoutBot What's the weakness in [competitor]'s positioning?
   ```

3. Ask ProblemDeepdiveBot:
   ```
   @ProblemDeepdiveBot What customer pain is [competitor] not solving?
   ```

4. Ask MoatDesignBot:
   ```
   @MoatDesignBot How can we build a moat against [competitor]?
   ```

5. Ask MarketsizeBot:
   ```
   @MarketsizeBot Is there enough market for both of us?
   ```

6. Decide: compete or pivot

**Key question:** Can you be meaningfully different?

---

## 📊 Workflow 6: Pre-Pitch Validation

**Use when:** You're preparing to pitch investors and want to validate your case.

**Steps:**

1. Submit your full pitch to VenturescoreBot:
   ```
   @VenturescoreBot Score this venture (full pitch):
   [Problem, Solution, Market, Competition, Traction, Team]
   ```

2. Get score and breakdown

3. For any dimension scoring < 70, ask:
   ```
   @[SpecialistBot] Help me strengthen this: [weak area]
   ```

4. Iterate until all dimensions > 70

5. Use the breakdown in your pitch deck:
   - "We score 82 on market size..."
   - "Our moat is built on..."

**Investor response:** "This is the most data-driven pitch I've seen."

---

## 🎯 Workflow 7: Pivot Evaluation

**Use when:** Your startup is struggling and you're considering a pivot.

**Steps:**

1. Describe your current situation:
   ```
   @VenturescoreBot Current state: [what you're building, why it's not working]
   ```

2. Get current venture score (likely low)

3. Brainstorm 3 pivot directions with IdeaScoutBot:
   ```
   @IdeaScoutBot Given our assets [describe], what are 3 good pivots?
   ```

4. Quick score each pivot

5. Deep dive the top 1-2

6. Make a data-informed decision

**Pivot checklist:**
- Leverages existing assets (users, tech, data)
- Higher market score?
- Stronger moat potential?
- Better timing?

---

## 🧪 Workflow 8: Hypothesis Testing

**Use when:** You want to test a specific assumption.

**Steps:**

1. State your hypothesis:
   ```
   If we add [feature], we can capture [market segment]
   ```

2. Ask MarketsizeBot:
   ```
   @MarketsizeBot How big is [market segment]?
   ```

3. Ask ProblemDeepdiveBot:
   ```
   @ProblemDeepdiveBot Does [market segment] have this pain?
   ```

4. Ask MoatDesignBot:
   ```
   @MoatDesignBot Does [feature] create a moat?
   ```

5. Get VenturescoreBot's view:
   ```
   @VenturescoreBot Does this hypothesis improve the venture score?
   ```

6. Decide: test or discard

---

## 🤝 Workflow 9: Co-Founder Compatibility

**Use when:** Evaluating if a team can execute the venture.

**Note:** VenturescoreBot's "execution" dimension looks at:
- Team experience
- Technical feasibility
- Resource requirements
- Execution risk

**Steps:**

1. Submit your team + idea:
   ```
   @VenturescoreBot Score: [idea]
   Team: [brief backgrounds]
   ```

2. Focus on execution score

3. If low (< 60), ask:
   ```
   @VenturescoreBot What's missing from the team?
   ```

4. Use output as hiring criteria

**Reality check:** Execution score is the hardest to improve quickly. Be honest.

---

## 📈 Workflow 10: Portfolio Management

**Use when:** You're running multiple projects and need to prioritize.

**Steps:**

1. List all your active ideas/projects

2. Quick score each:
   ```
   @VenturescoreBot Score [project 1], [project 2], [project 3], [project 4]
   ```

3. Create a matrix:
   ```
   High Score + High Urgency → Do now
   High Score + Low Urgency → Schedule
   Low Score + High Urgency → Pivot or kill
   Low Score + Low Urgency → Kill
   ```

4. Kill or pause low-scoring projects
5. Double down on top 1-2

**Rule of thumb:** 1-2 projects max at any time

---

## 🛠️ Workflow: Custom Agent Orchestration

**Advanced:** For complex research, combine agents beyond the core 5.

**Example: Deep due diligence**

```
1. IdeaScoutBot — Opportunity landscape
2. ProblemDeepdiveBot — Pain validation
3. MarketsizeBot — Market sizing
4. MoatDesignBot — Defensibility
5. VenturescoreBot — Final score
6. [Custom] CompetitorAnalysisBot — Deep competitor research
7. [Custom] TechFeasibilityBot — Technical complexity
8. [Custom] FinancialModelBot — Build financial model
9. VenturescoreBot — Re-score with additional inputs
```

---

## 🎓 Learning from Each Workflow

After each workflow, VenturescoreBot logs:
- What you asked
- What the score was
- What you decided
- (Optional) What the outcome was

Over time, this becomes your decision history. Review it quarterly to:
- Spot patterns in your judgment
- See which scores were accurate
- Improve your venture instincts

---

**Pick a workflow. Try it. Tell us how it goes.** 🚀
