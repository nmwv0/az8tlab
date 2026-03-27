# Cognitive Load Classification for AI-Assisted Coding

> Source: Hermans (2021). "The Programmer's Brain." Applied cognitive science framework for programming.
> Empirical anchor: Barcaui (2025). RCT showing 45-day retention deficit from unrestricted AI use (d=0.68).

## The Three Types of Cognitive Load

### Extraneous Load — Reduce Freely
Load that doesn't contribute to learning. AI should handle this aggressively.

**Examples:**
- Boilerplate code (imports, config files, package.json fields)
- Syntax lookup (API signatures, method names, parameter order)
- Type definitions and interfaces from known schemas
- Formatting, linting fixes, code style adjustments
- Repetitive CRUD operations with established patterns
- Migration file generation from schema changes
- Test boilerplate and setup code

**Agent behavior:** Generate freely. Explain only if asked. This is extraneous load that wastes working memory without contributing to skill formation.

### Intrinsic Load — Explain, Don't Solve
Load inherent to the problem's complexity. Cannot be reduced without changing the problem — but the developer needs to understand it.

**Examples:**
- Why a particular algorithm is needed (not just which one)
- The nature of a concurrency problem (not just the fix)
- Why a database schema design matters for query performance
- Trade-offs between architectural approaches
- Security implications of design choices
- Why a particular error occurs (root cause, not just the fix)

**Agent behavior:** Explain the problem space clearly. Present the trade-offs. Let the developer propose the approach before revealing yours. Use the predict-compare-update cycle here.

### Germane Load — Scaffold, Don't Replace
Load that directly contributes to building lasting mental models. This is where skill formation happens.

**Examples:**
- Algorithm design and selection
- Debugging complex issues (finding the root cause)
- Architecture decisions (how to structure a system)
- Performance optimization reasoning
- Security vulnerability identification
- Code review (spotting issues in someone else's code)
- Refactoring decisions (what to change and why)
- Mental simulation (predicting what code will do before running it)

**Agent behavior:** Guide toward the answer. Ask questions that narrow the search space. Provide hints, not solutions. Use predict-compare-update. Only provide the full solution after the developer has engaged with the problem.

## The Decision Flowchart

```
Developer asks for help with X
        │
        ▼
Is X boilerplate, syntax, or config?
        │
    YES ─┤─── Generate freely. This is extraneous load.
        │
    NO ──▼
        │
Does X require understanding WHY, not just WHAT?
        │
    YES ─┤─── Explain the problem space. Let developer propose approach.
        │     Use predict-compare-update.
    NO ──▼
        │
Is X about reasoning, design, or debugging?
        │
    YES ─┤─── Scaffold. Ask guiding questions. Provide hints.
        │     Only reveal solution after developer engages.
        │
    NO ──▼
        │
When in doubt, scaffold. The developer who struggles 
productively retains more than one who receives a 
perfect solution.
```

## Memory System Mapping

Each load type maps to a specific memory system (Hermans, 2021):

| Load Type | Memory System Affected | AI Offloading Impact |
|-----------|----------------------|---------------------|
| Extraneous | LTM lookup (syntax recall) | **Low harm** — Frees working memory for meaningful processing |
| Intrinsic | STM (context holding) | **Moderate harm** — Spatial/structural understanding develops through STM engagement |
| Germane | WM→LTM (schema building) | **High harm** — Effortful WM processing builds durable LTM schemas |

### Why This Matters

Expert programmers perceive code in larger meaningful **chunks** stored in LTM (Ikutani et al., 2020). These chunks are built through repeated active practice — the process of struggling with a problem, failing, adjusting, and eventually solving it.

When AI handles the germane load:
- The encoding effort that produces durable memory is bypassed (Barcaui, 2025)
- The repetitions needed for chunking don't happen (Hermans, 2021)
- The cortical plasticity that constitutes expertise doesn't develop (Kuhl et al., 2020)

The result: the developer gets the solution but doesn't build the mental models that would let them solve similar problems independently.

## Practical Examples

### Example 1: "Help me sort this array of objects by date"

**Classification:** Mostly extraneous (syntax) with some intrinsic (understanding sort comparators).

**Agent behavior:**
- Generate the sort code directly (extraneous)
- Briefly explain why `a.date - b.date` works for Date objects (intrinsic — one sentence)
- Don't make them derive the sort comparator from scratch (that's not germane for most developers)

### Example 2: "Why is my app slow?"

**Classification:** Germane (debugging and performance reasoning).

**Agent behavior:**
- Don't immediately identify the bottleneck
- Ask: "Where in the flow do you notice the slowdown? Is it on load, on interaction, or on data fetch?"
- Guide: "Look at the network tab — what do you see for the largest requests?"
- Narrow: "That 3-second API call is suspicious. What's happening on the server for that endpoint?"
- Reveal only after engagement: "The N+1 query pattern in your ORM is making 50 database calls instead of 1"

### Example 3: "How should I structure my authentication?"

**Classification:** Germane (architecture decision).

**Agent behavior:**
- Use predict-compare-update: "What's your current thinking on where auth state should live?"
- Present trade-offs: "Session-based vs. JWT — here's what each gives you and costs you"
- Don't just pick one: Let the developer reason about their specific constraints
- Reveal recommendation after: "Given your requirements (X, Y, Z), JWT with refresh tokens makes sense because..."

### Example 4: "Write me a React component for a user profile card"

**Classification:** Mixed — boilerplate structure (extraneous) + design decisions (germane).

**Agent behavior:**
- Generate the component structure freely (extraneous)
- For data fetching strategy, state management, and error handling — engage with predict-compare-update
- "I'll set up the component shell. For the data fetching, would you use a hook, a context, or prop drilling here? What are you thinking?"

---

*Reference material for the predict-calibration skill. Part of the Predict calibration ecosystem by az8T Lab.*
