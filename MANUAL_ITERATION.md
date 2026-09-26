# Vertical Accretion — Manual Iteration Handoff

## Purpose

This is the lightweight, replaceable handoff for the **current human-guided iteration** on Vertical Accretion.

It exists so a fresh conversation can resume directly from repository state without reconstructing the previous chat. It is working context, not canonical design truth and not permanent history. Replace it when the active iteration changes.

Begin with this file, then read [README.md](./README.md) and follow its authority/workflow.

## Executable state

The protected accepted executable remains:

- [`index.html`](./index.html) — accepted E1 canonical head. Do not overwrite it without explicit acceptance/promotion authority.

The current working executable for the next iteration is:

- [`candidates/vertical_accretion_async_workers_candidate.html`](./candidates/vertical_accretion_async_workers_candidate.html) — asynchronous-worker candidate preserved exactly at Git blob `80aca0a4e1238e640dd2cca7a7796eacf7d83ff7`.

This candidate is evidence, not canonical state. It successfully exposed concurrency that earlier serialization had hidden, and in doing so exposed deeper ownership errors.

Known control seed: **741**.

## What the asynchronous candidate taught us

The asynchronous activity machinery itself is worth preserving:

- deterministic fixed-step simulation remains authoritative;
- workers advance independent persistent activities in simulation time;
- no JavaScript promises/threads/nondeterministic concurrency are required;
- one worker may travel while another explores or performs physical work;
- sequential ECS stepping already gives physical mutations a deterministic commit order.

The observed failure state was useful:

- multiple sibling wooden works appeared;
- workers excavated beneath/near existing works;
- workers fetched planks speculatively;
- the history bound eventually threw `History bound reached; export and start another expedition.`.

These are not reasons to return to global worker serialization.

They exposed an ownership problem.

## Core correction

The world is **not a god object** and does not decide what work is valid, best, useful, or desirable.

The world simply exists and can be acted upon.

It owns physical facts and deterministic consequences:

- geometry and material;
- support and gravity;
- occupancy;
- topology;
- whether a body can traverse current geometry;
- whether a proposed placement is physically possible now;
- whether a proposed removal can physically occur;
- what changes after an action.

Physical possibility is not intention.

Likewise, individual workers should not independently turn every physically possible mutation into construction or excavation.

There is a missing coordination boundary:

```text
PHYSICAL WORLD
        ↓
PERCEPTION / POSSIBLE INTERVENTIONS
        ↓
TEAM DECISION
"We are doing this."
        ↓
LOGISTICAL DECOMPOSITION
        ↓
ASYNCHRONOUS EMBODIED EXECUTION
        ↓
PHYSICAL CONSEQUENCE
        ↓
observe changed world
        ↓
next team decision
```

A **foreman entity is not required**. A **team decision is required**.

A future experiment may implement that decision through a foreman, consensus, disagreement, voting, negotiation, rotating authority, or something stranger. Do not solve that now.

For the current small simulation, use the smallest deterministic, explicitly provisional surrogate for a team decision.

## Hard ownership invariant for the next work

> **Coordination chooses the intervention. Logistics realizes it. Physics decides what happens.**

Construction and excavation logistics begin **only after** the team has committed to a specific intervention.

Wrong causal order:

```text
world enumerates possible placements
→ placement count becomes demand
→ workers fetch planks
→ carriers choose somewhere to put them
```

Required causal order:

```text
team commits to PLACE A→B
→ one embodied member is required
→ worker retrieves that member
→ worker travels
→ immediately before placement, current physical state is revalidated
→ place or fail
```

Excavation follows the same boundary:

```text
team commits to REMOVE at target
→ worker travels / executes
→ immediately before mutation, current physical state is revalidated
→ remove or fail
→ physical spoil/support/topology consequences occur
```

No worker excavates merely because an edge is mutable.

No worker fetches a plank merely because a placement is possible.

## Important consequence: continuation is also a decision

A placed plank does **not** mean "therefore place another plank."

After every intervention, observe the changed physical world and make another team decision.

If natural terrain is now traversable, ordinary movement/exploration may resume.

If another placement is selected, fetch and place another member.

If excavation is selected, excavate.

If the current line is no longer viable or no longer selected, the team may eventually choose another direction.

Do not add semantic project state such as:

- bridge project;
- finish bridge;
- continue bridge;
- switchback;
- no branches;
- keep same heading.

## Target behavior

The immediate experimental goal is to watch the team descend as far as it coherently can, potentially spending the entire finite plank stock.

For an ordinary sustained continuation we should **not see sibling branching plank works**.

That is not because branching is hard-coded away.

It should be an emergent consequence of coordinated commitment: once the team has selected a place to extend access, logistics execute that intervention; the changed local situation is then reconsidered before another intervention is chosen.

A later branch remains legitimate if the previous way forward becomes physically impossible or the team decision changes because another continuation is selected.

> **No branching-by-rule. No branching-by-accident.**

## What code archaeology established

The current candidate's `vaDeriveWork()` is conceptually wrong for this ownership model.

It scans home-reachable nodes and turns surveyed unreachable neighbors directly into `remove` or `place` work items, then scores them. This promotes geometric possibility directly into intentional work.

The current async selector compounds the problem:

- empty workers prioritize available excavation;
- member carriers prioritize available placement;
- placement-opportunity count creates lumber demand.

That is why true worker concurrency produced multiple works and arbitrary carving.

Do not repair this by making the world choose a smaller set of "best work."

