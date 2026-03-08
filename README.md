# dt-skill

Design Thinking skill for Claude Code. Human-centered problem solving before you write code.

Every AI coding tool helps you build fast. This one helps you figure out **what to build and for whom**.

## What it does

Walks Claude through the 5 stages of design thinking with structured outputs:

| Command | Stage | Output |
|---------|-------|--------|
| `/dt:full` | All 5 | Complete design thinking exercise |
| `/dt:empathize` | 1 | Empathy maps, personas, pain point priority list |
| `/dt:define` | 2 | "How Might We" problem statement + success criteria |
| `/dt:ideate` | 3 | Brainstorm, assumption challenges, impact/effort matrix |
| `/dt:prototype` | 4 | Specs, wireframes, schemas at the right fidelity |
| `/dt:test` | 5 | Test plans, observation checklists, decision framework |
| `/dt:audit` | Review | Scorecard (1-25) for existing features |
| `/dt:help` | — | Command reference |

## Install

```bash
npx skills add ORBWEVA/dt-skill
```

Or manually copy files:
- `skills/design-thinking/SKILL.md` -> `~/.claude/skills/design-thinking/`
- `commands/dt/*.md` -> `~/.claude/commands/dt/`

## Example output

Running `/dt:define` on a SaaS product:

```
How might we help creators scale authentic, personalized 1-on-1
conversations through AI avatars so that their followers get real
value in under 5 minutes -- without requiring the creator to be
present or the end user to overcome signup friction?

Success Criteria:
1. Click-to-voice time < 30 seconds (returning users)
2. Session completion rate > 60%
3. Return rate > 25% within 7 days
4. Creator activation > 70% publish within 24h
```

Running `/dt:audit` on an existing feature:

```
DT AUDIT: Onboarding Flow
==============================
User Clarity:        4/5
Problem Definition:  3/5
Solution Fit:        4/5
Validation:          2/5
Iteration:           1/5
-------------------------------
SCORE:               14/25
TOP RECOMMENDATION:  Run 5 user tests and iterate based on
                     where users drop off.
```

## When to use it

- **Before planning** — `/dt:define` before creating a roadmap
- **Before building** — `/dt:empathize` to clarify who you're building for
- **After shipping** — `/dt:audit` to find iteration opportunities
- **New products** — `/dt:full` for a comprehensive exercise

Works well paired with implementation skills like GSD, frontend-design, or product-manager-toolkit.

## Security

This skill contains **zero executable code**. It's pure markdown — structured prompts that guide Claude's thinking. No scripts, no dependencies, no API calls, no shell commands. Read every file in 2 minutes.

```
skills/design-thinking/SKILL.md    # methodology + output formats
commands/dt/*.md                   # slash command definitions
package.json                       # metadata only
```

## License

MIT
