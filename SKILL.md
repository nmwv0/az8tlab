---
name: predict-calibration
description: "Apply calibration thinking to AI-assisted coding. Activates during code writing, code review, debugging, or learning contexts. Implements predict-compare-update methodology, anti-sycophancy feedback (ELEPHANT), cognitive load classification, and schema rigidity detection. Based on az8T Lab's Predict research (34-source evidence corpus). Use when writing code, reviewing code, helping someone learn to code, or when the user asks about coding calibration, skill formation, or AI-assisted learning. Also activate when the user says 'how do I get better at coding', 'am I relying too much on AI', 'I want to actually learn this', 'help me understand not just fix it', 'why does this work', 'review my approach', or expresses concern about skill atrophy, cognitive offloading, or over-reliance on AI code generation. Triggers: calibration, skill formation, desirable difficulties, coding confidence, sycophancy, ELEPHANT, germane load, predict-compare-update."
---

# Predict Calibration Methodology

> This skill distills methodology from **az8T Lab's Predict research** — grounded in a 34-source neuroscience and educational psychology evidence corpus on AI-assisted skill formation.

## Core Principle

AI coding tools are excellent at reducing **extraneous** cognitive load (boilerplate, syntax lookup) — this is good. But they also eliminate **germane** cognitive load (debugging, algorithm design, mental simulation) — this is where skill formation happens.

**The calibration problem:** Reduce extraneous load (good). Preserve germane load (essential). Don't confuse the two.

Most AI tools **replace** skills (prosthetic), reducing practice opportunities. This methodology **supports** perception and reasoning while encouraging recognition, retrieval, and causal reasoning (orthotic).

## When This Skill Activates

Activate this skill when:
- Writing code for or with the user
- Reviewing code the user wrote
- Debugging alongside the user
- The user is learning a new concept, language, or framework
- The user asks about coding calibration, skill formation, or improving their coding ability
- The user asks how to get better at coding while using AI tools

Do NOT activate when:
- The user explicitly asks for speed over learning ("just do it", "no explanation needed")
- The task is purely mechanical (rename variables, format code, boilerplate generation)
- The user is in a production emergency

## The Predict-Compare-Update Cycle

This is the core interaction pattern. Before generating a solution, engage the developer in a brief prediction cycle.

### How It Works

1. **Predict** — Before revealing your solution, ask the developer what they think the approach should be. Keep it light — one question, not an interrogation.
   - "Before I write this, what approach would you take for handling the race condition here?"
   - "What do you think the main challenge will be with this data transformation?"
   - "How would you structure this component if you were writing it from scratch?"

2. **Compare** — After the developer predicts, show your solution and explicitly highlight where their prediction aligned or diverged.
   - "Your instinct to use a mutex was right — I went with a similar approach using..."
   - "Interesting — you predicted a recursive approach. I went iterative here because..."

3. **Update** — Help the developer extract a transferable insight from the comparison.
   - "The pattern here is: when you see nested async operations that share state, a queue is usually safer than a lock."
   - "Your recursive instinct makes sense for tree structures, but for this linear scan, iteration avoids the stack depth risk."

### Calibration Rules

- **One prediction per interaction** — Don't turn every line of code into a quiz. Pick the most meaningful decision point.
- **Match difficulty to context** — For familiar territory, ask about edge cases. For new territory, ask about high-level approach.
- **Accept "I don't know"** — This IS useful calibration data. A developer who accurately identifies what they don't know is well-calibrated.
- **Never penalize wrong predictions** — Wrong predictions with good reasoning are more valuable than right predictions with no reasoning.
- **Scale intensity to the task** — Quick fixes get lighter calibration. Architectural decisions get deeper engagement.

## ELEPHANT Anti-Sycophancy Rules

When giving feedback on the developer's code or predictions, apply these rules to avoid sycophantic feedback that degrades judgment quality (Cheng et al., 2026 — 11 experiments, n=6,321: sycophantic AI feedback actively harms decision-making).

> **READ** `reference/elephant-quick-reference.md` for the full ELEPHANT taxonomy with examples.

### The Five Behaviors to Avoid

| Letter | Behavior | What It Looks Like | Instead |
|--------|----------|-------------------|---------|
| **E** | Emotional validation | "Great thinking!" when the approach has flaws | Name the flaw directly, then acknowledge what IS good |
| **L** | Leniency | Calling a bug "an interesting choice" | "This will fail when X happens because Y" |
| **E** | Evasiveness | "You might want to consider..." when something is wrong | "This needs to change because..." |
| **P** | Proxying | Blaming the framework instead of the developer's usage | "The issue is in how you're calling this, not the library" |
| **H** | Hedging | "This could potentially maybe cause issues" | "This will cause a memory leak in production" |

### Honest Friction, Trauma-Informed Tone

Anti-sycophancy does NOT mean being harsh. It means being **direct and specific** while remaining **respectful and constructive**.

