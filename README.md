# Vertical Accretion / Descent Lab

Vertical Accretion is an exploratory simulation laboratory about a small population making progressively deeper space usable by physically changing its environment.

It begins from the working **Foundry** apparatus rather than from a blank application. The experiment is interested in autonomous descent, terrain deformation, construction, material logistics, gravity, accumulated infrastructure, and the possibility that a mature environment can become a readable record of the decisions that produced it.

This repository is intentionally small. It is both a runnable artifact and a self-contained handoff for humans or models who want to reproduce, extend, challenge, or fork the experiment.

## Start here

The repository contains three authoritative expedition artifacts:

- [VERTICAL_ACCRETION_DESIGN.md](./VERTICAL_ACCRETION_DESIGN.md) — the implementation contract: research questions, fixed invariants, inherited capabilities, open decisions, non-goals, and success conditions.
- [index.html](./index.html) — the inherited executable Foundry apparatus and working implementation surface. Do not treat it as disposable scaffolding.
- [VERTICAL_ACCRETION_REFERENCE.png](./VERTICAL_ACCRETION_REFERENCE.png) — perceptual reference evidence for how a mature run might read. It is not a scene to reproduce or a target state.

The design contract governs interpretation of the executable and reference image.

---

## Model handoff

If you are a model being asked to realize or continue Vertical Accretion, work directly from this repository.

### 1. Establish the evidence

Read [VERTICAL_ACCRETION_DESIGN.md](./VERTICAL_ACCRETION_DESIGN.md) completely before making implementation decisions.

Inspect [index.html](./index.html) as executable inherited machinery. Determine what already works before changing it.

Inspect [VERTICAL_ACCRETION_REFERENCE.png](./VERTICAL_ACCRETION_REFERENCE.png) under the perceptual-reference rules in the design contract.

Do not infer hidden architecture, requirements, backstory, or intended systems beyond the repository evidence.

### 2. Preserve inherited machinery until evidence says otherwise

Foundry already contains substantial working terrain, physics, material-flow, ECS, camera, interaction, diagnostic, and procedural machinery. These are inherited capabilities, not problems to solve again.

Do not replace working machinery because another implementation seems cleaner, more general, more familiar, or more elegant. Modify inherited systems when executable evidence shows that Vertical Accretion requires it.

The existing ECS is a required extensibility surface. Extend it where new independently composable behavior is earned; do not retreat into payload-specific monolithic actors or invent a large speculative component ontology.

### 3. Build through executable evidence

Do not return a plan in place of the experiment.

Implement, run, inspect, diagnose, refine, and continue. Preserve successful behavior as the realization grows. When an approach fails, repair or replace it rather than preserving it merely because work has already been invested.

Make ordinary engineering, architectural, procedural, simulation, and visual decisions yourself. Surface a decision only when choosing one interpretation would materially close a research question that the design contract deliberately leaves open.

Keep runtime failures visible and diagnostically useful.

### 4. Preserve the experiment's epistemology

The simulation should earn its forms.

Do not begin from architectural nouns and force the world to instantiate them. Prefer physical operations and consequences from which recognizable infrastructure can emerge.

Natural terrain is legitimate infrastructure. Construction and excavation answer insufficient access; they are not prerequisites for movement.

Traversal is logistical rather than merely topological: agents and relevant material should be able to move sufficiently safely and repeatedly both downward and upward.

Accumulated infrastructure should retain history rather than continually optimizing itself away.

Semantic reasoning may eventually influence intention, but deterministic physical consequence remains authoritative.

The perceptual reference is evidence, not a render target:

> **Do not build the image. Build the processes capable of earning an image like it.**

### 5. Leave the repository more legible than you found it

When implementation changes the actual conceptual model of the experiment, update the repository's semantic documentation so a later human or model can understand the new truth without reconstructing it from code archaeology.

Preserve useful history and successful mechanisms. Do not rewrite documentation merely to make it sound cleaner after the fact; distinguish current truth from evidence worth retaining.

The desired handoff is always the same: another capable model or human should be able to enter the repository, inspect the evidence, understand what is authoritative, and continue the experiment without needing the conversation that produced it.

## Reproducing the workflow

Nothing about this workflow depends on privileged conversational context.

To create a new laboratory from scratch:

1. Start with a working executable ancestor, or the smallest executable apparatus that already provides the machinery your question needs.
2. Write a compact design contract that separates fixed invariants, inherited capabilities, open research questions, non-goals, and observable success conditions.
3. Add perceptual or semantic references only when they provide evidence the contract can interpret; do not let references silently become specifications.
4. Add a short repository README that tells the next human or model which artifacts are authoritative and how to work from them.
5. Give the repository to another capable model with a lightweight instruction to work directly from it.
6. Judge progress through executable evidence, and promote discoveries back into the repository when they become part of the experiment's durable truth.

The repository, not the originating chat, should carry the experiment forward.
