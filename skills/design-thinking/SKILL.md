---
name: design-thinking
description: Guide users through human-centered design thinking for product features, systems, dashboards, and architecture decisions. Use when user wants to design a new feature, rethink a user flow, plan a dashboard, architect a system from the user's perspective, or explicitly invokes /dt. Triggers on "design thinking", "user needs", "empathize", "how should we design", "what should the UX be", or /dt commands.
---

# Design Thinking Skill

A structured, iterative framework for human-centered problem solving. Use this to move from "what should we build?" to "here's why we're building this, for whom, and how we'll validate it" — before writing code.

## Commands

| Command | Stage | What it does |
|---------|-------|-------------|
| `/dt` | Full | Walk through all 5 stages for a feature, system, or product |
| `/dt empathize` | 1 | User research: personas, pain points, context mapping |
| `/dt define` | 2 | Synthesize a clear problem statement (HMW format) |
| `/dt ideate` | 3 | Structured brainstorm with constraint-breaking and prioritization |
| `/dt prototype` | 4 | Generate specs, wireframes, or code prototypes |
| `/dt test` | 5 | Create test plans, feedback frameworks, success metrics |
| `/dt audit` | Review | Audit an existing feature/page against DT principles |

## Stage 1: Empathize

**Goal:** Understand the real humans who will use this thing.

### Process

1. **Identify the user(s).** Ask:
   - Who are the primary users? (Be specific — "busy professionals learning Korean" not "users")
   - What's their context? (Device, time of day, emotional state, environment)
   - What are they trying to accomplish? (Job-to-be-done, not feature request)

