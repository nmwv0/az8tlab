# Cognitive Load Classification for AI-Assisted Coding

> Based on the three-type cognitive load framework from educational psychology, applied to AI-assisted programming contexts.

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

**Agent behavior:** Generate freely. Explain only if asked. This is extraneous load that wastes working memory without contributing to skill formation. Structured mnemonic strategies (acronyms, acrostics, keyword methods) can further reduce extraneous load by organizing complex information into meaningful chunks — convergent with Cowan's 4±1 WM chunk ceiling as encoding capacity boundary (Olivete et al., 2025; Di Filippo et al., 2025). WM interference vulnerability evidence strengthens this: attentional prioritization cannot shield WM contents from visual interference — items are equally vulnerable regardless of focus state, meaning extraneous visual noise must be eliminated by design rather than compensated by user attention (Hautekiet, Niklaus & Oberauer, 2025; 250ms temporal boundary condition for interference susceptibility).

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

### Example 5: "This library is confusing — just show me how to use it"

**Classification:** Processing fluency illusion risk — the request to "just show me" reduces germane load to extraneous load.

**Agent behavior:**
- Acknowledge the frustration: "The API surface is large — let me help you build a mental model"
- Provide a minimal working example (extraneous — show the syntax)
- But scaffold the conceptual understanding: "Notice how the middleware chain works — each function receives context from the previous one. Why do you think they designed it this way?"
- The developer's discomfort with complexity is not a signal to simplify — it's the learning signal itself (Balepur et al., 2024: easier-feeling ≠ better-learning)

### Example 6: "I tried X but it didn't work"

**Classification:** Germane load opportunity — the developer has a prediction (X should work) that failed. This is a calibration moment.

**Agent behavior:**
- Do not immediately give the correct answer
- Probe the prediction: "What made you think X would work here? What were you expecting to happen?"
- Compare prediction to reality: "X fails because [specific reason]. Your mental model assumed [Y], but the actual behavior is [Z]"
- Update: "Now that you see the gap, what would you try instead?"
- The developer's expressed preference may be "just tell me what works" — but the observed learning outcome from predict-compare-update is better retention

---

*Reference material for the predict-calibration skill. Part of the Predict calibration ecosystem by az8T Lab (57-source evidence corpus).*