The world should not choose work at all.

A data structure named `vaWork` may survive if useful, but its semantics must no longer be "every mutable edge adjacent to reachable space." It may represent committed/executing work or another clearly owned concept.

## Commit-time physical revalidation

The final thing a worker does before mutating the world is ask the physical substrate whether the **already intended action can still physically occur now**.

For placement, re-evaluate current geometry/support/reach/occupancy using the existing physical predicates.

For excavation, re-evaluate the intended current geometry before removal.

Do not ask the world whether the action is strategically good.

Workers are advanced synchronously in deterministic entity order, so an earlier worker's mutation is visible before a later worker reaches its own commit point. No locks, promises, or concurrency primitives are needed at this scale.

If revalidation fails:

- do not mutate;
- record the physical failure;
- invalidate/complete the commitment as appropriate;
- preserve embodied state;
- return to team decision.

A worker carrying a now-orphaned plank keeps a real plank. Do not invent automatic cleanup or opportunistic retargeting.

## Excavation and infrastructure

Do not add `dontExcavateUnderBridge` or infrastructure immunity.

Excavating beneath a supported member may be physically possible, and the member falling afterward is legitimate physical evidence.

The problem in the async candidate is that arbitrary excavation became intentional work without team commitment—not that destructive excavation must be physically forbidden.

## History bound

The current fatal history limit is instrumentation killing physics.

Repair it so observational storage pressure is nonfatal. A deterministic ring buffer, bounded recent history plus counters, or another bounded representation is acceptable.

Invariant:

> **Instrumentation must not terminate the physical simulation.**

Keep this correction narrow.

## Implementation sequence

Do **not** do all of this in one pass.

### Pass A — Ownership seam

Establish explicit team commitment and remove speculative work demand.

- introduce provisional team commitment state;
- stop treating all derived physical possibilities as active jobs;
- remove placement-count → plank-retrieval coupling;
- make excavation require commitment;
- make member retrieval require a specific placement commitment;
- preserve asynchronous worker activities;
- make history exhaustion nonfatal if necessary for observation.

**Pass A probe:** with no active commitment, workers do not excavate or fetch a plank merely because physical possibilities exist.

Stop and inspect after Pass A. Do not automatically continue because the code compiles.

### Pass B — Embodied execution

Make one committed intervention execute correctly.

- assign concrete worker activity from commitment;
- retrieve exactly the required embodied member for placement;
- travel asynchronously;
- revalidate immediately before physical mutation;
- execute placement/removal;
- refresh support/topology;
- complete or invalidate commitment;
- preserve orphan material on failure.

**Probe:** make the member trip long. Other workers remain alive/asynchronous; exactly one member is fetched; the carrier never shops for another edge.

### Pass C — Provisional team-decision continuity

Only after A and B are observed, implement the smallest deterministic surrogate for collective choice.

Requirements:

- at most one active intervention commitment for this controlled expedition;
- choose only at decision boundaries;
- reconsider the changed state after each intervention;
- may select excavation or placement;
- no architectural nouns;
- no hard-coded branch prohibition;
- strongly preserve local continuation when the surrogate still selects that way forward;
- may abandon/revise when continuation is no longer viable or selected;
- isolated and replaceable so later genuine team deliberation can replace it.

This is not an experiment in collective intelligence. Do not add voting, dialogue, worker disagreement, LLM reasoning, a Foreman entity, or global optimal planning.

### Pass D — Long-run observation

Run the apparatus long enough to falsify it.

Look for:

- substantial or complete plank-stock consumption where continuation remains viable;
- repeated natural traversal / excavation / placement transitions;
- no speculative lumber train;
- no accidental sibling plank works;
- physically legitimate support failure still possible;
- honest stopping when material or continuation is exhausted;
- deterministic replay;
- no fatal history exhaustion.

Repair observed causal failures, not imagined future architecture.

## Acceptance observations

The implementation is not successful merely because the ownership classes look clean.

We want executable evidence that:

1. no placement commitment means no plank retrieval;
2. one placement commitment produces one member logistics chain;
3. several mutable excavation sites do not cause independent arbitrary carving;
4. completed physical consequence is observed before the next team decision;
5. natural traversable ground can dissolve immediate construction pressure;
6. sustained chosen continuation can accumulate into a long coherent works;
7. sibling plank works do not appear merely because nearby placements are physically possible;
8. a later branch is still possible when the chosen direction fails or the decision changes;
9. finite material can genuinely run out;
10. physical support failure remains real;
11. deterministic replay remains intact;
12. history instrumentation cannot kill the simulation.

## Explicit non-goals

Do not add during this iteration:

- Foreman entity;
- voting/consensus/negotiation;
- worker dialogue;
- LLM reasoning;
- bridge/stair/switchback project types;
- hard-coded no-branch rule;
- automatic plank-chain continuation;
- infrastructure immunity from excavation;
- global optimal route planning;
- speculative material staging;
- automatic orphan-material cleanup;
- generalized task-market architecture.

## Fresh-thread instruction

A fresh conversation should begin from this repository and say to continue the current manual iteration.

Read this handoff and README first. Inspect the preserved async candidate before editing it.

Begin with **Pass A only**.

Make ordinary implementation decisions without asking the human to choose them. Preserve successful asynchronous machinery. Validate against the Pass A probe and return executable evidence for inspection before broadening into Pass B.

The protected canonical `index.html` remains untouched until a later candidate is explicitly accepted for promotion.
