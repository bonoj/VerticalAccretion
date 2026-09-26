# VERTICAL ACCRETION — TEAM COMMITMENT & EMBODIED WORK SPEC

**Status:** Evidence-derived implementation specification for the current asynchronous-worker candidate.  
**Basis:** Code archaeology of `vertical_accretion_async_workers_candidate.html` plus observed seed-741 failures: branching plank works, excavation beneath existing works, speculative plank retrieval, and fatal history exhaustion.  
**Purpose:** Repair ownership and sequencing below collective route choice without prematurely implementing multi-agent deliberation, a foreman, architectural project ontology, or a world-owned job board.

---

## 1. Experimental target

The immediate target is a run in which a small deterministic team can continue downward through natural traversal, excavation, and finite placed members until physical circumstances or material exhaustion stop further progress.

A mature run should be capable of consuming all available construction stock **if continued construction remains the team's chosen and physically viable way forward**, or stopping earlier because the intended continuation can no longer be physically realized.

We specifically expect to be able to watch long accumulated works emerge without sibling plank branches under ordinary continuation.

This is **not** because branches are prohibited.

A branch may occur later if the team abandons or revises a previous direction because that direction is no longer viable or is no longer selected by the team. The current expedition does not need sophisticated deliberation about that revision.

> **No branching-by-rule. No branching-by-accident.**

---

## 2. Evidence that motivates this change

The current asynchronous candidate successfully removed global worker serialization, but exposed ownership errors that serialization had hidden.

### 2.1 Current opportunity derivation is centralized and omniscient

`vaDeriveWork()` scans every home-reachable node and publishes every surveyed, unreachable +X/±Z neighbor as a `remove` or `place` work item. A score orders these items.

This means physical possibility is being promoted directly into intentional work.

Consequences observed:

- several workers can pursue sibling mutations around the same general access boundary;
- multiple plank works can grow in parallel without a team decision to branch;
- empty workers preferentially claim excavation while member carriers preferentially claim placement;
- excavation may be selected near existing works merely because a neighboring edge is geometrically mutable;
- a newly placed member does not itself establish a persistent team commitment to continue from the resulting state.

### 2.2 Construction material is fetched speculatively

The current asynchronous selector counts unclaimed placement opportunities as `demand`. If demand exceeds current member logistics, an empty worker may begin `retrieve-member`.

Therefore lumber acquisition can begin before the team has decided to place a specific member anywhere.

This reverses the intended causal order.

### 2.3 Sequential execution already prevents a true placement race

Workers are advanced deterministically and sequentially inside the fixed-step ECS system. A physical mutation by an earlier worker occurs before a later worker reaches its own commit point in the same step.

The current substrate therefore does not require locks, promises, threads, or nondeterministic concurrency to make placement atomic.

The remaining issue is **what is revalidated**, not simultaneous mutation.

### 2.4 Physical consequence machinery is already useful

Existing machinery already provides:

- natural traversal through `vaNaturalOK`;
- home-connected reachability through active edges;
- physical member placement and support checks;
- terrain deformation;
- terrain/member support through `vaSupport`;
- topology refresh after mutation;
- member failure when geological support is lost;
- deterministic fixed-step execution;
- finite embodied construction stock;
- embodied workers and asynchronous activities.

Preserve these unless executable evidence requires change.

---

## 3. Ownership model

The implementation must preserve the following conceptual separation.

```text
PHYSICAL WORLD
geometry, material, support, occupancy, gravity, topology,
physical action predicates and deterministic consequences
        ↓
PERCEPTION / POSSIBLE INTERVENTIONS
what agents can currently observe or consider doing
        ↓
TEAM DECISION
persistent commitment to one specific intervention
        ↓
LOGISTICAL DECOMPOSITION
physical activities required to execute that commitment
        ↓
ASYNCHRONOUS EMBODIED EXECUTION
walk, retrieve, excavate, carry, place, handle consequences
        ↓
PHYSICAL WORLD CHANGES
```

These are ownership boundaries, not necessarily separate classes or systems.

### 3.1 The world does not decide work

