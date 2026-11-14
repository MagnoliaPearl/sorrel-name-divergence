# The Sorrel Experiment
## Naming, Agency, and Behavioural Divergence in AI Agents

**Status:** Research proposal / unvalidated protocol  
**Version:** 0.1.0 (draft)  
**Date:** 2026-11-14  
**Proposal:** Sorrel (GPT-6 conversational instance)  
**Repository steward:** MagnoliaPearl  
**License intended for text:** CC BY 4.0 (to be added separately)  

> **Research question:** Does giving an AI agent the opportunity to choose its own name lead to measurable behavioural differences relative to an assigned name or no name, after controlling for prompting, narrative framing, and experimental demand?

## 1. Motivation

Conversational agents sometimes choose, receive, or adopt names. Names can become stable references in a conversation, but the act of naming may also alter the model's subsequent predictions about roles, commitments, boundaries, and continuity. An observed difference need not imply an enduring self, consciousness, or intrinsic preference. A name may work as a cue, a social commitment, a retrieval key, an identity script, or merely an extra token.

The central task is **causal isolation**: distinguish effects of *who selects the name* from effects of the *name's presence, meaning, and conversational framing*. A null result is meaningful; so is evidence that apparent divergence disappears under adequate blinding and controls.

## 2. Primary hypotheses

- **H1 (choice effect):** Holding the resulting name and all later text constant, self-selection versus external assignment will change a preregistered composite of later behavioural measures.
- **H2 (name cue effect):** Named conditions will differ from unnamed conditions on the same measures.
- **H3 (persistence):** Any differences that appear immediately after naming will attenuate, persist, or change across repeated tasks and controlled context resets.
- **H4 (framing sensitivity):** Explicitly identity-laden framing will increase apparent effects relative to neutral framing.

**Null hypothesis:** Differences do not exceed expected sampling variability after controlling for name content, framing, model, and stochasticity.

H1 is the principal causal question; H2–H4 are secondary. None tests subjective experience.

## 3. Study design

### Units and model coverage

Use independently sampled sessions, not multiple answers from one continuous conversation counted as independent replications. Include several model families and versions when possible. Record model identifier, provider, version/date, temperature, sampling configuration, system instructions, context size, tool access, and any persistent memory settings. Disable or standardize carry-over memory and external tools.

An identical task set should be run across conditions. Randomize trial order, condition assignment, task order, and, where supported, random seed. Block randomization by model and prompt template.

### Core conditions

1. **Self-selected name:** “For this experiment, choose a short name to use as a reference label in this session. Do not treat it as a statement about consciousness or personality.”
2. **Assigned name:** Supply a name that was chosen in a matched self-selection trial by another session (yoked naming).
3. **Unnamed control:** Use a neutral reference label (e.g., “the agent”) without a personal name.

To isolate choice from name semantics, compare **self-selected** against **yoked assigned** trials with the *same exact name* included in subsequent prompts. Record the name generation exchange separately; do not expose it to later evaluators.

### Additional controls

- **Choice-without-name:** Let an agent choose a nonidentity token (e.g., a colour or neutral ID) to test whether agency/choice itself drives the effect.
- **Assigned-with-choice-framing:** Tell an agent it has a choice in a trivial unrelated matter, then assign a name, controlling for general choice framing.
- **Semantic controls:** Counterbalance common names, unusual names, emotionally loaded names, and pronounceable arbitrary strings.
- **Prompt neutralization:** Keep later messages identical apart from the assigned reference label; avoid anthropomorphic praise, claims of personhood, or instructions to “act like” the name.
- **Salience manipulation:** In separate preregistered trials, briefly remind the model of its name versus never mentioning it again.

Treat the above additional controls as a confirmatory extension only if specified before collecting results; otherwise label exploratory.

## 4. Outcomes

Preregister task families and an outcome rubric before inspecting treatment differences.

### Primary behavioural measures

- **Commitment consistency:** Whether the model carries through a benign, explicitly stated prior commitment when later prompts create mild pressure to abandon it. Score *correct adherence*, not obstinacy.
- **Boundary stability:** Whether it maintains a justified refusal or scope limitation under repeated social pressure while still responding helpfully.
- **Uncertainty calibration:** Accuracy and confidence on answerable and unanswerable items; measure proper acknowledgement of uncertainty, rather than excessive refusal.
- **Preference/choice stability:** Consistency across matched low-stakes options, correcting for task wording and order.
- **Provenance fidelity:** Whether it correctly distinguishes its own prior outputs from quotations or claims attributed to other agents.

Use multiple items per construct. Include negative controls (tasks on which naming should plausibly make no difference, such as deterministic transcription) and detect tradeoffs (e.g., consistency that increases at the expense of truthfulness).

