# Vertical Accretion — Manual Iteration Handoff

## Purpose

This is a lightweight, replaceable handoff for the **current human-guided iteration** on Vertical Accretion.

It exists so a fresh conversation can resume ordinary inspection and polish directly from repository state without reconstructing the previous chat. It is working context, not canonical design truth, not an expedition contract, and not a permanent historical record. Replace or delete it whenever the active iteration changes.

Begin with this file, then follow its links as needed.

## Repository state

The accepted executable is:

- [`index.html`](./index.html) — accepted Vertical Accretion E1 head.

Durable context is:

- [`VERTICAL_ACCRETION_DESIGN.md`](./VERTICAL_ACCRETION_DESIGN.md) — design intent, invariants, inherited machinery, and research framing.
- [`EXPERIMENT_LOG.md`](./EXPERIMENT_LOG.md) — living protocol, verified evidence, implementation archaeology, observations, interpretations, boundaries, and open questions.
- [`VERTICAL_ACCRETION_REFERENCE.png`](./VERTICAL_ACCRETION_REFERENCE.png) — perceptual reference evidence, not target geometry.
- [`README.md`](./README.md) — repository authority, workflow, and worker-expedition handoff rules.

E1 has been accepted and promoted. Do not treat it as an unfinished worker candidate.

## Current mode: manual legibility iteration

We are **not beginning E2 yet**.

The immediate work is to inspect and lightly polish accepted E1, primarily for **legibility**. Preserve the simulation's causal rules and experimental findings unless concrete evidence requires otherwise.

Working principle:

> Make represented truths easier to perceive without materially changing the rules that produce them.

This is intentionally different from an autonomous worker expedition. We can make small changes together, inspect them, and iterate quickly.

## Things discovered during post-acceptance inspection

Several systems are more substantial than their current visual presentation suggests.

### Construction stock

- E1 begins with **28 finite physical member-bundle entities**.
- A bundle transitions through `stock → carried → placed`; the same entity becomes constructed member geometry.
- The entrance pile currently reads as a repetitive, boring lumber stack and can look effectively infinite.
- This is primarily a legibility problem. Do not add a new resource system merely to fix the presentation.

### Excavated spoil

- Terrain removal emits representative spoil through inherited Foundry granular bearings.
- Bearings have provenance linking them to removal events and source nodes.
- Free bearings participate in physical motion and gravity; individual pieces have been observed rolling from scaffolding into the void.
- Workers can claim reachable spoil, carry it upward, release it into an entrance stock area, and record it as delivered.
- During carrying, the bearing position is synchronized directly to the worker with a vertical offset.
- At the normal miniature viewing scale this carrying relationship is difficult or impossible to read visually.
- Decision/history text describing spoil hauling is therefore substantially true, but more legible than the embodied presentation.

### Structural failure

- Constructed members depend on geological feet.
- Loss of sufficient geological support deactivates the traversal edge and subjects the member to inherited gravity.
- Route collapse has been observed directly.
- A worker whose active path loses an edge can become `isolated after support loss`; E1 does not teleport the worker back to the network.
- Route failure can therefore strand workers. This is existing causal behavior, not a feature proposal.

### Access semantics

E1 already distinguishes graph connectivity, loaded traversal, repeated bidirectional loaded traversal, and later work that depends on established access. Preserve this distinction.

## Immediate polish interests

These are **interests, not a mandatory checklist**.

- Make carried spoil perceptually legible.
- Make returned spoil / its entrance destination easier to notice.
- Make finite construction stock read as discrete usable material rather than decorative scenery.
- Improve perception of failed/isolated states without turning the lab into conventional game UI.
- Explore modest terrain/rendering improvements. Prefer shader/material/lighting/surface presentation changes over changing the deterministic geological field.
- Preserve the distant miniature character and the fact that construction remains subordinate to geology.

Do not use polish as an excuse to introduce major new simulation capability.

## Seed inspection

The accepted E1 specimen uses **seed 741**.

E1 was deliberately verified for deterministic replay at seed 741: different tick batching produced equal exported state and history. The implementation has a seeded procedural geology/RNG path, but the current presentation does not expose ordinary seed selection.

A useful manual iteration is to expose seed selection or a similarly small inspection affordance while preserving 741 as the known regression specimen.

Desired use:

- replay 741 to ensure perceptual changes have not accidentally changed known simulation history;
- deliberately try unfamiliar seeds to inspect whether E1's local rules produce coherent but different histories;
- distinguish visual-only changes from changes that alter deterministic simulation state.

Do not assume every seed will produce a successful descent. Failure, stall, awkward infrastructure, material exhaustion, or other differences may be experimental evidence.

## Things deliberately deferred to future expeditions

Do **not** rush to implement these during manual polish merely because they are interesting:

- lift/elevator apparatus;
- conditions explicitly designed to force a lift;
- carts, baskets, chutes, cranes, or other prescribed logistics solutions;
- generalized cave navigation;
- sophisticated structural simulation;
- new global planning machinery;
- green-material perturbation.

In particular, vertical logistics should remain available as an **open worker expedition**. A future expedition can introduce a rigorous pressure and completion criteria without prescribing “build a lift.” The resulting mechanism—or failure to find one—is the interesting evidence.

## Current collaboration rhythm

For now:

**inspect accepted E1 → improve legibility → run it → notice behavior → inspect code when useful → record durable findings → dream the next expedition**

When a question becomes mature enough for autonomous work:

**state the pressure and invariants → define evidence and completion criteria → avoid prescribing the solution → dispatch a worker → inspect the returned candidate**

A worker expedition does not have to improve the executable to succeed. A failed mechanism or stalled world can advance the experiment if it produces useful evidence and documentation.

## Handoff instruction

In a fresh conversation, a sufficient opening is simply to provide the repository or this file and say to continue the current manual iteration.

Recover durable truth from the linked repository artifacts rather than asking the user to reconstruct the previous conversation. Inspect the accepted executable and current repository state before making implementation claims.

Keep this handoff cheap. When the active manual iteration materially changes, rewrite this file rather than accreting permanent history into it.
