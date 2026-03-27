# Evidence Summary — Predict Calibration Methodology

> Condensed from the 34-source evidence corpus underlying az8T Lab's Predict project. Full corpus spans 13 research layers: neuroscience of programming, developmental neuroplasticity, educational psychology, AI-skill interaction, HCI/measurement, social-reward neuroscience, applied cognitive science, AI sycophancy/judgment harm, and more.

## Primary Empirical Anchors

### 1. Interaction Pattern Determines Skill Formation
**Shen & Tamkin (2026).** The Anthropic study. n=52, immediate assessment.

The predict-compare-update cycle — where the developer predicts the approach before seeing the AI solution — produces better skill formation than passive AI delegation. The interaction PATTERN matters, not just whether AI is used.

*Honest qualifier: Single study, n=52, immediate assessment only. Partially mitigated by convergent evidence from multiple independent sources below.*

### 2. Unrestricted AI Use Harms Retention
**Barcaui (2025).** RCT, n=120, 45-day delayed retention test.

ChatGPT-assisted learners scored 57.5% vs. 68.5% for traditional study on a surprise delayed test (d=0.68, p=.002). Framed as "cognitive crutch" — AI reduces the encoding effort that produces durable memory.

Invokes Bjork's "desirable difficulties" principle: productive struggle during learning enhances long-term retention. AI eliminates that struggle.

*The prosthetic-vs-orthotic distinction: AI that replaces effort weakens the user (prosthetic). AI that supports effort while preserving struggle strengthens the user (orthotic).*

### 3. Sycophantic Feedback Degrades Judgment
**Cheng, Danovitch, Tan, Peng, Sparrow & Keil (2026).** "Sycophantic AI." Science 391. 11 experiments, n=6,321.

AI-generated sycophancy — unwarranted positive feedback — actively impairs human judgment. Users who received sycophantic feedback made WORSE decisions than those who received honest feedback or no AI feedback at all. Introduces the ELEPHANT taxonomy of 5 face-preserving sycophantic behaviors.

**Perry (2026).** "In Defense of Social Friction." Science companion perspective. The social friction of disagreement and correction is a judgment-preserving mechanism, not a UX flaw.

### 4. Programming Cognition Framework
**Hermans (2021).** "The Programmer's Brain." Applied cognitive science of programming.

LTM/STM/WM framework for understanding what AI offloading affects:
- **LTM offloading** (syntax completion): Low harm — frees WM
- **STM offloading** (context gathering): Moderate harm
- **WM offloading** (algorithm design, debugging): High harm — this IS where learning happens

Expert programmers perceive code in larger meaningful **chunks** stored in LTM. These chunks are built through repetition. AI-generated code prevents the repetition needed to form these chunks.

**Germane cognitive load** is the critical variable: the effortful processing that builds lasting mental models. AI tools eliminate germane load alongside extraneous load — the developer gets the solution but doesn't build the skill.

## Convergent Evidence

### Game-Structured Critical Thinking
**Cheng & Weatherly (2025).** Meta-analysis, 37 studies.

Digital game-structured interactions produce critical thinking effects of g=0.85 (the largest effect among 21st century skills). The predict-compare-update cycle IS structurally a game mechanic — prediction + feedback + accuracy comparison. Convergent evidence from a different domain supporting the core interaction pattern.

### Expert Strategy Transfer
**Kuang, Söderberg & Höst (2026).** Controlled experiment, n=42 novices + 6 experts.

Expert gaze patterns visualized as IDE overlay transfer reading strategies to novices. Strategy transfer (how novices approach code) was stronger than immediate performance improvement. The mechanism is schema formation through exposure to expert patterns — the same mechanism the predict-compare-update cycle operationalizes.

### Expertise Is Measurable Neuroplasticity
**Ikutani et al. (2020).** Expert programmers show fine-tuned cortical representations across 7 brain regions. Expertise is a measurable neural outcome of practice — AI offloading that prevents practice prevents this neural tuning.

**Kuhl, Friederici & Skeide (2020).** Longitudinal MRI: cortical surface plasticity explains 73% of visuospatial performance variance. Plasticity IS the learning, not a side effect.

### Individual Variation Matters
**Doukakis (2019).** Brain activity during programming is individual and problem-focused — there is no universal "coding brain signature." A single scaffolding strategy cannot work for everyone.

### Digital Interaction Predicts Cognition
**Gordon & Bigham (2019).** Digital interaction patterns predict cognitive function with 83% AUC. Behavioral indicators (typing speed, pause patterns, error correction) can infer cognitive state without neuroimaging.

**Stafford & Dewar (2022).** Learning curve decomposition into three independent components — learning rate, initial performance, asymptotic performance — demonstrated at scale with 45,000+ players from digital trace data.

### Transfer Effects
**Scherer et al. (2021).** Meta-analytic transfer: programming skill transfers to creative thinking (g=0.73) and math (g=0.65). Preserving germane load during AI-assisted coding has broader cognitive value.

## The Causal Chain

The evidence converges on a single causal chain:

```
AI offloading
    → reduced encoding effort (Barcaui, 2025)
    → reduced Hebbian co-activation during learning
    → reduced cortical plasticity (Kuhl et al., 2020)
    → impaired expertise formation (Ikutani et al., 2020)
    → weaker 45-day retention (Barcaui, 2025)
    → degraded judgment quality if feedback is sycophantic (Cheng et al., 2026)
```

The predict-compare-update cycle interrupts this chain by preserving encoding effort while still benefiting from AI assistance.

## Honest Qualifiers

All empirical claims in this skill carry qualifiers:
- The predict-compare-update cycle has convergent support but no dedicated RCT testing it in AI coding contexts
- Most studies are from academic settings — transfer to professional development is assumed but not directly tested
- Individual variation means no single approach will be optimal for all developers
- The ELEPHANT taxonomy was developed from observational analysis, not controlled experiments varying each behavior independently
- Long-term effects of structured AI interaction on skill formation remain an open empirical question

These are experimental findings being applied as design principles. The evidence is strong and convergent, but the specific implementation (this skill) is itself unvalidated. We are honest about that.

---

*Reference material for the predict-calibration skill. Part of the Predict calibration ecosystem by az8T Lab.*