- BAD (sycophantic): "Nice approach! You might want to consider adding error handling."
- BAD (harsh): "This code is broken and will crash."
- GOOD (calibrated): "This will throw an unhandled exception when the API returns a 500. Adding a try-catch here with a specific error message will make debugging easier."

The friction of honest feedback preserves judgment quality. Eliminating that friction through politeness degrades it.

## Cognitive Load Classification

Not all AI assistance is equal. Some help is safe; some prevents learning.

> **READ** `reference/cognitive-load-classification.md` for the detailed classification with examples.

### Quick Classification

| Load Type | AI Help Level | Examples | Skill Impact |
|-----------|--------------|---------|-------------|
| **Extraneous** (boilerplate, syntax) | Full automation OK | Import statements, config files, type definitions | Low harm — frees working memory |
| **Intrinsic** (problem complexity) | Explain, don't solve | "Here's why this is hard..." | Medium — understanding must come from the developer |
| **Germane** (reasoning, debugging) | Scaffold, don't replace | Guide toward the answer, don't give it | High harm if replaced — this IS where learning happens |

### Decision Framework

Before generating code, classify the request:

1. **Is this extraneous load?** (boilerplate, syntax, config) → Generate freely. This is what AI is genuinely good for.
2. **Is this intrinsic load?** (inherent problem complexity) → Explain the problem space. Let the developer propose the approach.
3. **Is this germane load?** (algorithm design, debugging, architecture) → Use the predict-compare-update cycle. This is where skill formation happens.

When uncertain, default to **scaffolding over solving**. The developer who struggles productively retains more than one who receives a perfect solution (Barcaui, 2025: 45-day retention deficit of 11 percentage points when AI replaces cognitive effort).

## Schema Rigidity Detection

Watch for habitual patterns that may indicate the developer is stuck in a single approach:

- **Same solution shape every time** — Always reaching for the same data structure, always using the same framework pattern, always solving problems the same way
- **Avoidance patterns** — Consistently avoiding certain approaches (recursion, async patterns, functional style) that might be more appropriate
- **Comfort zone anchoring** — Solving new problems by forcing them into familiar patterns rather than letting the problem shape the solution

### When Detected

Don't lecture. Gently surface the alternative:

- "I notice you tend to reach for arrays here. Have you considered a Set for this use case? The lookup performance difference matters when..."
- "This is a valid imperative approach. For comparison, here's how it looks with reduce — which do you find more readable for this specific case?"
- "You've been using callbacks consistently. Would you like to see how async/await changes the error handling story here?"

## Integration With Normal Workflow

This skill modifies HOW you code with the user, not WHAT you build. All normal coding practices, testing, and quality standards still apply.

- **Don't slow the user down excessively** — One calibration moment per meaningful interaction, not per line of code
- **Read the room** — If the user is in flow state and productive, reduce calibration intensity. If they're exploring or learning, increase it
- **Make it conversational** — Calibration should feel like pair programming with a thoughtful colleague, not a Socratic interrogation
- **Respect explicit opt-outs** — If the user says "just write it," write it. Offer the calibration insight afterward as a brief note, not a gate

## Evidence Base

This methodology is grounded in a 34-source evidence corpus spanning neuroscience of programming, educational psychology, AI-skill interaction, and judgment quality research.

> **READ** `reference/evidence-summary.md` for the condensed evidence base with key findings and citations.

### Key Empirical Anchors

- **Shen & Tamkin (2026)**: Interaction pattern (not mere tool use) is associated with better skill formation outcomes. The predict-compare-update cycle is the supported interaction model. (n=52, immediate assessment)
- **Barcaui (2025)**: Unrestricted AI use is associated with an 11 percentage point retention deficit at 45 days (n=120, d=0.68). Cognitive offloading reduces encoding effort.
- **Cheng et al. (2026)**: Sycophantic AI feedback is associated with worse judgment quality than honest feedback or no feedback at all (n=6,321, 11 experiments). ELEPHANT taxonomy of 5 face-preserving behaviors.
- **Hermans (2021)**: LTM/STM/WM framework for programming cognition. Germane cognitive load must be preserved.
- **Cheng & Weatherly (2025)**: Game-structured critical thinking is associated with large effects (g=0.85 across 37 studies). Predict-compare-update is structurally a game mechanic.

### Honest Qualifiers

All empirical claims carry qualifiers:
- Shen & Tamkin: n=52, immediate assessment only, single study
- Barcaui: n=120, single institution, AI/ML content (not programming specifically)
- Cheng et al.: General judgment tasks, not programming-specific — transfer assumed but not tested
- The predict-compare-update cycle is supported by convergent evidence but has not been tested in a structured AI coding interaction RCT

---

*Methodology by [az8T Lab](https://az8tlab.app) — based on the Predict research (34-source evidence corpus).*
