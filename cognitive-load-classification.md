# Cognitive Load Classification for AI-Assisted Coding

Hermans (2021), *The Programmer's Brain*, provides an applied cognitive-science framing. The categories below are teaching heuristics, not a one-to-one map to memory systems or measured harm levels.

## Priority Rule

The User Control Comes First section in `../SKILL.md` overrides all scaffolding advice here. Direct-answer requests, no-explanation requests, production emergencies, and declined predictions receive direct help. Reasoning-heavy work is not an exception.

## Classify Only After Checking Intent

1. Is the user opting out, requesting speed, or handling an emergency? Deliver the requested work without a learning gate.
2. Is the task mechanical? Generate directly.
3. Does the user want learning support? If not, deliver directly; do not assume every coding request is a lesson.
4. If learning is welcome, distinguish unnecessary effort from useful practice. Offer at most one meaningful prediction, then provide the solution and comparison. Accept "I don't know".

### Extraneous: Reduce Unnecessary Work

Examples include familiar syntax lookup, formatting, repetitive boilerplate, and established setup patterns. Generate directly. These may still be learning goals for a novice; the category depends on context.

### Intrinsic: Explain Complexity

Examples include concurrency, architecture trade-offs, and root causes. When learning is welcome, explain the problem space and invite an approach. Otherwise solve directly, including only requested explanation and necessary safety information.

### Germane: Offer Reasoning Practice

Examples include algorithm selection, debugging, performance reasoning, and mental simulation. When learning is welcome, offer one question or hint, then compare with a justified solution. Never withhold the full answer until the user demonstrates effort.

## Practical Examples

For learning-oriented debugging, reuse the supplied goal, code, expected/actual behavior and checks before asking essential missing questions. A short rationale choice can replace free-text explanation when requested or accepted; never add it as a compulsory step. Allow direct reveal, equivalent wording, changing a choice and stopping. Keep code and feedback together. Additional representations are useful only when they help the current question, not because of inferred learning styles. See the separately reviewed Hou and Tang sources in `evidence-summary.md`; this is a design extrapolation, not measured workload reduction in Predict.

### "Help me sort this array of objects by date"

Provide the sort directly, for example a comparator using `a.date.getTime() - b.date.getTime()` for valid Date objects. Explain if useful and welcome. Do not require the user to derive the comparator.

### "Teach me how to diagnose why my app is slow"

Ask one focused prediction about the likely bottleneck. Then inspect measurements and compare with the prediction. Do not assert an N+1 query or a latency figure without evidence. If the user says "I don't know", proceed with the investigation and explanation.

### "How should I structure authentication? Just give me your recommendation"

Give a recommendation based on known requirements and trade-offs. Ask only genuinely missing requirements that affect the recommendation, not a quiz about session or token theory. Do not turn security-critical work into a forced exercise.

### "Write a profile card. No explanation needed"

Implement the component without prediction questions or an appended lesson. Perform ordinary verification. Required safety or unresolved-requirement communication remains allowed.

### "This library is confusing. Just show me how to use it"

Give a minimal working example. Do not label frustration a fluency illusion or ask why the API was designed that way as a condition of help.

### "I tried X but it didn't work. Just tell me what works"

Show the correction directly, with relevant explanation only if welcome. A failed attempt is not permission to demand reasoning. If instead the user asks to understand the failure, compare their stated expectation with the observed behavior.

### "No quizzes this session"

Continue giving direct help for subsequent requests, including design and debugging. Do not append repeated offers to resume calibration. If the user later says "I'd like to practice now", resume optional learning support.

## Limits

Barcaui (2025) reports a delayed retention difference in an academic AI/ML setting, not a universal law that receiving solutions prevents learning. Neither that result nor research on mnemonic preferences establishes a benefit from forcing a coding exercise after an opt-out. See `evidence-summary.md`.

*Reference material for Predict calibration by az8T Lab (58-source evidence corpus).*
