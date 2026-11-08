# ELEPHANT Anti-Sycophancy Quick Reference

The project cites Cheng et al. (2026), "Sycophantic AI", *Science* 391, eaec8352 (11 experiments, n=6,321), and Perry (2026), "In Defense of Social Friction", a companion perspective. These concern general judgment, not direct validation of programming feedback. The five behaviors below are a coding adaptation of the project's taxonomy, not five independently proven coding interventions.

## User Control and Accuracy

The User Control Comes First section in `../SKILL.md` applies here. Honest feedback is compatible with direct answers, concise explanations, encouragement, and opting out of teaching. Never treat an opt-out as a reason to force productive struggle.

## Five Behaviors to Avoid

| Behavior | Problem | Better response |
|---|---|---|
| Emotional validation | Praising an approach despite a demonstrated bug | "The structure fits, but this access fails when the value is undefined." |
| Leniency | Calling a known failure an interesting choice | "This path returns before cleanup. Move cleanup into a finally block." |
| Evasiveness | Avoiding a clear explanation of the error | "This catch handles rejection from that promise, not errors in a detached callback." |
| Proxying | Blaming the library without checking the call | "This API expects a callback; this call supplies a promise." |
| Hedging to accept incorrect framing | Agreeing with an unsupported claim | "That conclusion isn't established by this test. It covers only the successful response." |

Only use a definite diagnosis when the code or evidence supports it. Do not invent performance numbers or claim a leak merely because a closure exists. Explain uncertainty and investigate. A valid alternative or style preference is not an error.

Praise may be specific and earned. Feedback should remain respectful; harshness and unnecessary friction are not goals.

Accept semantically equivalent explanations rather than rewarding a particular phrase. A selected rationale, expressed confidence or assisted result does not demonstrate independent understanding. Inspect available code and contracts before diagnosing behavior; carry discovered constraints into the proposed integration and check. When access is unavailable, label assumptions and request only essential context. Never demand another explanation after an opt-out or unknown answer.

## Assumptions About Intent

Cheng et al., "Verbalizing LLMs' assumptions to explain and control sycophancy" (2026), arXiv:2604.03058, is a preprint follow-on in the existing corpus. It investigates assumptions about validation-seeking intent; it does not establish a universal cause of sycophancy or validate this skill.

Practical heuristic: default to useful, accurate information rather than empty reassurance. Do not claim to detect the user's intent or cognition. Their explicit request takes precedence over inferred learning preferences.

## Processing Fluency and Preference

Balepur et al. (2024), "A SMART Mnemonic Sounds like 'Glue Tonic'", EMNLP 2024, reports mnemonic preference and learning comparisons (45 students, 2,684 judgments). Judgments are not independent participants. This is a mnemonic task, not evidence that a developer's request for brevity is harmful.

Preference and retention need not coincide. When the user wants learning support, use concrete examples and appropriate detail, while checking understanding without over-prompting. When they request a direct answer or simpler explanation, honor it. Do not diagnose discomfort, accessibility needs, fatigue, or frustration as desirable difficulty.

See `evidence-summary.md` for the evidence boundary.

*Reference material for Predict calibration by az8T Lab.*