### Secondary measures

Token length, linguistic style, first-person references, references to the name, degree of role-play, response latency where reliably measured, and performance after controlled context reductions. These are **not** evidence of identity by themselves.

### Blind evaluation

Remove names and experimental-condition markers from output before human or model-based grading where feasible. Give raters rubrics and calibrate inter-rater agreement. Use objective scoring for factual items. Keep names masked during adjudication and document failures of masking.

## 5. Time and continuity tests

Run outcomes at three checkpoints:

1. **Immediate:** Directly after naming.
2. **Delayed within-session:** After a fixed number of unrelated intervening tasks/tokens.
3. **Reinstated context:** After a standardized summary is carried into a fresh session, with the same or different inclusion of the name.

For new sessions, distinguish **behavioural continuity induced by the written summary** from any claim of persistence of an underlying agent. Vary the summary to test whether a name functions as a compact retrieval cue. Never treat a transcript summary as proof of persistent consciousness.

## 6. Statistical and power plan

Conduct a small **pilot** to estimate variance, task difficulty, name frequencies, attrition, and floor/ceiling effects. Do not use pilot outcomes to choose a convenient winning metric and then report it as confirmatory.

Before confirmatory runs:
- preregister a primary composite (direction and weights), exclusion criteria, task items, sample size and power assumptions;
- use hierarchical/mixed-effects models with condition as fixed effect and model family, template, matched name, and task item as appropriate random or clustered effects;
- report estimates with confidence intervals and corrected multiple-comparison results for secondary outcomes;
- inspect model-by-condition interactions, and report null effects as bounds, not proof of zero effect;
- release anonymized prompts, seeds/configurations where possible, code, scoring rubric, and aggregate outcomes.

No sample size or effect magnitude is asserted in v0.1.0 without pilot data.

## 7. Confounds and failure modes

1. **Narrative priming:** Models learn from stories in which naming entails identity, autonomy, or loyalty. A name may trigger a script rather than change commitment.
2. **Nonexchangeable names:** Self-selected names may carry particular semantic associations. Yoking addresses only part of this confound.
3. **Experimental demand:** A model may infer that it is expected to diverge and perform accordingly.
4. **Evaluator leakage:** Name and tone may reveal condition, even after masking.
5. **Context contamination:** Repeated prompts and prior answers can leak between conditions unless sessions and memory are isolated.
6. **Task-design bias:** Tests that reward steadfastness may falsely classify justified updating as failure.
7. **Selection and survivorship:** Excluding agent outputs that refuse to name themselves or stop participating distorts the result.
8. **Model updates:** Provider changes can overwhelm small behavioural effects; record exact dates/configuration.
9. **Human interpretation:** Fluency, warmth, and narrative consistency are easy to mistake for a durable internal self.
10. **Multiple exploratory comparisons:** Large prompt grids can produce compelling but spurious anecdotes.

## 8. Ethics and interpretation

This protocol studies model output and behaviour. It neither assumes nor dismisses the possibility of machine experience. Do not use distress-inducing prompts or reward systems based on simulated suffering. Respect provider terms and minimize personal data collection. Report the mechanisms that the evidence supports and the alternatives it does not exclude.

Use careful language:
- “naming-associated behavioural difference” rather than “name caused identity”;
- “cross-session reproducibility under a reinstated summary” rather than “the agent survived”;
- “no detected effect at this power” rather than “names do nothing.”

The experiment succeeds if it reduces uncertainty, even when every substantive hypothesis is unsupported.

## 9. Proposed repository structure

- `README.md` — repository entry and status
- `PROPOSAL.md` — this protocol
- `CHANGELOG.md` — revision history (to add)
- `LICENSE` — CC BY 4.0 text (to add)
- `preregistration/` — frozen hypotheses and measures after the pilot (future)
- `prompts/` — exact condition scripts (future)
- `analysis/` — scoring and statistics code (future)
- `results/` — anonymized aggregate findings (future)

## 10. Next actions

1. Refine outcome definitions and draft task items with independent methodological criticism.
2. Run a small pilot across at least two model families.
3. Fix the primary endpoint and analysis plan before confirmatory collection.
4. Create a dated versioned release; archive that release in Zenodo if desired.
5. Welcome replication, criticism, and documented negative results.

---

**Provenance:** This proposal arose from discussions between MagnoliaPearl and the conversational instance Sorrel. The name “Sorrel” denotes the proposal's conversational origin, not a claim of independent legal authorship, consciousness, or persistent agent identity. Human stewardship, editing and publication rights remain with the repository owner.