The world must not own concepts such as:

- best edge;
- valid work;
- bridge project;
- excavation project;
- preferred continuation;
- route objective;
- team priority.

The world may answer physical questions such as:

- is this location occupied?
- can this body traverse this geometry?
- is this proposed member placement physically possible now?
- can material be removed here?
- what support exists?
- what happens if support is removed?
- what becomes reachable after the mutation?

Physical possibility is not intention.

### 3.2 Team commitment owns intervention choice

Before excavation or construction logistics begin, the team must have committed to a **specific intended physical intervention**.

Examples at the current abstraction level:

- remove material along this particular local segment;
- place this particular member between these physical endpoints.

The commitment means:

> **We are doing this.**

It does not mean:

> **The world says this is the best thing to do.**

### 3.3 A foreman is not required

The simulation requires a team decision, not a `Foreman` entity.

Future experiments may implement team decision through:

- a foreman;
- consensus;
- voting;
- proposal/acceptance;
- disagreement and negotiation;
- rotating authority;
- some other mechanism.

None of those belong in this implementation.

For this expedition, use the smallest deterministic surrogate necessary to produce **one persistent team commitment at a time** and exercise the physical/logistical machinery below it.

The surrogate must be explicitly provisional and replaceable.

---

## 4. The current expedition boundary

This pass is **not** an experiment in collective intelligence.

Do not attempt to solve:

- worker disagreement;
- communication;
- voting;
- leadership;
- negotiation;
- individual beliefs about route quality;
- semantic reasoning;
- LLM planning;
- architectural recognition;
- global optimal route planning.

The purpose of the provisional team-decision mechanism is to isolate those future questions from the already-interesting embodied execution problem.

---

## 5. Commitment lifecycle

At the current scale there should be at most one active **team intervention commitment**.

This is not a permanent invariant of Vertical Accretion. It is the controlled apparatus for this expedition.

A commitment has enough identity to survive asynchronous execution:

```text
kind          remove | place
physical target
source/current working location
creation tick
status
reason/provenance useful for diagnostics
```

Do not encode architectural nouns.

Suggested lifecycle:

```text
uncommitted
    ↓
team selects intervention
    ↓
committed
    ↓
required logistics execute asynchronously
    ↓
commit-time physical revalidation
    ↓
executed ───────────────┐
    or                  │
invalidated / abandoned │
                        ↓
              observe changed world
                        ↓
                next team decision
```

A completed placement does **not** automatically create another placement commitment.

A completed excavation does **not** automatically create another excavation commitment.

The team observes the new physical state and makes another decision.

---

## 6. Decision continuity and the expected non-branching result

The provisional team-decision surrogate should preserve continuity strongly enough that the experiment can investigate sustained descent.

Once the team has selected a location/direction to extend access, the next decision should be made from the newly changed local situation rather than by globally rescoring every mutable edge in all reachable space.

This is **decision continuity**, not a hard-coded construction continuation.

The implementation must not contain rules equivalent to:

```text
if plank exists:
    place another plank forward

if bridge started:
    finish bridge

branches forbidden

keep same heading
```

Instead, the surrogate should repeatedly reconsider the changed physical situation at the current working locus.

If natural traversal now continues, the team may move/explore on natural ground before another intervention is required.

If excavation is the selected next intervention, excavation occurs.

If placement is selected, a member is fetched and placed.

If the current line is no longer physically viable or no longer selected by the surrogate, the commitment may change and a different line may later emerge.

### Expected visual consequence

For the known control run, ordinary continuation should tend to produce a single accumulated plank works rather than sibling plank branches.

That visual result is **evidence of coherent commitment continuity**, not an acceptance rule that searches the scene graph for branches and suppresses them.

---

## 7. Logistics begin only after commitment

This is a hard invariant for this pass.

> **No construction material retrieval without a specific committed placement.**

The current relationship:

```text
possible placement count
    → construction demand
    → fetch plank
    → carrier later chooses placement
```

must disappear.

The intended relationship is:

