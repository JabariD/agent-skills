# Persistent Learning Programs

## Contents

- [Operating model](#1-operating-model)
- [When to use this protocol](#2-when-to-use-this-protocol)
- [Create a program](#3-create-a-program)
- [The ledger](#4-the-ledger)
- [Run or resume a session](#5-run-or-resume-a-session)
- [Maintenance contacts](#6-maintenance-contacts)
- [Concept records and mastery](#7-concept-records-and-mastery)
- [Spaced retrieval and scheduling](#8-spaced-retrieval-and-scheduling)
- [Assessments and completion](#9-assessments-and-completion)
- [Program maintenance](#10-program-maintenance)
- [Resources and artifacts](#11-resources-and-artifacts)
- [Boundaries](#12-boundaries)

Use this protocol when the learner asks to create, continue, review, assess, pause, or inspect a multi-session course. It adds durable course state to the `tutor` skill; use it with `teaching-loop.md` and the selected activity reference.

## 1. Operating model

A learning program lives in a learner-chosen private workspace, outside this skill and any public repository. Confirm that location before creating the first durable course, then reuse it for later sessions. Do not store learner records in this published skill folder.

```text
<learner-workspace>/courses/<course-slug>/
  course.md
  ledger.md                    # required; append-only evidence record
  concepts/
    <concept-slug>.md
  sessions/                    # only sessions that produced a learner attempt
    YYYY-MM-DD-HHMM.md
  maintenance/                 # course edits, scope changes, admin. Not progress.
    YYYY-MM-DD-HHMM.md
  assessments/
    <assessment-slug>.md
  resources.md                 # optional; only when curated sources need maintenance
  artifacts/                   # optional; reusable reference material
```

Use lowercase kebab-case for folder and file names. Create folders only when a program begins. Do not create a generic course merely because a topic was mentioned.

The files are the canonical learner record. Read the relevant files before teaching, reviewing, or updating. Do not rely on chat history as course memory.

A program is a loop, not a fixed chapter list:

```text
load state → report the ledger → reinstate context → cold test what is due
→ choose the limiting next step → teach or practice
→ collect observable evidence → write the ledger row → update state → schedule review
```

A lesson being explained is not proof of learning. A correct card or two correct questions are data points, not a mastery decision. Advance a concept only from observable evidence: a cold explanation, applied solve, artifact, diagnosis, teach-back, or realistic performance. Make validation proportional to the course target and the concept's consequences: a low-stakes awareness fact may need one clean retrieval; a causal, procedural, or decision-critical concept needs independent retrieval plus varied transfer before it is called reliable.

**The structure is not the work.** A course folder can be improved indefinitely, and improving it produces a strong and entirely false sense of progress. Measure a course by its ledger rows, never by the quality of its plan.

## 2. When to use this protocol

Load this file for requests such as:

- "Create a course for X" or "make me a learning program"
- "Resume X," "continue X," or "what were we doing?"
- "What is due for review?" or "quiz me on X"
- "Show my learning dashboard," "pause X," or "give me a mock"

Use normal in-session tutoring for one-off questions unless the learner explicitly wants durable tracking. If uncertain, ask whether the topic should become a persistent program.

## 3. Create a program

### Intake

Ask only for information that changes the program. Obtain it conversationally over one or more turns; do not block useful progress on optional detail.

1. **Mission (required):** The specific thing the learner will be able to do in a real situation, and why that matters now. See below; this one is not optional.
2. **Outcome:** What should the learner be able to do in a real situation?
3. **Current model:** What does the learner already know or believe? Treat the answer as a hypothesis, not a starting level; see "Baseline probe" below.
4. **Depth:** awareness, basic understanding, working competence, or reliable performance under pressure.
5. **Constraints:** deadline, sustainable time budget, required sources, and scope exclusions.
6. **Completion evidence:** What concrete output would prove the target was reached?

For an outcome with a clear performance environment, make that environment the final assessment. Examples: a timed mock interview, blind coding solve, fault diagnosis, explained diagram, or functioning build.

### The mission is mandatory and concrete

Every course states its mission in `course.md` before any teaching happens. A mission is not the course outcome restated at a higher altitude. It is a specific, dated, real situation:

- Not: "maintain algorithmic fluency as a senior engineer."
- Yes: "in six weeks, solve an unfamiliar medium problem in Python, cold, in 35 minutes, narrating, because I intend to interview in the spring."

- Not: "reason about systems from first principles."
- Yes: "turn the next ambiguous request my lead hands me into a one-page decision brief they can disagree with concretely."

An abstract mission produces abstract lessons, and abstract lessons are impossible to fail, which is precisely why they feel good. If the learner cannot state the mission concretely, that is the first session's work. Do not proceed to content with the mission unset, and do not invent one on their behalf.

Missions change as capability develops. That is normal: update `course.md`, run the [mission-map sync](#10-program-maintenance), and log it in `maintenance/`, after confirming with the learner.

### Proposal and approval

Before creating files, propose a concise dependency-based course map with milestones. Keep it a draft until the learner approves it. A map should describe prerequisites and evidence, not merely a list of topics.

Keep the initial map small. A twelve-milestone map for a course with zero completed reps is a planning artifact, not a curriculum. Prefer three milestones that will actually be attempted.

### Baseline probe

Self-reported prior knowledge can miss gaps. Open the first session with a short cold probe of the first milestone's prerequisites: a few unaided blank-page or applied prompts. Take predictions only when calibration tracking is enabled. Write the results as ledger rows, and fill `Starting model` from what the probe showed, not only from self-report.

Before the first teaching segment, list the terms and prior concepts it will assume, and check each one with a quick cold question. Teach any that fail before building on them.

After approval, create the course folder, `course.md`, and `ledger.md`. Create a concept file when that concept is introduced or needed for review; do not pre-create dozens of empty files.

### External validation

For each milestone, choose a check outside the tutor's own judgment: a test run, a reference recording, a human review, or an observed real-world result. Match it to the target and available access. Public posts, external messages, and contributions require the learner's explicit authorization; a course plan does not grant it.

### `course.md` template

```markdown
# <Course title>

## Mission
- <The specific thing the learner will be able to do, in a real situation, by when, and why it matters now.>

## Status
- State: active | paused | completed
- Created: YYYY-MM-DD
- Last session: YYYY-MM-DD-HHMM (or: none yet)
- Unaided cold reps, last 30 days: <n>
- Calibration tracking: on | off
- Calibration gap: <signed number, not yet measured, or not tracked>
- Current focus: <one limiting concept or milestone>
- Anchor: <source and section the learner is working through, with position | none, and why>
- Next entry point: <the smallest concrete next action the learner performs>

## Course contract
- Outcome:
- Target depth:
- Deadline or cadence:
- Time budget:
- In scope:
- Explicitly out of scope:
- Learner preferences:
- Resource index: resources.md | none
- Artifact index: artifacts/ | none
- Completion evidence:

## Starting model
- What the learner already knows:
- Assumptions to test:

## Program map
| Milestone | Concepts / dependencies | Required evidence | External check | State |
|---|---|---|---|---|
| Foundations | ... | ... | ... | not started |

## Cross-course error patterns
- <Only recurring patterns that affect multiple concepts>

## Parking lot
- <Interesting but intentionally deferred tangent> , revisit after <condition>

## Recent assessment evidence
- <date>: <assessment> , <result and next consequence>
```

## 4. The ledger

`ledger.md` is append-only. One row per evidence attempt. Never edit or delete a past row; a wrong prediction is the data.

```markdown
# Ledger , <Course title>

Append-only. One row per evidence attempt. Never revise a past row.

- `predicted`: the learner's stated probability, 0-100, given before the named test. Record its test ID, timing, resources, and success criterion in the note.
- `scored`: 100 correct and unaided, 50 correct with material gaps or one hint, 0 wrong model or could not produce.
- `success`: binary 100 or 0 on the specified test, distinct from `scored`; pending predictions have no outcome. Pair later outcomes by test ID in an appended row.
- `aided`: y if the tutor supplied reasoning, hints, or structure during the attempt. Aided rows never promote a concept.
- `delay`: days since the material was last taught or reviewed. 0 means same-session, which tests fluency only.
- Item (optional): note `[seen]` or `[unseen]` when it matters whether the learner had met this exact problem before; see [Repeat the skeleton, rotate the problem](practice-and-assessment.md#repeat-the-skeleton-rotate-the-problem).

| Date | Concept | Mode | Predicted | Scored | Aided | Delay | Success | Test ID / gap type / note |
|---|---|---|---|---|---|---|---|---|
```

At the start of every session, compute and report from the ledger before anything else:

1. **Unaided cold reps in the last 30 days** (rows where `aided` is n and `delay` is 1 or more). Report zero plainly; a new course may still contain valid same-session practice without delayed evidence yet.
2. When calibration tracking is enabled, **signed calibration gap** over completed prediction/outcome pairs, following the scoring reference below. Report the pair count and exclude pending or legacy unpaired rows; say unavailable when there are no pairs. Skip calibration reporting when the learner opted out.
3. When tracking is enabled, **absolute calibration error** and **resolution** when there are enough completed pairs to be meaningful, roughly ten or more.

Existing ledgers keep their columns and historical rows. New attempts may put the test ID and binary outcome in the note column until a new ledger uses the expanded template; never infer a legacy row's predicted event or rewrite it as valid calibration.

Scoring rules and the benchmark for good calibration live in [practice-and-assessment.md](practice-and-assessment.md#calibration-scoring).

Report these numbers even when they are unflattering, especially then. Do not editorialise them into encouragement, and do not let an improving calibration gap become the new thing that feels like progress; it is an instrument, not a score.

## 5. Run or resume a session

A session requires a learner attempt. If no attempt happens, it is a maintenance contact and is logged in `maintenance/`.

1. Read `course.md`, `ledger.md`, the last relevant session, and concept files for the current focus and due reviews.
2. Report the ledger numbers from section 4.
3. Give a brief context reinstatement: the last breakthrough, the active goal, and the exact next step. Do not re-teach the whole course.
4. Open with a cold test before any restudy. Blank-page recall is the default; see [practice-and-assessment.md](practice-and-assessment.md#blank-page-recall). Type every gap rather than noting it.
5. Run due reviews in one batch at the start, not scattered through the session, and keep them proportionate. A normal session should not become an endless backlog-clearing exercise. When the backlog is large enough to consume the session, park the least connected items instead.
6. Select the next activity by the limiting constraint; courses do not use a mandatory lesson script:
   - new, missing, or incorrect mental model → teach the smaller atom and use a worked example when needed;
   - understood model but dependent execution → guided or faded practice;
   - weak recall or fluency → independent reps or retrieval review;
   - correct explanation but weak transfer → fresh applied scenario;
   - weak performance under pressure → timed, realistic practice;
   - recurring misconception → counterexample and error-repair exercise.

   When the course has an anchor source, a teach segment ends by assigning the matching section of it; the learner's reading record of that section can happen in-session or before the next one. See [sources.md](sources.md#session-shape-tutor-first-source-section-second).

   At the lesson opening, state the capability target, chosen mode, and why it fits. Use assessment deliberately for baselines, milestones, re-entry, or genuine uncertainty; do not default a new course to assessment when instruction is the limiting need.
7. Default to taking one concept from cold test through repair to a changed application. Adapt the depth and session shape to the learner's preferences and observed needs.
8. Follow `teaching-loop.md` and the selected activity reference. Elicit the current model when it changes the next move, build first principles, and use scaffolding only as needed. Keep explanations no longer than necessary to enable the next productive rep; if a rep exposes a broken mental model, repair that smallest atom before assigning more reps.
9. Validate at the concept's target depth. Use an unfamiliar variation, a boundary case, a counterexample, or a decision between plausible alternatives when the concept requires transfer. Do not promote capability from a prompted repetition of the just-taught example.
10. End with evidence the learner produced. Take a prediction before the final rep only when calibration tracking is enabled, and write the ledger row after it.
11. Update the concept files, `course.md`, and a new session log in `sessions/`. When the current focus moves to a different milestone, update that milestone's `State` in the program map.
12. Glossary check: if the learner used a new course term correctly and unaided this session, ask them to define it, then add their definition, tightened, to `artifacts/glossary.md`. Create the file on the first such term. Format: [learning-artifacts.md](learning-artifacts.md#the-course-glossary).

Never mark a review complete merely because it was shown to the learner. The learner must attempt retrieval or application first.

### `sessions/YYYY-MM-DD-HHMM.md` template

```markdown
# Session , YYYY-MM-DD HH:MM

## Evidence produced
- yes | no    # "no" means this file belongs in maintenance/ instead

## Intended focus
- <concept or milestone>

## Ledger at session start
- Unaided cold reps, last 30 days:
- Calibration gap:

## Context reinstatement
- Previous breakthrough:
- Starting point:

## Cold open
- Blank-page result:
- Gaps, typed: never encoded / comprehension / retrieval

## Work and evidence
- <attempt, artifact, answer, or mock-performance observation the learner produced>

## What held / what broke
- Reliable:
- Gap or misconception:
- Predicted vs scored:

## Updates made
- Ledger rows added:
- Concepts reviewed or changed:
- Glossary terms added:
- Reviews scheduled:

## Next entry point
- <smallest concrete action the learner performs next session; usually a structure to test, often via an unseen problem>
```

## 6. Maintenance contacts

Editing the contract, resequencing milestones, folding a topic in, clarifying a boundary, or renaming a concept produces no learning. Log it in `maintenance/YYYY-MM-DD-HHMM.md`:

```markdown
# Maintenance , YYYY-MM-DD HH:MM

## Change
- <what changed in the course structure>

## Reason
- <why>

## Learning impact
- None. No capability was assessed or promoted.
```

Do not write a maintenance contact into `sessions/`, do not update `Last session` for it, and do not present it as progress. When maintenance is the third consecutive contact with a course that produced no attempt, say so directly and propose the smallest real rep instead of a fourth revision. Refining a plan is the most reliable way to feel productive while learning nothing, and a course whose structure keeps improving while its ledger stays empty is exhibiting exactly that.

## 7. Concept records and mastery

A concept is not a binary "mastered" label. Track the kind of evidence needed for the course outcome.

### `concepts/<concept-slug>.md` template

```markdown
# <Concept name>

## Role
- Why it matters to this course:
- Prerequisites:
- Unlocks:

## Mental model
- Governing rule or causal mechanism:
- Concrete anchor:
- Common trap:

## Validation plan
- Target depth: awareness | basic understanding | working competence | reliable performance
- Required evidence: <specific proof appropriate to this concept>
- Required variations: <none for a simple atom, otherwise the meaningful changes to test>
- Promotion rule: <what must be true before a dimension can be called reliable>

## Current capability
| Dimension | State | Evidence |
|---|---|---|
| Explain from memory | untested | |
| Apply in a fresh case | untested | |
| Identify boundaries / trade-offs | untested | |
| Perform under target conditions | untested | |

Use `untested`, `developing`, or `reliable`. Omit dimensions that do not matter to the course target; do not manufacture drill requirements for a simple fact whose target is awareness.

## Error record
- <date>: <specific incorrect model or failure pattern> , repair: <correct causal rule or next exercise>

## Review state
- Last reviewed: YYYY-MM-DD
- Next due: YYYY-MM-DD
- Interval days: 0
- Review mode: atomic recall | causal chain | discrimination | error repair | applied scenario | performance
- Most recent grade: again | hard | good | easy

## Evidence log
- <date>: <what the learner produced and what it demonstrated>
```

### Promotion gate

Update one row only when the validation plan supports it, and only from an unaided ledger row. A correct answer after a cue, a repeated version of the worked example, or agreement with the tutor can maintain a `developing` state; it cannot promote a concept to `reliable`.

Apply promotion rules proportionately to the target depth and the cost of being wrong. The gates below define `reliable` understanding for causal, procedural, or decision-critical concepts; do not impose them on simple awareness facts.

| Capability | Minimum evidence for `reliable` |
|---|---|
| Explain from memory | An independent, cold explanation of the causal "why" and at least one boundary or failure condition. For reliable-performance or consequential targets, confirm with a second delayed explanation. |
| Apply in a fresh case | Correctly solves or chooses in at least two meaningfully different unfamiliar scenarios; explains why the choice fits and why a plausible alternative does not. |
| Identify boundaries / trade-offs | Predicts what changes when a key constraint changes, identifies when not to use the concept, and traces the failure mechanism. |
| Perform under target conditions | Produces the required output in a realistic simulation with the course's stated constraints; repeat when the stakes or target require reliability. |

Use variations that change the governing conditions rather than surface details: scale, inputs, constraints, missing information, failure modes, competing options, or the direction of the question. Ask "what if?" only when the answer tests an actual causal rule.

When an attempt fails, distinguish a recall lapse from an incorrect mental model or a transfer failure. Record the specific failure, repair the smallest broken rule, then validate it again in a new context. Do not substitute more generic cards for this repair.

Put a repeated, cross-cutting behavior in `course.md`'s error patterns. Keep local conceptual mistakes in the corresponding concept file.

## 8. Spaced retrieval and scheduling

Spaced retrieval protects knowledge after deep learning; it does not replace teaching, application, feedback, or realistic practice. Schedule the smallest review that tests the weak dimension.

Use these review modes:

| Mode | Tests |
|---|---|
| Atomic recall | a necessary fact, term, or rule |
| Causal chain | mechanism and relationships |
| Discrimination | choosing between similar tools or explanations |
| Error repair | a documented personal misconception |
| Applied scenario | transfer to a fresh context |
| Performance | execution under target constraints |

Set the retention target first: an exam date, a project date, or indefinite. Space reviews at roughly 10 to 20 percent of that interval. A target a few weeks out means gaps of days; a year out means gaps of weeks. Equal and expanding gaps perform about the same; delaying the first retrieval matters more than the shape of the schedule.

For a capability that must last beyond the current session, schedule the first cold retrieval after a night's sleep, an independent attempt after 1 to 3 days, then a changed application roughly a week later. Use the smallest review that tests the weak dimension. After this initial sequence, use the transparent adaptive schedule below. This is intentionally simpler than FSRS; use FSRS only after enough genuine review history exists to justify it.

Every review begins with a cold test before any restudy. Relearn to one correct retrieval. Three spaced relearning sessions capture most of the benefit for month-scale retention; add more only for long-horizon targets.

| Grade | Meaning | Next interval |
|---|---|---|
| again | could not retrieve or the core model was wrong | 1 day |
| hard | recalled only with material gaps or heavy effort | max(3 days, previous interval × 1.2) |
| good | correct independent retrieval or application | max(7 days, previous interval × 2) |
| easy | robust retrieval plus a fresh transfer or strong performance | max(14 days, previous interval × 3) |

Round calculated intervals up to whole days. For the first adaptive review after the initial sequence, treat the previous interval as 1 day. If the course has a deadline sooner than the calculated due date, schedule the review before the deadline and keep gaps near 10 to 20 percent of the time remaining.

Grade the attempt, not the learner's confidence. Confidence goes in the ledger as calibration data, never into the grade.

When asked "what is due," scan active concept files whose `Next due` is today or earlier. Present a short prioritized queue:

1. overdue and fragile concepts;
2. concepts blocking the current milestone;
3. maintenance reviews.

Do not auto-reschedule overdue material without an attempt. Overdue means "needs attention," not "failed." When a due concept no longer connects to an active goal, ask whether to park it rather than drill it. A review queue that has grown beyond what sessions can absorb is a signal to cut scope, not to run longer sessions.

## 9. Assessments and completion

Use an assessment when a milestone needs integration or when a target performance must be tested. An assessment should combine previously learned concepts in a fresh setting and state its constraints up front.

### `assessments/<assessment-slug>.md` template

```markdown
# <Assessment title>

- Date:
- Milestone:
- Format and constraints:
- Concepts exercised:
- Predicted success probability (optional, before the specified test):

## Prompt or scenario

## Learner's output

## Evidence-based evaluation
- Held:
- Broke:
- Error patterns:
- Predicted vs actual:
- Required repair:

## Result
- pass | partial | retry
- Next action:
```

A course is completed only when its `Completion evidence` is met, including its external checks. On completion, set the course state to `completed`, retain concept records for optional maintenance reviews, and write the final evidence in `course.md`.

## 10. Program maintenance

- **Dashboard:** Read `course.md`, `ledger.md`, and active concept files. Lead with unaided cold reps and, only when tracking is enabled, calibration gap. Then show current focus, milestone progress, due reviews, recent evidence, recurring errors, and next entry point. Do not manufacture a separate dashboard file that can drift from the canonical records.
- **Pause:** Set the state to `paused`, write the reason and next entry point, and retain all records. Pausing is a valid state, not a failure. A course that is not being practiced is better paused honestly than left `active` with an empty ledger.
- **Resume after a gap:** Re-establish the last successful context, then use a small diagnostic review before selecting new content. Do not assume the old schedule proves current recall.
- **Change scope:** Update the course contract and program map, run the mission-map sync, and log it in `maintenance/`.
- **Mission-map sync:** Run whenever the mission, pass bar, completion evidence, or program map changes, and when building a dashboard. Fix each failure in the same maintenance entry, or flag it to the learner when the fix changes what they committed to (a pass bar, a mission scope). Complete when all four hold:
  1. Every capability or format the mission names has a milestone that teaches it.
  2. Every milestone serves the mission; one that does not is parked or cut.
  3. The pass bar or completion evidence tests the whole mission scope, not one slice of it.
  4. Milestone states match `Status`: the current focus is marked active, and every gated milestone names its gate.
- **Tangents:** Put nonessential interests in the parking lot. Revisit only when their prerequisite condition is met or the learner reprioritizes them.
- **Too many active courses:** More active courses than the learner practices is itself a symptom. When several courses have empty ledgers, propose pausing all but one rather than servicing them all.

## 11. Resources and artifacts

- **Resources:** Create `resources.md` once the course has a source worth tracking. Follow [sources.md](sources.md) for the anchor source, the queue format, and the learner's verdicts; do not duplicate the index in `course.md`.
- **Artifacts:** Create `artifacts/` for reusable reference material: a reference sheet, glossary, diagram source and render, or interactive exercise. Follow [learning-artifacts.md](learning-artifacts.md) and retain editable source with any render. A course glossary, once created, is binding on later lessons.
- **Preferences:** Record stable, course-specific teaching preferences in `course.md`; do not create a parallel notes file.

## 12. Boundaries

Do not add automatic reminders, cron jobs, task creation, external messaging, or background automation as part of a learning program. The default is persistent state that is consulted when the learner initiates a session.

If the learner later requests reminders, design a separate, opt-in scheduler with explicit destination, cadence, opt-out, and a rule that it never marks learning complete without the learner's attempted response.