2. **Map pain points.** For each user type, identify:
   - Current frustrations (what's broken or missing today?)
   - Workarounds they use (reveals unmet needs)
   - Emotional friction (confusion, anxiety, boredom, overwhelm)

3. **Build an empathy map.** Output as a structured artifact:

```
EMPATHY MAP: [User Type]
--------------------------
THINKS: What occupies their mind? What matters to them?
FEELS:  What emotions drive their behavior? What worries them?
SAYS:   What do they tell others about this problem?
DOES:   What actions do they take? What workarounds exist?
PAIN:   Frustrations, obstacles, risks they face
GAIN:   What would success look like for them?
```

4. **Contextual factors.** Consider:
   - Technical literacy level
   - Language/cultural context (critical for multilingual projects)
   - Accessibility needs
   - Frequency of use (daily vs. occasional)

### Output
Deliver: 1-3 empathy maps + a pain point priority list ranked by severity and frequency.

## Stage 2: Define

**Goal:** Turn empathy insights into a crisp, actionable problem statement.

### Process

1. **Synthesize insights** from Stage 1 into themes. Group related pain points.

2. **Write a "How Might We" (HMW) statement:**

```
How might we [action/change]
for [specific user]
so that [desired outcome]
without [key constraint to respect]?
```

**Good example:**
> How might we help busy professionals maintain daily Korean practice so that they build lasting habits without requiring more than 10 minutes per session?

**Bad example:**
> How might we make the app better? (too vague)

3. **Define success criteria.** What does "solved" look like?
   - User behavior change (measurable)
   - Business metric impact
   - Emotional outcome ("feels confident" → measured via NPS/survey)

4. **Scope check.** Is this:
   - Too broad? → Split into sub-problems
   - Too narrow? → Zoom out to the real need
   - Already solved elsewhere? → Study existing solutions first

### Output
Deliver: HMW statement + 3-5 measurable success criteria + scope assessment.

## Stage 3: Ideate

**Goal:** Generate diverse solutions before converging on the best approach.

### Process

1. **Diverge first.** Generate 8-12 ideas without judgment. Use these prompts:
   - "What if we had unlimited budget?"
   - "What if the user could only use this on mobile?"
   - "What would the competitor's version look like?"
   - "What's the simplest possible version?"
   - "What if we removed [core assumption]?"
   - "How would [analogous industry] solve this?"

2. **Challenge assumptions.** List 3-5 assumptions baked into the current thinking. For each, ask: "What if this isn't true?"

3. **Prioritize using Impact/Effort matrix:**

```
HIGH IMPACT
    |
    |  Quick Wins    |  Big Bets
    |  (DO FIRST)    |  (PLAN)
    |________________|________________
    |                |
    |  Fill-ins      |  Money Pits
    |  (MAYBE)       |  (AVOID)
    |
    LOW IMPACT -----------> HIGH EFFORT
```

4. **Select 2-3 candidates** to prototype. For each, note:
   - Why this idea (link back to HMW)
   - Key risk/assumption to validate
   - Minimum viable version

### Output
Deliver: Idea list + assumption challenges + prioritization matrix + 2-3 selected candidates with rationale.

## Stage 4: Prototype

**Goal:** Make ideas tangible enough to test, with minimum effort.

### Process

1. **Choose fidelity level** based on what you're validating:

| Fidelity | When to use | Format |
|----------|------------|--------|
| Low | Validating concept/flow | Text description, ASCII wireframe, bullet-point spec |
| Medium | Validating layout/interaction | Component spec with props, Figma description, HTML mockup |
| High | Validating feasibility/performance | Working code prototype, API stub, database schema |

2. **For UI/UX prototypes**, describe:
   - Page/screen layout (what appears where)
   - User flow (step-by-step interaction sequence)
   - Key states (empty, loading, error, success, edge cases)
   - Content hierarchy (what's most important visually)

3. **For system/architecture prototypes**, describe:
   - Data flow diagram
   - API contract (endpoints, request/response shapes)
   - State management approach
   - Integration points with existing systems

4. **For dashboard prototypes**, describe:
   - What questions does this dashboard answer?
   - What are the 3-5 most important metrics? (link to user goals from Stage 1)
   - What actions can the user take from this view?
   - What's the information hierarchy? (glanceable summary → drill-down detail)

5. **Build constraints into the prototype:**
   - Must be testable in under 30 minutes
   - Must reveal whether the key assumption (from Stage 3) is valid
   - Must be throwaway — don't over-invest

### Output
Deliver: Prototype artifact (spec, wireframe, code, or schema) + what assumption it tests + how to test it.

## Stage 5: Test

**Goal:** Validate with real users (or realistic proxies) and decide next steps.

### Process

1. **Define the test.** For each prototype:

```
TEST PLAN
---------
Hypothesis: [What we believe will happen]
Method:     [How we'll test — user session, A/B, analytics, survey]
Audience:   [Who we're testing with — be specific]
Duration:   [How long the test runs]
Success:    [Quantitative threshold — e.g., "70% complete the flow in < 2 min"]
Failure:    [What result means we pivot]
```

2. **Identify what to observe:**
   - Task completion (can they do it?)
   - Time on task (is it efficient?)
   - Error rate (where do they get stuck?)
   - Emotional response (do they feel confident/frustrated?)
   - Unprompted feedback (what do they say without being asked?)

3. **Create feedback capture framework:**
   - What worked? (Keep)
   - What was confusing? (Fix)
   - What was missing? (Add)
   - What was unnecessary? (Remove)

4. **Decision framework after testing:**

| Result | Action |
|--------|--------|
| Clear success (meets all criteria) | Ship it, monitor metrics |
| Partial success (some criteria met) | Iterate — return to Stage 3 or 4 |
| Clear failure (no criteria met) | Pivot — return to Stage 2, redefine problem |
| Surprising insight | Explore — return to Stage 1, dig deeper |

### Output
Deliver: Test plan + observation checklist + decision framework + recommended next action.

## Audit Mode (/dt audit)

Review an existing feature, page, or system against design thinking principles:

1. **User alignment** — Is it clear who this is for and what problem it solves?
2. **Problem-solution fit** — Does the solution actually address the stated problem?
3. **Assumption exposure** — What untested assumptions are baked in?
4. **Feedback loops** — Is there a way to know if it's working? (Analytics, user feedback)
5. **Iteration history** — Has this been tested and refined, or shipped once and forgotten?

Output a scorecard:

```
DT AUDIT: [Feature/Page Name]
==============================
User Clarity:        [1-5] — Do we know who this is for?
Problem Definition:  [1-5] — Is the problem clearly stated?
Solution Fit:        [1-5] — Does the solution match the problem?
Validation:          [1-5] — Has this been tested with users?
Iteration:           [1-5] — Has it been refined based on feedback?
-------------------------------
SCORE:               [X/25]
TOP RECOMMENDATION:  [One actionable next step]
```

## Integration with Existing Workflow

- **Before GSD phases:** Run `/dt define` to sharpen the problem before creating a roadmap
- **Before new features:** Run `/dt empathize` + `/dt define` to validate you're solving the right problem
- **Dashboard design:** Run `/dt empathize` to surface what metrics users actually need
- **Architecture decisions:** Run `/dt` full to consider the human impact of technical choices
- **Multilingual projects:** Empathy maps should be created per-language audience (cultural context matters)
- **Post-launch:** Run `/dt audit` on shipped features to identify iteration opportunities

## Principles

1. **Users first, technology second.** The question is never "what can we build?" — it's "what should we build?"
2. **Diverge before converging.** Generate many ideas before picking one. Premature convergence kills innovation.
3. **Make it tangible.** Abstract discussions waste time. Prototypes — even rough ones — accelerate decisions.
4. **Test assumptions, not egos.** The goal of testing is to learn, not to prove you were right.
5. **Iterate, don't perfect.** Ship, learn, improve. A shipped 80% solution teaches more than an unshipped 100% solution.
