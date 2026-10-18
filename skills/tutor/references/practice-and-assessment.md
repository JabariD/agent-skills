# Practice and Assessment

Use when selecting reps, validating understanding, scoring calibration, designing an assessment, deciding whether to advance a concept, or building reliable performance under pressure.

## Contents

- [Define independent performance](#define-independent-performance)
- [Blank-page recall](#blank-page-recall)
- [Calibration scoring](#calibration-scoring)
- [Match the method to the component](#match-the-method-to-the-component)
- [Evidence by target depth](#evidence-by-target-depth)
- [Choose the rep](#choose-the-rep)
- [Sequence and mix reps](#sequence-and-mix-reps)
- [Calibrate volume](#calibrate-volume)
- [Assessment design](#assessment-design)
- [Performance under pressure](#performance-under-pressure)

## Define independent performance

For substantial learning, state what the learner should be able to explain, decide, build, or perform independently, the situation in which it matters, and the resources that will be available. Choose evidence that resembles that result.

For working competence or reliable performance, include at least one delayed attempt without the original worked example, notes, or tutor hints. Immediate smoothness or recognition is not enough evidence of retention.

## Blank-page recall

The default opener for a course session, and the cheapest honest test available. Five minutes, no preparation, no lookahead.

1. Name the topic boundary out loud, then close everything.
2. Write everything that can be produced: facts, mechanisms, connections, examples, definitions, relationships. Maximum output, not curated accuracy. Do not stop to evaluate correctness mid-flow.
3. Only then open the source and diff against it.
4. **Type every gap.** This step is the point of the exercise and is the one usually skipped:

| Gap type | What it means | Correct response |
|---|---|---|
| Never encoded | Was not actually studied, or was skimmed past | Teach it; this is new material, not a failure |
| Comprehension gap | Partially understood, could not reconstruct | Repair the causal rule, then retest in a changed case |
| Retrieval gap | Known, but did not surface under cold conditions | More spaced retrieval; the model is fine, the access path is weak |

Record the typed gaps in the session log. "I should review that" is not a gap type and does not discriminate between three problems needing three different fixes.

Use a blank page before restudy, never after. Restudying first converts the test into a recognition exercise and destroys its diagnostic value.

## Calibration scoring

Optional: only when a course is measuring calibration or the learner asks; skip it entirely when they opt out (see SKILL.md, The ledger).

Before a substantial rep, name the exact predicted test, its timing, allowed resources, and success criterion; then ask for the probability of success, 0 to 100. For a retention prediction, name the later cold, unaided test and leave its outcome pending until that test happens. A prediction about tomorrow is paired only with tomorrow's specified attempt, never with today's practice.

Keep the performance score separate from the probability outcome:

| Outcome | Score |
|---|---|
| Correct, unaided, complete | 100 |
| Correct but with material gaps, or needed one hint | 50 |
| Wrong model, could not produce, or needed the answer | 0 |

Record the prediction and test identity in the course ledger. On the specified test, record binary `success`: 100 only when the stated success criterion is met, otherwise 0. A hinted attempt fails an unaided-success criterion even if its performance score is 50. Use append-only follow-up rows to pair a pending prediction with its later outcome; a stable test ID connects them. Legacy rows without a matching test identity and outcome remain performance evidence, excluded from calibration.

Compute calibration only over completed prediction/outcome pairs. Three derived measures matter, in this order:

- **Signed calibration gap** = mean(predicted − success). Positive is overconfidence, negative is underconfidence. Report the number of completed pairs beside it.
- **Absolute calibration error** = mean(|predicted − success|). This describes prediction error without its direction; it is separate from the performance score.
- **Resolution** = compare success rates for predictions above 70 and below 40 when both groups have enough observations to be useful.

A useful benchmark: predictions near 90 should succeed almost always, predictions near 50 about half the time, predictions near 20 rarely. Succeeding 60% of the time at a stated 90 is overconfidence, and it is actionable: it means the felt sense of "I have this" is firing about thirty points early in that domain.

Grade the attempt, never the confidence. Confidence is data about calibration, not an input to promotion. Report the gap plainly when it is large; do not soften it, and do not let a good gap become its own source of satisfaction.

If recall succeeds but application fails, schedule an **applied scenario**, not another definition card.

## Match the method to the component

| Component | Primary practice |
|---|---|
| Facts and terminology | Spaced retrieval with corrective feedback |
| Concepts and mental models | Explain relationships, compare examples, and predict consequences |
| Cognitive procedures | Worked examples, faded guidance, then independent problems |
| Perceptual judgment | Classify and contrast labeled examples |
| Motor procedures | Demonstration, physical repetitions, and sensory or video feedback |
| Creative judgment | Analyze exemplars, imitate deliberately, produce volume, and receive critique |
| Real-world performance | Representative tasks under realistic constraints |

Use supporting knowledge only when it enables the target decision or performance. Do not substitute fact recall for a real procedure, judgment, or performance task.

For material with many interacting parts, confirm understanding before cold retrieval. Use elaborated retrieval that explains the mechanism and why the alternative fails, not atomic recall. If a cold attempt fails with signs of overload, drop to a worked example plus self-explanation rather than more recall.

## Evidence by target depth

| Target | Evidence that is enough to move on |
|---|---|
| Awareness | Recognizes the concept and its purpose; one example may be enough. |
| Basic understanding | Explains the causal model and completes one small application. |
| Working competence | Applies the model independently in fresh cases with changed governing conditions. |
| Reliable performance | Transfers under realistic constraints, identifies boundaries and trade-offs, and retains the capability after delay. |

Do not infer mastery from agreement, a prompted repetition, or a reworked example.

## Choose the rep

- **Recall:** retrieve a fact, rule, or causal chain without notes.
- **Apply:** solve or build in a fresh case.
- **Discriminate:** choose between plausible tools or explanations and reject the closest alternative.
- **Compare:** two cases that share a mechanism with different surfaces, or two confusable tools; name the shared structure and the discriminating feature.
- **Boundary test:** predict what changes when a governing constraint changes or identify when not to use the model.
- **Forensic audit:** find a hidden flaw, trace why it fails, and propose a repair.
- **Teach-back:** explain the mechanism and its limits in plain language.
- **Performance:** complete the target task under its real constraints.

Mutate governing conditions, such as inputs, scale, state, failure mode, cost, uncertainty, or competing options, not merely surface wording.

Prefer free production over fixed options. When a rep does use options, such as a quick quiz, keep every option the same length and format and make each distractor a mistake someone could genuinely make, so nothing but the knowledge separates them.

Vary the correct option's position. Use an available randomness tool when possible; for example, a shell-enabled agent can draw a slot with `python3 -c 'import random; print(random.randint(1, 4))'`. Without such a tool, vary positions across questions and avoid claiming statistical randomness. An HTML exercise can shuffle its options at render time.

### Repeat the skeleton, rotate the problem

A default to weigh, not a rule. Repetition is how a pattern becomes automatic, like a shooter's form, so drilling a skeleton is valuable. The thing to watch is re-solving the *same problem*: after a few passes it can measure memory of that solution more than command of the rule. Varied examples tend to transfer better to new problems than the same example repeated (Butler et al. 2017).

Things that usually help:

- Short cold writes of a bare skeleton (a sliding-window loop, binary-search bounds, a request-flow outline) as a warm-up, when the pattern is not yet automatic.
- After teaching, reaching for an isomorph: same governing structure, different story, data shape, or objective. Each one is also a skeleton rep.
- Bringing a seen problem back after some delay as a check, rather than as the main rep session after session.
- Treating a pass on a seen problem as weaker evidence than a pass on an unseen one when deciding what is solid.

Use judgment from what you see in the session and what the learner seems to need. Redoing a problem can be the right call, for example when the last attempt broke on the skeleton itself, or when they want another go at it.

## Sequence and mix reps

For a new operation, use a worked example and a few blocked reps until the learner can complete the standard case independently. Then interleave nearby, plausibly confusable cases so the task includes selecting the right operation, not only executing one already selected. Interleave when the confusion is between similar categories; block until they can name the defining feature of one category.

After basic competence, vary one governing condition at a time. Use variation to test a rule that has already been established, not to create random overload before the standard case is understood.

## Calibrate volume

- A confident, correct attempt at the requested depth earns one meaningful variation before advancing.
- A hesitant or hinted attempt remains developing; add a blind variation.
- A wrong model requires repair, then a fresh application.
- Add multiple varied reps only when the learner selected reliable performance or evidence shows fragile transfer.
- One correct cold retrieval per item per session is enough; spread further retrievals across sessions.

Do not use arbitrary quotas. Time pressure and no-hint work are tools for a chosen performance target, not default proof of learning.

Prefer depth over breadth within a session: one concept carried from cold test through repair to a changed application beats five concepts touched once each. Fragmenting a session across many atoms costs sustained focus and returns less than the queue appears to promise.

After a guess, give the correct model immediately. In a retrieval rep, let the whole attempt finish before correcting.

## Assessment design

State the capability, constraints, allowed resources, evidence standard, and pass consequence before starting. Combine concepts only when integration is the target. A fair assessment tests the model, not surprise terminology or irrelevant working-memory load.

Afterward, classify failure precisely: recall lapse, incorrect model, transfer failure, execution error, or environmental constraint. Record the smallest repair needed and retest it in a new case.

## Performance under pressure

Use when the learner explicitly chooses reliable performance under pressure or the course contract requires it. It supplements normal teaching and practice; it does not impose elite-training volume by default.

### Protect diagnostic effort

Use focused practice periods with one concrete output. When errors become careless or fatigue-driven rather than diagnostic, stop, take a break, or return to a lower-load rep. Do not treat exhaustion, fixed session length, or volume as evidence of readiness.

### Design the performance environment

1. Name the real task, constraints, stakes, time limit, allowed tools, and quality standard.
2. Build the required model and working competence before adding pressure.
3. Introduce one realistic constraint at a time: time, ambiguity, interruption, incomplete information, scale, failure, or skeptical review.
4. Run a cold performance, evaluate observable output, and classify the failure.
5. Repair the smallest weak rule or execution step, then rerun a changed scenario.

### Reliable evidence

Use the course's stated completion evidence. For consequential capabilities, look for retained cold retrieval, transfer across changed conditions, clear boundary reasoning, and at least one realistic performance. Do not substitute exhaustion, artificial hostility, or a fixed rep count for valid evidence.

Treat pressure practice as diagnostic, not punishment. State constraints before the attempt, preserve enough challenge to produce evidence, and adjust difficulty when it measures irrelevant overload rather than the target capability.