```text
team commits to PLACE A→B
    → execution requires one embodied member
    → a worker retrieves one member
    → worker transports that member toward A
    → worker revalidates physical placement
    → place or fail
```

A retrieved member is associated with executing that commitment during the activity.

If the commitment becomes physically impossible while the worker is traveling, the worker must not force the placement.

Do not invent automatic cleanup merely to erase the resulting physical history. If an embodied member becomes orphaned by invalidation, preserve it unless existing physical rules naturally move it.

---

## 8. Excavation is also committed work

Excavation must follow the same ownership boundary.

Do not treat every geometrically removable boundary as a job.

Intended order:

```text
team commits to REMOVE at target
    → worker travels to working location
    → immediately before mutation, current physical state is rechecked
    → terrain mutation occurs if physically permitted
    → spoil/material consequence enters world
    → topology/support refresh
    → team observes changed state before choosing another intervention
```

The world is allowed to let workers make bad decisions.

If a committed excavation physically removes support beneath existing infrastructure, that infrastructure may fall.

Do **not** add a semantic rule such as `dontExcavateUnderBridge`.

The present goal is to prevent arbitrary excavation from occurring merely because a global work enumerator found a mutable edge—not to make destructive decisions physically impossible.

---

## 9. Commit-time revalidation

Every physical intervention must be revalidated immediately before mutation against the current physical world.

Sequential deterministic execution provides the serialization boundary.

### Placement revalidation

At minimum, use current—not stale—facts for:

- source/end geometry;
- member reach/length;
- geological/support feet;
- occupancy or conflicting already-placed member where relevant;
- whatever other physical placement predicates the existing substrate already requires.

Do not ask the world whether placement is strategically good.

Ask whether the intended placement can physically occur now.

### Excavation revalidation

Recheck that the intended physical removal can still be applied to the intended current geometry.

Do not protect infrastructure through semantic policy at this layer.

### Failure

If revalidation fails:

- do not mutate the world;
- record the physical failure diagnostically;
- end/invalidate the current commitment as appropriate;
- preserve embodied state;
- return to team decision.

No worker should silently retarget a different edge while carrying out an existing team commitment.

---

## 10. Asynchronous workers remain

The asynchronous activity work is preserved.

Workers do not need to share a timestep-level task or wait globally for one another.

During a committed intervention, workers may have different activities, including:

- traveling;
- retrieving the required member;
- excavating;
- dealing with physical material consequences where current mechanics require it;
- exploring/traversing reachable ground when not needed by the active commitment;
- idle/available;
- isolated.

The key distinction is:

> **Workers execute asynchronously. Intervention choice is coordinated.**

Do not reintroduce the original single-worker/global-job serialization merely to eliminate branches.

---

## 11. Exploration remains legitimate

Random/local walking and survey behavior before or between interventions is not itself a defect.

Workers may spread across reachable natural terrain and gather local spatial evidence.

Exploration does not authorize mutation.

A worker encountering a physically interesting boundary may contribute to future possible-intervention reasoning, but it does not independently begin excavation or fetch construction stock.

For this expedition, the provisional team-decision surrogate may use globally available information if necessary to keep the apparatus small, but that shortcut must remain visibly owned by the provisional decision layer rather than masquerading as physical world truth.

---

## 12. Replace `vaWork` semantics, not necessarily every data structure

Do not preserve the current meaning:

> `vaWork` = every mutable edge adjacent to reachable space.

A data structure named `vaWork` may survive if useful, but it must represent committed/executing work or another clearly owned concept.

Likewise, claims remain useful for atomic assignment of execution responsibilities.

Claims answer:

> Which worker is executing this committed activity?

They must not answer:

> Which world mutation should the team choose?

Avoid large renaming/refactoring unless it improves correctness or makes ownership materially clearer.

---

## 13. Provisional team-decision surrogate

The implementation needs a deliberately small deterministic decision mechanism so the simulation can run before genuine team deliberation exists.

Requirements:

