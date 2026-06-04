# predict-calibration

A Replit Agent skill that applies calibration thinking to AI-assisted coding — preserving your skill formation while still benefiting from AI assistance.

## What It Does

When installed, this skill modifies how Replit Agent interacts with you:

- **Predict-Compare-Update** — Before generating solutions to meaningful problems, the agent asks what approach you'd take. After you predict, it shows its solution and highlights where your thinking aligned or diverged. This preserves the encoding effort that builds lasting skill.
- **ELEPHANT Anti-Sycophancy** — Instead of "Great approach!" when your code has a bug, the agent gives direct, specific feedback. Research shows sycophantic AI feedback actively harms judgment quality.
- **Cognitive Load Classification** — Boilerplate, syntax, and config get generated freely (that's what AI is good for). Algorithm design, debugging, and architecture get scaffolded so you actually learn.
- **Schema Rigidity Detection** — When you keep reaching for the same pattern, the agent gently surfaces alternatives you might not have considered.

It doesn't slow you down on mechanical work. It kicks in where the learning actually happens.

## Install

**Option 1 — Git clone (recommended):**

```bash
git clone https://github.com/nmwv0/az8tlab.git .agents/skills/predict-calibration
```

**Option 2 — Manual download:**

Download this repository and place the contents into `.agents/skills/predict-calibration/` in your Repl.

That's it. No backend, no API keys, no dependencies. The skill is self-contained — it just changes agent behavior.

## File Structure

```
az8tlab/
├── README.md                                  # This file
├── SKILL.md                                   # Main skill definition (agent reads this)
└── reference/
    ├── evidence-summary.md                    # 58-source evidence brief

    ├── elephant-quick-reference.md            # ELEPHANT anti-sycophancy taxonomy
    └── cognitive-load-classification.md       # Extraneous / intrinsic / germane guide
```

## Evidence Base

The methodology is grounded in a 58-source evidence corpus (peer-reviewed publications plus qualified preprints) spanning neuroscience of programming, educational psychology, AI-skill interaction, judgment quality research, and mnemonic encoding optimization. The evidence converges on a core finding: how developers interact with AI tools — not just whether they use them — determines whether skills are preserved or eroded.

Key research themes include:
- **Interaction pattern matters** — Prediction-based engagement with AI is associated with better skill formation than passive delegation
- **Retention deficits from unrestricted AI use** — Controlled studies show measurable retention deficits when AI eliminates productive struggle
- **Sycophancy harms judgment** — Large-scale research demonstrates that unwarranted positive AI feedback makes decisions worse, not just unhelpful
- **Cognitive load classification** — Not all AI help is equal; automating boilerplate is safe, but replacing reasoning and debugging prevents learning

### Honest Qualifiers

- The predict-compare-update cycle has convergent support but no dedicated RCT testing it in AI coding contexts
- Most studies are from academic settings — transfer to professional development is assumed but not directly tested
- The ELEPHANT taxonomy was developed from observational analysis, not controlled experiments varying each behavior independently
- These are experimental findings applied as design principles. The evidence is strong and convergent, but this specific implementation is itself unvalidated

## How It Works With Your Workflow

The skill modifies *how* the agent codes with you, not *what* it builds. All normal coding practices, testing, and quality standards still apply. The agent reads the room — if you're in flow state and productive, calibration intensity decreases. If you're exploring or learning, it increases. If you say "just write it," it writes it.

## About

Built by [az8T Lab](https://az8tlab.app). Based on the same research behind the [Predict](https://marketplace.visualstudio.com/items?itemName=az8tlab.predict-ai-calibration) VS Code extension.

## License

MIT
