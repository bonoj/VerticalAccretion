# Vertical Accretion / Descent Lab

<p align="center">
  <img src="./VERTICAL_ACCRETION_REFERENCE.png" alt="Vertical Accretion" width="900">
</p>

Vertical Accretion is a deterministic embodied descent experiment about progressively making inaccessible nearby space operationally reachable through physical exploration, excavation, logistics, and construction.

The repository is intentionally small. Its live surface should answer two questions without requiring conversational context:

1. **What can the experiment actually do?**
2. **What do those capabilities currently mean?**

## Start here

Read these in order:

1. [SEMANTIC_SURFACE.md](./SEMANTIC_SURFACE.md) — the present-tense semantic interpretation of the accepted experiment: authority boundaries, earned capabilities, important distinctions, and explicit non-claims.
2. [index.html](./index.html) — the accepted executable head. This is the ground truth for whether a capability actually exists.
3. [VERTICAL_ACCRETION_REFERENCE.png](./VERTICAL_ACCRETION_REFERENCE.png) — perceptual evidence for the geological/material/structural character of a mature run. It is evidence, not a scene to reproduce.

The executable governs capability. The semantic surface governs the repository's present interpretation of that capability.

If they materially disagree, executable behavior is evidence that the semantic surface needs revision.

Historical designs, expedition specifications, experiment logs, rejected candidates, and prior handoffs live in Git history. They are archaeology, not additional current authority.

## Working posture

Work from semantic intent and executable evidence.

Preserve the distinctions in the semantic surface unless new executable evidence earns a change. Preserve useful implementation machinery when it helps, but do not treat current code architecture, helper names, constants, state-machine decomposition, or historical implementation choices as semantic invariants.

A future implementation may substantially replace today's machinery while preserving the experiment's meaning. Conversely, changing code does not automatically change the semantic surface: a new semantic claim should be earned by executable behavior.

The central loop is:

**local physical evidence → embodied intention → physically reachable intervention → logistics → physical consequence → new local evidence**

The current experiment is simulation-forward. Ordinary engineering decisions belong to the implementer. When behavior is uncertain, prefer implementation, execution, inspection, diagnosis, and refinement over speculative architecture.

Keep failures visible. Do not silently convert physical limitations into permissions merely to make a run continue.

## Semantic maintenance

Update [SEMANTIC_SURFACE.md](./SEMANTIC_SURFACE.md) when executable evidence materially changes what the project knows about itself.

Do not use the semantic surface as a roadmap or wish list. It describes what the accepted executable has earned now.

Temporary expedition briefs and working specifications are useful when a concrete investigation needs them. They do not become permanent root authority merely because they helped produce a successful change. Once their relevant discoveries have been incorporated into the accepted executable and semantic surface, Git history is sufficient archaeology.

The live root should remain legible to a capable human or model arriving cold.

## Executable state

[index.html](./index.html) is the currently accepted executable head.

Do not replace, delete, or publish over it without explicit acceptance from the person directing the experiment. A working implementation may be preserved in Git while it is under investigation, but superseded candidates should not accumulate in the live root as competing versions of present truth.

Acceptance and transport are separate concerns.

## Artifact transport — FUUTP

Use [FUUTP](https://github.com/bonoj/FUUTP) when an artifact must cross repository, model, conversation, or execution-runtime boundaries and the ordinary direct path is insufficient.

The transport invariant is simple:

**Git is durable working storage. Execution runtimes are temporary working space. Conversation carries intent, observations, decisions, and reports—not artifact bytes.**

Prefer direct repository reads and writes when they preserve exact fidelity. When that seam fails or cannot carry the artifact, read the current FUUTP README and use the simplest exact-fidelity route available.

Transport does not authorize semantic change, reconstruction, minification, refactoring, or canonical promotion. Human download/upload or copy/paste is a last-resort transport failure state, not the normal workflow.

## Continuing the experiment

A capable successor should be able to enter from this repository alone:

- read the semantic surface;
- inspect and execute the accepted head;
- identify a concrete question or observed failure;
- alter or replace implementation as needed without accidentally inheriting archaeological constraints;
- test the result through executable evidence;
- revise the semantic surface only when the evidence earns a new present-tense understanding.

The repository should preserve **understanding and capability**, not ceremony.

Git history preserves how we got here.
