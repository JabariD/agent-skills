# Agent Skills

Reusable agent skills, starting with [Tutor](skills/tutor/SKILL.md).

## Tutor

Use AI to practice your own reasoning. Tutor asks for an attempt, gives the smallest useful hint, checks the reasoning, and separates an assisted answer from something you can do independently.

It supports quick explanations, guided practice, quizzes, and optional courses with private progress records. A simple question stays a simple question. Confidence tracking is optional.

### Use it

Download or clone this repository, then copy the **entire `skills/tutor/` folder**, including `references/`, into the skill location supported by your agent. Installation locations and invocation syntax depend on the host. This is a plain Markdown skill, with no required API keys, services, or other skills.

If your agent does not discover skills automatically, point it at `skills/tutor/SKILL.md` and ask it to follow that file and the relevant linked references. Keep the full folder available; pasting the entrypoint alone omits the teaching references.

Try:

> Use Tutor to help me understand this concept. Ask me what I think first, then give me a small example to work through.

> I cannot read music yet. Help me identify a few melody notes, one step at a time. Let me try before giving the answer.

> Create a course for learning Python so I can write a small script that cleans up a CSV. I have 20 minutes per session. Do not track confidence scores.

For a durable course, choose a **private workspace outside this repository**. Tutor keeps course state, attempts, and learning records there. This repository contains instructions and blank templates only.

### What it can establish

An assisted solve can guide the next lesson. It does not prove unaided retention or transfer. Tutor asks for evidence appropriate to the target, including later independent attempts when durable capability matters. The skill is a teaching workflow, not a validated intervention or a guarantee of learning outcomes.

The general approach was inspired by [Matt Pocock's agent skills](https://github.com/mattpocock/skills), then customized around independent attempts, feedback, and durable learning.