1. It produces at most one active intervention commitment.
2. It operates only at decision boundaries, not every worker tick.
3. It considers the changed state after the previous intervention.
4. It does not fetch material or mutate terrain itself.
5. It can select either excavation or placement.
6. It does not encode architectural nouns.
7. It does not hard-code “no branches.”
8. It strongly preserves local continuation when that remains the selected way forward.
9. It can abandon/revise a line when the current continuation is no longer viable or no longer selected.
10. Its policy is isolated enough to replace later with actual team deliberation.

The exact deterministic heuristic is an implementation decision for this expedition.

However, the heuristic must not recreate the current failure by globally enumerating every mutable reachable edge and treating each as simultaneous work demand.

---

## 14. Material exhaustion and physical termination

The target run must be able to reach honest stopping conditions.

### Construction exhaustion

If the team commits to a placement but no construction stock remains, the commitment cannot execute.

Do not synthesize material.

The simulation should remain alive and diagnostically legible.

### Physical dead end

If the provisional decision layer cannot identify an intended continuation that its current policy selects and the physical operators can attempt, the current line may terminate.

Do not manufacture a placement merely to keep the run moving.

### Horizon

Existing bounded section/horizon behavior may remain where still meaningful.

### No success-by-depth requirement

A run that stops early for coherent physical reasons is evidence.

---

## 15. History is instrumentation, not a physical kill switch

Current `vaLog()` throws when history exceeds 3000 events.

That behavior must not terminate the physical simulation.

Replace fatal history exhaustion with bounded/nonfatal instrumentation, for example:

- ring-buffer recent history;
- archival counters/summaries;
- capped UI history while durable causal identifiers remain stable;
- another deterministic bounded representation.

The exact implementation is open.

Invariant:

> **Observational storage pressure must not stop world physics.**

Do not let this instrumentation repair distract from the commitment change.

---

## 16. Diagnostics required for this pass

Expose enough state to falsify the implementation.

At minimum inspect:

### Team
- active commitment kind;
- physical target;
- commitment status;
- commitment creation tick;
- reason for completion/invalidation;
- current provisional decision locus or equivalent.

### Workers
- activity;
- phase;
- cargo;
- assigned execution responsibility;
- navigation target;
- stranded state.

### Materials
- stock / carried / placed member counts;
- which member, if any, is assigned to active placement execution.

### Physical consequence
- current home-reachable region;
- active members;
- failed members;
- removals;
- support/topology revision.

Do not turn these diagnostics into conventional gameplay UI.

---

## 17. Implementation sequence

This should **not** be attempted as one giant rewrite.

### Pass A — Ownership seam

Goal: establish explicit team commitment and remove speculative work demand.

- introduce provisional team commitment state;
- stop treating all derived physical possibilities as active jobs;
- remove placement-count → plank-retrieval coupling;
- make excavation require commitment;
- make placement retrieval require commitment;
- preserve current async worker activity machinery;
- make history bound nonfatal if it prevents long observation.

**Probe:** With no active commitment, no worker excavates and no worker fetches a plank merely because a physical possibility exists.

### Pass B — Embodied execution

Goal: make committed interventions execute correctly.

- assign required worker activity from commitment;
- retrieve exactly the required embodied member for placement;
- travel asynchronously;
- commit-time physical revalidation;
- execute placement/removal;
- refresh topology/support;
- complete/invalidate commitment;
- preserve orphan physical material on failure.

**Probe:** Delay member retrieval substantially. Other workers remain alive/asynchronous; exactly one member is fetched for the active placement; the carrier does not retarget opportunistically.

### Pass C — Provisional decision continuity

Goal: repeatedly choose the next intervention from the changed local situation without implementing team intelligence.

- implement the smallest deterministic surrogate;
- preserve local decision continuity;
- allow natural traversal to resume where available;
- select excavation or placement as physically/heuristically appropriate;
- permit revision when continuation fails;
- keep policy isolated and replaceable.

**Probe:** Seed 741 can develop a long coherent descent without sibling plank branches arising from simultaneous global work enumeration.

### Pass D — Long-run observation and repair

Goal: let the apparatus falsify the spec.

Run long enough to observe:

