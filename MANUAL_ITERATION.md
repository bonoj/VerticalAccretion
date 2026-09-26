# Vertical Accretion — Manual Iteration Handoff

## Purpose

This is the replaceable handoff for the **current working expedition**. It exists so a fresh conversation can resume from repository state without reconstructing the previous chat.

Read [README.md](./README.md) first and follow its authority and inspect → spec when warranted → implement → validate → observe workflow.

## Current executable lineage

The protected accepted E1 head remains:

- [`index.html`](./index.html) — canonical accepted executable. **Do not overwrite or promote over it without explicit human acceptance.**

The current experimental executable is:

- [`candidates/vertical_accretion_async_workers_candidate.html`](./candidates/vertical_accretion_async_workers_candidate.html) — asynchronous-worker candidate preserved from the current manual iteration.
- Git blob identity: `80aca0a4e1238e640dd2cca7a7796eacf7d83ff7`.

This candidate is evidence and the starting implementation surface for the next pass. It is **not canonical**.

## Active implementation contract

The next work is governed by:

- [`VERTICAL_ACCRETION_TEAM_COMMITMENT_SPEC.md`](./VERTICAL_ACCRETION_TEAM_COMMITMENT_SPEC.md)

The spec was written after code archaeology and direct observation of the asynchronous candidate. Do not replace its ownership model with remembered chat context.

Its core causal boundary is:

> **Coordination chooses the intervention. Logistics realizes it. Physics decides what happens.**

The physical world does not decide what work is strategically valid. It exposes physical facts, predicates, and deterministic consequences. A team decision selects a specific intervention. Only then do embodied logistics begin.

A foreman entity is not required. Genuine team deliberation is deliberately deferred. For this expedition, use the smallest deterministic, isolated, replaceable surrogate for team commitment.

## Why this pass exists

The asynchronous worker implementation successfully exposed a deeper scheduling/ownership error that previous serialization had hidden.

Observed failure at seed 741 included:

- multiple sibling wooden works growing from nearby possibilities;
- excavation occurring beneath/around existing works;
- speculative plank retrieval driven by globally enumerated placement demand;
- eventual fatal `History bound reached` instrumentation failure.

The important diagnosis is **not** “ban concurrent work” and not “the world should expose the best edge.”

The current machinery collapses:

```
physical possibility
→ intentional work
→ logistics
```

The required ownership is:

```
physical world
→ perception / possible interventions
→ team decision
→ persistent intervention commitment
→ logistical decomposition
→ asynchronous embodied execution
→ physical consequence
→ observe changed world
→ next team decision
```

## Critical invariants

- No construction material retrieval without a **specific committed placement**.
- No excavation merely because terrain is geometrically removable; excavation also requires a team commitment.
- Workers execute asynchronously below the commitment boundary.
- A completed placement does **not** automatically mean “place another plank.”
- A completed excavation does **not** automatically mean “excavate again.”
- After each intervention, topology/support/terrain consequences become current truth before the next team decision.
- Immediately before placement or excavation, revalidate the intended physical action against the current world.
- Commit-time validation asks whether the action **can physically happen now**, not whether it is strategically good.
- If a carried plank becomes orphaned by invalidation, preserve embodied state; do not invent cleanup or opportunistic retargeting.
- Do not add `Foreman`, `BridgeProject`, `Switchback`, `continueBridge`, `noBranches`, or infrastructure-protection semantics.
- Physical failure remains legitimate. Digging away support may cause a member to fall.
- Logging/history capacity must not terminate physics.

## Expected emergent result

The immediate experimental goal is to watch the team continue downward through natural traversal, excavation, and finite member placement until they either:

- consume all available planks while continued placement remains selected and physically viable; or
- reach an honest physical/material/decision dead end.

During ordinary sustained continuation we should **not** see sibling branching plank works.

That is an expected consequence of coherent team commitment and decision continuity, **not a hard-coded no-branch rule**.

A later branch is legitimate if the previous direction becomes invalid, is abandoned, or the team decision mechanism selects another continuation.

Before works exist, workers roaming and surveying different parts of the hillside is fine. Exploration does not itself authorize mutation.

## Current code archaeology that should not be rediscovered from scratch

The asynchronous candidate currently has:

- deterministic fixed-step sequential ECS execution;
- per-worker persistent Activity state;
- independent worker movement/work timing;
- physical finite member entities;
- physical terrain deformation and representative spoil;
- support/gravity consequences;
- topology refresh after placement/removal;
- stale-path rerouting rather than automatic isolation.

The problematic current layer is centered around `vaDeriveWork()` and its consumers:

- it scans reachable nodes and turns surveyed unreachable neighbors directly into `remove` / `place` work;
- it globally scores those mutations;
- empty workers prefer available excavation;
- member carriers prefer available placement;
- placement opportunity count drives member retrieval demand.

Sequential worker stepping means there is no true simultaneous placement race. Earlier same-step mutations are visible to later workers. Preserve that determinism; do not introduce JS async, threads, promises, locks, or random timing.

Existing `vaPlace()` already performs useful physical support/length checks and refreshes topology afterward, but its strategic predicate is too weak because stale globally-derived work can still look physically placeable.

Existing `vaRemove()` mutates a corridor broader than a nominal edge, so an excavation can physically undermine nearby support. That consequence is legitimate; arbitrary excavation selection is the ownership problem.

## Implementation cadence

Follow the spec in bounded passes. Do **not** implement the whole correction in one rewrite.

### Pass A — ownership seam

Start here.

- establish explicit provisional team commitment state;
- stop treating all physical possibilities as active jobs;
- remove placement-count → plank-retrieval coupling;
- require commitment before excavation;
- require committed placement before member retrieval;
- preserve asynchronous Activity machinery;
- make history exhaustion nonfatal if needed for observation.

**Pass-A stop/probe:** with no active commitment, workers must not excavate or fetch a plank merely because physical possibilities exist.

Do not proceed into Pass B merely because Pass A compiles. Run and inspect the Pass-A probes first.

### Later passes

The spec defines subsequent bounded work:

- **Pass B:** embodied execution of committed interventions and commit-time physical revalidation.
- **Pass C:** deliberately boring/replaceable deterministic team-decision surrogate with decision continuity.
- **Pass D:** long-run observation, deterministic replay, material exhaustion/termination, and repair.

Let executable evidence determine whether each pass is ready for the next.

## Known control

Seed **741** remains the primary regression/control specimen.

The current async candidate reached a useful failure state rather than a successful expedition. Preserve that failure as evidence; do not rewrite history to make the candidate appear correct.

## Durable context

Also consult as needed:

- [`VERTICAL_ACCRETION_DESIGN.md`](./VERTICAL_ACCRETION_DESIGN.md) — experiment intent and fixed invariants.
- [`EXPERIMENT_LOG.md`](./EXPERIMENT_LOG.md) — accepted evidence and archaeology.
- [`VERTICAL_ACCRETION_REFERENCE.png`](./VERTICAL_ACCRETION_REFERENCE.png) — perceptual reference evidence, not target geometry.
- [`README.md`](./README.md) — repository authority and workflow.

Historical failed semantic/LLM-agent work is archaeology only. Do not revive it.

## Fresh-thread instruction

A fresh conversation should be able to begin with the repository alone:

> Work directly from this repository. Read README.md and MANUAL_ITERATION.md, then follow the active team-commitment spec. Begin at Pass A. Inspect the preserved asynchronous candidate before editing. Do not promote over index.html without explicit acceptance.

The repository should carry the reasoning needed to continue. If the next thread requires reconstruction of this conversation, this handoff is insufficient and should be repaired.
