# Predict agent skill

### Help me finish. Help me understand when I ask.

**This skill gives a compatible AI agent instructions for optional learning support and evidence-based feedback.** It is designed for coding, debugging and review. Unlike the Predict extension, it has no sidebar, completion detector or score tracker. You do not need the extension to use it.

```text
Want the result?         →  Direct help, without a quiz.
Want to understand?     →  Predict → Check → Revise.
Evidence changes?      →  Correct the answer, whoever gave it.
```

## Choose your kind of help

**“Help me understand this bug.”**

The agent can invite one short prediction, compare it with the code or a test, and explain one useful distinction.

**“Just fix it. No explanation.”**

The agent should do the work without a teaching exercise. “I don’t know” and “skip” also end a prediction prompt. “No quizzes this session” applies for the session.

**“Give me a different example to practise.”**

The agent can offer optional, untimed practice. Reveal, skip or stop whenever you prefer.

> **One useful distinction**
>
> “The AI agrees with me” is not a correctness check. “This input produces the required result” is evidence, with a scope. The skill asks the agent to make that difference clear.

Accuracy and necessary safety checks still apply when teaching is declined. Emergencies and routine mechanical work do not need learning prompts.

## Why it exists

AI can help you produce code. Learning to code gives you opportunities to ask better questions about it: what should happen, why did it fail, and how could it be improved? Predict makes room for both getting work done and practising that reasoning—with optional predictions, explanations and concrete checks.

AI can help you finish code before you understand why it works. That matters when you need to adapt it, investigate a failure or review an important change. Predict makes room for your understanding without turning every request into a lesson.

Learning and practising coding give you opportunities to break a problem down, compare solutions and revise an assumption. The skill brings those activities into a conversation you are already having:

| Your goal | What to ask |
|---|---|
| Understand a new concept | “Help me trace this with one input.” |
| Review a consequential change | “Compare my expectation with this refactor and suggest a check.” |
| Explore a different approach | “Show one alternative and explain when it would be a better fit.” |

**The aim is something you can use again:** a clearer explanation, a corrected assumption or a better test. Compare approaches for correctness, readability and performance in context, rather than treating more complicated or faster code as automatically better.

### One small example

You expect a greeting to use “world” for a blank name, but a spaces-only name slips through.

**Expectation → Difference → Check**

The agent uses the expectation you already gave, explains why trimming must happen before choosing the fallback, and checks a spaces-only input. If it cannot run the code, it gives you the expected result and says the check has not been run. The underlying rule transfers across languages; the syntax changes.

You do not need another quiz to finish that exchange. If you want more practice, ask for a different example.

### Why practice matters

Neuroplasticity is the brain’s capacity to adapt through experience. In coding, breaking down a problem, checking an assumption and revising a solution are chances to practise useful ways of thinking.

[Mera and colleagues’ word-pair experiments](https://doi.org/10.3758/s13421-025-01813-x) found that trying to recall or answer before seeing the material, followed by feedback, improved later recall compared with copying. The study was about memory, not coding.

In [Shen and Tamkin’s 2026 coding study](https://www.anthropic.com/research/AI-assistance-coding-skills), 52 mostly junior developers learned an unfamiliar Python library. The AI-assisted group scored lower on an immediate understanding quiz. Within that group, exploring explanations was associated with stronger results than delegating the work; that interaction pattern was not separately randomized.

Learning to code can matter beyond producing software. [Scherer, Siddiq and Sánchez-Scherer (2021)](https://doi.org/10.3389/fpsyg.2021.559424) discuss possible benefits for reasoning, creativity and mathematics, drawing on earlier research. Their perspective offers a reason to value coding practice, but does not establish how long benefits last or how widely they transfer.

These sources address different questions; none tests Predict. The skill’s practical aim is to help you use AI while keeping room to reason, compare and check. See the [evidence brief](reference/evidence-summary.md) for source details and limits.

If writing an explanation feels unnecessary, ask for a few rationale choices instead. You may change a choice, request the explanation directly or stop. The agent should reuse the context you supplied, accept equivalent wording and never convert uncertainty into another compulsory quiz.

Unlike a tutorial, this skill works with your current problem. Unlike the extension, it guides the conversation rather than keeping an editor comparison or local history. It is a set of instructions for an agent, not a separate AI model.

## Install

In a host that supports this layout, copy the **contents** of this folder into:

```text
.agents/skills/predict-calibration/
├── SKILL.md
├── LICENSE
├── README.md
└── reference/
    ├── evidence-summary.md
    ├── elephant-quick-reference.md
    └── cognitive-load-classification.md
```

Keep the instructions, license and all three references together. Check an existing destination before replacing it. No Path backend, API credentials or package installation is required by the skill.

Ask the host to use **predict-calibration**, then confirm it discovers the skill and respects your preferences. Host support and adherence vary; copying files does not guarantee either.

## Help and privacy

- [Research findings and their limits](reference/evidence-summary.md): the learning rationale and what the studies actually establish.
- [Examples of useful feedback](reference/elephant-quick-reference.md): correcting an error without flattery or unnecessary harshness.
- [Choosing the right amount of guidance](reference/cognitive-load-classification.md): when to explain, invite practice or simply do the work.

### Your data and control

The instructions add no telemetry, cognitive scoring or independent memory. Your host’s storage, tools and privacy policies still apply.

The agent should distinguish performed checks from reported results, acknowledge uncertainty and correct itself. It must not invent capabilities or diagnose your abilities.

The historical 58-source snapshot includes experiments, reviews, preprints and perspectives, not 58 validations of this skill. Academic findings do not automatically transfer to professional programming.

### For maintainers

Run `node companion/scripts/check-skill-structure.mjs` from the containing project to check parity, references and instruction safeguards, not learning effectiveness. This update reuses existing predictions, keeps feedback focused, makes checks concrete and loads reference material only when needed. No marketplace publication is claimed.

MIT · [LICENSE](LICENSE)