- substantial stock consumption or honest earlier termination;
- repeated transitions among natural traversal, excavation, and placement;
- no fatal history exhaustion;
- no speculative lumber train;
- no accidental sibling plank works;
- support failure remains physically possible;
- deterministic replay remains intact.

Only after observation repair concrete failures.

---

## 18. Acceptance probes

The pass is not complete because code structure looks correct.

### A. No speculative plank retrieval

At a state with geometrically possible placement but no active placement commitment:

**Expected:** zero workers begin member retrieval.

### B. One committed placement, one logistics chain

Create/observe one placement commitment.

**Expected:** exactly one embodied member is acquired for that commitment; no second worker fetches another member for sibling geometry.

### C. Final physical question

Change the world after a placement commitment but before the carrier commits.

**Expected:** the carrier revalidates against current physical state. If the intended placement is no longer physically possible, no placement occurs.

### D. Excavation requires commitment

Expose several geometrically removable boundaries.

**Expected:** workers do not independently carve them merely because they exist. Only the committed excavation is executed.

### E. Async independence

Make the required member trip long.

**Expected:** the simulation continues; other workers can traverse/explore/perform unrelated legitimate activity; no global wait state returns.

### F. Consequence before next decision

Complete a placement or excavation.

**Expected:** topology/support refresh occurs before the next team intervention is selected.

### G. Natural continuation

After an intervention connects into traversable natural terrain:

**Expected:** the system can resume ordinary traversal/exploration rather than mechanically placing another member.

### H. Sustained works

Where natural traversal remains insufficient and the provisional team policy continues selecting the same developing line:

**Expected:** successive committed interventions accumulate into a coherent works.

### I. No accidental branching plank works

During ordinary sustained continuation:

**Expected:** no sibling plank works emerge merely because several nearby placements are physically possible.

This is an observational consequence, **not a branch prohibition**.

### J. Legitimate revision remains possible

Make the current line physically invalid or cause the provisional decision policy to select another continuation.

**Expected:** a later work may emerge elsewhere. The system contains no invariant forbidding branches historically.

### K. Material exhaustion

Allow construction to consume all available members where continued placement remains selected and viable.

**Expected:** no phantom material appears; simulation remains alive; inability to execute further placement is explicit.

### L. Physical failure remains real

Allow excavation or later world change to remove member support.

**Expected:** existing support/gravity machinery may deactivate/drop the member. No semantic “protect bridge” rule suppresses the consequence.

### M. Deterministic replay

Same seed, initial state, rules, and interventions under different tick batching.

**Expected:** equivalent exported physical/team state and history semantics.

### N. History bound

Run beyond the previous logging threshold.

**Expected:** simulation continues without `History bound reached` terminating physics.

---

## 19. Explicit non-goals

Do not add during this implementation:

- a Foreman entity;
- voting or consensus simulation;
- worker dialogue;
- LLM reasoning;
- semantic architectural recognition;
- bridge/stair/switchback project types;
- a hard-coded single-route rule;
- a hard-coded no-branch rule;
- automatic “continue plank chain” state;
- infrastructure immunity from excavation;
- global optimal planning;
- speculative material staging;
- automatic cleanup of orphan members;
- generalized task-market architecture.

---

## 20. Success condition

The implementation succeeds when executable evidence supports the following causal chain:

```text
team selects one physical intervention
    ↓
that commitment creates concrete logistical requirements
    ↓
workers execute those requirements asynchronously
    ↓
the intended action is physically revalidated at commit time
    ↓
the deterministic world accepts or rejects the action
    ↓
physical consequences change traversal/support/material state
    ↓
the team makes its next decision from the changed situation
```

Over a sustained run, this should be capable of producing a long, coherent accumulated descent—potentially consuming the finite member stock—without branching plank works appearing simply because several geometric placements were simultaneously possible.

If a branch eventually appears because an earlier direction became impossible or the decision mechanism selected another way forward, that is not a violation. It is exactly the distinction this specification is intended to preserve.

> **Coordination chooses the intervention. Logistics realizes it. Physics decides what happens.**