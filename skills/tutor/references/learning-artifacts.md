# Learning Artifacts

Create a durable artifact only when it improves retrieval, inspection, reuse, or a concrete learning task. Text remains the canonical explanation.

## Two kinds, with different lifetimes

- **A lesson** is consumed once. It carries the learner from not having a model to having one, then its job is done. Lessons are rarely revisited.
- **A reference** is revisited indefinitely: a cheat sheet, glossary, reference algorithm, decision checklist, or diagram. It is the compressed residue of a lesson, built for lookup rather than for reading through.

Build references deliberately; they are where the durable value accumulates. Do not build a lesson as though it were a reference, and do not leave a hard-won model trapped in a session log where it will never be found again.

## The course glossary

A course glossary is the highest-value reference for any topic with its own nomenclature. Once it exists, later lessons use its terms and do not silently redefine them.

Promote a term only once the learner has used it correctly without prompting. The entry records a compressed model they already hold; it is not a definition handed to them in advance. Writing it is itself a rep, so ask them for the definition before supplying one.

- Define what the term is in one or two sentences, not what it does or how to perform it.
- Keep one word per concept and list the rejected synonyms under `_Avoid_`, so the language compresses instead of accumulating.
- Use the glossary's own terms inside later definitions. That is what makes the harder terms cheap to grasp.
- When the wider field uses a term loosely, record the resolution this course holds to.
- Revise an entry in place as understanding deepens. A week-one definition is often wrong by week six.

A course glossary lives at `artifacts/glossary.md`. Group terms under subheadings once natural clusters appear:

```markdown
# <Course title> Glossary

<One sentence on what this glossary covers.>

## Terms

**Back-pressure**:
A consumer signalling a producer to slow down when it cannot keep up.
_Avoid_: throttling, flow control
```

## The polish trap

A beautiful artifact is a fluency machine. Reading a well-typeset explanation with the answers laid out produces a strong sense of understanding and no retrieval whatsoever, which is exactly the failure mode this skill exists to prevent. Effort spent making a lesson elegant is effort that produced no reps.

Two rules follow:

1. **The learner produces the session artifact; the tutor produces the reference.** The thing that provides evidence is the thing they made from a blank page. A polished document the tutor made about the topic is a resource, never evidence.
2. **Every lesson artifact ends in an unaided production task.** If it can be read to completion without producing anything, it is content, not a lesson. Put the answers behind a fold, a second file, or a later turn so that the retrieval attempt has to happen first.

A reference the learner explicitly asks for (cheat sheet, flashcards, glossary, quiz) gets built; offer the production rep alongside it rather than as a gate.

Invest in appearance only once the content has already earned reps. Legible beats beautiful.

## Choose the smallest precise form

1. Markdown or ASCII for a definition, comparison, trace, or immediate sketch.
2. Mermaid or Graphviz source plus SVG for state, dependency, sequence, and flow relationships.
3. A self-contained HTML/SVG exercise only when interaction, spatial manipulation, or time is part of the concept.
4. A generated image only for contextual intuition or real-world appearance, never as the authoritative source for technical labels or causal arrows.

## Rules

- State what every visual relationship means in text; label edges and provide a legend for meaningful encoding.
- Retain editable source beside any render and provide a text fallback.
- Make a visual an active rep: ask for a prediction, annotation, mutation, trace, or recreation.
- Default to static artifacts. Add animation only when state over time is the concept, and give the learner control to pause or inspect it.
- Reuse an existing course artifact before making another version of the same reference. When a second artifact would duplicate part of a first, extract the shared part once and link to it.
- Cite sources inside an artifact when the claim is contestable or the learner will need to revisit it; follow [sources.md](sources.md).

For a persistent course, store reusable artifacts under `artifacts/` and record them in the course's artifact index. Do not create an artifact library for a one-off explanation unless the learner asks to keep it.
