# predict-calibration

A Replit Agent skill that applies calibration thinking to AI-assisted coding — preserving your skill formation while still benefiting from AI assistance.

## What It Does

When installed, this skill modifies how Replit Agent interacts with you:

- **Predict-Compare-Update** — Before generating solutions to meaningful problems, the agent asks what approach you'd take. After you predict, it shows its solution and highlights where your thinking aligned or diverged. This preserves the encoding effort that builds lasting skill.
- **ELEPHANT Anti-Sycophancy** — Instead of "Great approach!" when your code has a bug, the agent gives direct, specific feedback. Based on research showing sycophantic AI feedback actively harms judgment quality (Cheng et al., 2026, *Science*).
- **Cognitive Load Classification** — Boilerplate, syntax, and config get generated freely (that's what AI is good for). Algorithm design, debugging, and architecture get scaffolded so you actually learn.
- **Schema Rigidity Detection** — When you keep reaching for the same pattern, the agent gently surfaces alternatives you might not have considered.

It doesn't slow you down on mechanical work. It kicks in where the learning actually happens.

## Install

**Option 1 — Git clone (recommended):**

```bash
git clone https://github.com/az8tlab/predict-calibration-skill.git .agents/skills/predict-calibration
```

**Option 2 — Manual download:**

Download this repository and place the contents into `.agents/skills/predict-calibration/` in your Repl.

That's it. No backend, no API keys, no dependencies. The skill is self-contained — it just changes agent behavior.

## File Structure

```
predict-calibration-skill/
├── README.md                                  # This file
├── SKILL.md                                   # Main skill definition (agent reads this)
└── reference/
    ├── evidence-summary.md                    # 34-source evidence corpus summary
    ├── elephant-quick-reference.md            # ELEPHANT anti-sycophancy taxonomy
    └── cognitive-load-classification.md       # Extraneous / intrinsic / germane guide
```

## Evidence Base

The methodology is grounded in a 34-source evidence corpus spanning neuroscience of programming, educational psychology, AI-skill interaction, and judgment quality research. Key findings:

| Study | Finding | Scale |
|-------|---------|-------|
| Shen & Tamkin (2026) | Predict-compare-update interaction pattern is associated with better skill formation than passive AI delegation | n=52 |
| Barcaui (2025) | Unrestricted AI use is associated with an 11 percentage point retention deficit at 45 days | n=120, d=0.68 |
| Cheng et al. (2026) | Sycophantic AI feedback is associated with worse judgment than honest feedback or no AI at all | n=6,321, 11 experiments |
| Hermans (2021) | Germane cognitive load (reasoning, debugging) is where skill formation happens — AI should scaffold it, not replace it | Applied framework |

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
