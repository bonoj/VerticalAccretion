# Vertical Accretion — Experiment Log

## Purpose and status

This is the living laboratory notebook for Vertical Accretion.

The design contract records what the experiment intends to investigate. This file records what was actually done, observed, implemented, verified, and currently inferred from executable evidence. It is deliberately malleable. Findings may be revised when later execution contradicts them.

This is **not** a specification, roadmap, release note, benchmark, or argument for a predetermined conclusion. Mundane results, failures, ambiguities, and negative findings belong here alongside successful ones.

The accepted executable remains `index.html`. The current design intent remains `VERTICAL_ACCRETION_DESIGN.md`.

## Evidence vocabulary

Notebook claims should make their epistemic status visible when the distinction matters.

- **OBSERVED** — directly seen during execution or inspection of the running artifact.
- **IMPLEMENTED** — established by inspection of executable code or state.
- **VERIFIED** — deliberately tested against an explicit condition.
- **INTERPRETATION** — the current reading of observations or implementation evidence; revisable.
- **OPEN** — an unanswered experimental question.

A claim can move between these categories as evidence improves. The raw record is preferable to a stronger label.

## Experimental protocol

The first expedition used the following rough turn structure:

1. Human/model exploration identified a research question without fixing an application genre or desired architecture.
2. Existing machinery was inspected for a suitable physical ancestor. Foundry was selected rather than rebuilding terrain deformation, granular matter, gravity, camera behavior, diagnostics, and other already-earned mechanisms.
3. Durable intent was moved into the repository: design contract, perceptual reference, executable ancestor, authority boundaries, workflow, and finish line.
4. A worker model was dispatched with a lightweight repository-oriented instruction rather than a large conversational handoff.
5. The worker model made ordinary implementation decisions and iterated through implementation, execution, inspection, diagnosis, and refinement.
6. The worker returned a complete candidate and expedition report rather than promoting its own work to accepted state.
7. Human inspection determined whether the candidate had reached the expedition finish line.
8. After acceptance, external transport promoted the exact candidate to canonical `index.html`.
9. Published text was compared with the accepted candidate to verify transport fidelity.
10. Observation continued against the accepted executable. Acceptance did not end experimentation.

The authority boundary used in E1 was:

- the **repository** carries accepted executable state and durable experimental context;
- the **worker** owns ordinary implementation decisions during its expedition;
- the **human** owns acceptance of a candidate into canonical state;
- **transport** moves accepted state but does not determine artifact semantics.

This structure is itself under observation. It should not be treated as a universal development methodology merely because E1 used it successfully.

## Timeline — E1

This timeline records useful procedural anchors rather than attempting exhaustive telemetry.

- The initial concept asked what kind of world develops when downward exploration requires a population to construct and deform the conditions of its own future exploration.
- Foundry was chosen as the inherited physical apparatus rather than beginning from an empty implementation.
- `VERTICAL_ACCRETION_REFERENCE.png` was established as perceptual evidence for how a mature run might read, explicitly not as geometry or a target scene to reproduce.
- `VERTICAL_ACCRETION_DESIGN.md` externalized the research questions, inherited machinery, invariants, non-goals, implementation authority, and E1 success condition.
- Foundry was extracted as a sovereign ancestor and VerticalAccretion was established as its own repository with the accepted Foundry executable as `index.html`.
- `README.md` became the lightweight entry and handoff protocol for an unfamiliar human or model.
- **26 min 29 sec:** the repository had reached the state from which the worker could be dispatched using only a short repository-oriented instruction. This is a known human-workflow anchor, not a performance benchmark.
- Astra Medium was dispatched to realize E1 from repository state. Autonomous model runtime continued without equivalent continuous human supervision.
- The worker returned a complete offline E1 candidate and report after implementation, execution, diagnosis, refinement, and verification.
- Human inspection accepted the candidate as having reached the E1 finish line. No additional worker turn was requested.
- The accepted candidate was promoted to canonical `index.html` through the external FUUTP transport path.
- Candidate and resulting Git blob were compared as complete decoded UTF-8 text: **2,969,176 characters on each side, exact equality**.
- Post-acceptance execution and code inspection immediately began producing additional observations recorded below.

The useful time quantity here is **human attention**, not autonomous model runtime. Roughly an hour of human attention covered conception, repository preparation, dispatch, inspection, acceptance, and promotion. This is protocol context only; E1 is not a controlled productivity comparison.

## E1 apparatus actually realized

E1 is a bounded open geological surface section with three deterministic embodied workers. Its active mechanisms include:

- local surveying and persistent sampled spatial nodes;
- a reachability graph whose edges can be natural ground or constructed access;
- loaded-grade constraints distinct from mere geometric connectivity;
- local work selection between terrain removal and supported placement;
- deformable inherited geology;
- physical representative spoil using Foundry's granular bearing machinery;
- finite construction stock represented by physical material entities;
- stock → carried → placed material state;
- supported constructed members with geological feet;
- persistent provenance and parent-access history;
- bidirectional and loaded traversal counts;
- support loss that closes traversal and subjects failed members to inherited gravity;
- workers that can become stranded after route loss;
- deterministic fixed-step execution and seeded replay;
- inspectable/exportable state, history, semantic slices, routes, support information, cargo, and provenance.

The apparatus deliberately does not claim enclosed cave navigation, engineering-grade structural analysis, calibrated mass conservation, or general-purpose locomotion.

## Verified E1 evidence

**VERIFIED — causal access milestone.** At tick 11,408 / 380.27 simulated seconds in seed 741, a constructed member had recorded at least three loaded downward crossings and two loaded upward crossings. Subsequent supported placement depended on that earlier access. E1 therefore demonstrated more than graph connectivity: established access was repeatedly used for loaded logistics and then supported later physical work.

**VERIFIED — accumulated physical history.** At tick 14,400 the run contained eight persistent members, twelve terrain removals, seventeen representative spoil bearings, twelve returned spoil bearings, and twenty unplaced construction bundles. Natural-ground travel preceded alteration, and later work retained provenance to earlier access.

**VERIFIED — deterministic replay.** Two reset runs advanced with different tick batching produced equal exported state and history.

**VERIFIED — terrain/support agreement.** A 40-position audit reported maximum mesh/support disagreement of approximately 0.000002619 world units.

**VERIFIED — finite stock accounting.** Stock cardinality was conserved through the tested run, and active members satisfied the configured length and geological-foot checks.

**VERIFIED — support consequence.** Recorded removal of a geological foot disabled the associated route and caused its member to fall.

**VERIFIED — interaction checks.** Chromium execution reported no uncaught page errors during the worker's verification. Desktop camera persistence, a 390×844 control-bound check, and emulated two-finger pinch/persistence passed. This is browser/emulation evidence, not a physical Android-device test.

## Continuing observations and implementation archaeology

### Physical spoil and hauling

**OBSERVED.** Individual pieces of excavated material were seen rolling from constructed works into the void below.

**QUESTION.** Visual inspection initially made it unclear whether these were actual Foundry granular bodies and whether the decision text describing returned material corresponded to embodied transport.

**IMPLEMENTED.** Worker terrain removal mutates the signed-density field and emits a finite representative yield through Foundry's `spawnBallRaw(...)` bearing mechanism. Each emitted bearing receives provenance linking it to its removal event and source node.

**IMPLEMENTED.** Reachable spoil can be claimed by a worker. The worker enters `collect spoil`, transitions the bearing into carried state, follows the reachable network toward the entrance, releases it into an entrance stock area, marks its provenance as delivered, and increments returned-spoil history.

**IMPLEMENTED.** While a bearing is carried, its position is synchronized directly to the worker position with a vertical offset. It therefore ceases to behave as freely rolling matter during the carried interval.

**OBSERVED.** At ordinary miniature viewing scale, the bearing-worker relationship is not perceptually legible. A viewer can reasonably conclude that the worker is not carrying anything even when the simulation records a carried bearing.

**INTERPRETATION.** E1's material-logistics truth is richer than its current perceptual representation. The missing piece is not necessarily a resource system; it is legible physical manipulation.

**OPEN.** What is the smallest representation that makes existing manipulation perceptible without prematurely prescribing baskets, carts, chutes, cranes, or another architectural vocabulary?

### Construction stock

**OBSERVED.** Entrance construction material initially reads as a repetitive static lumber stack and can appear effectively inexhaustible.

**IMPLEMENTED.** The entrance begins with 28 finite physical member-bundle entities. A placement consumes one actual entity by transitioning it from `stock` to `carried` to `placed`. The same entity becomes the constructed member geometry.

**INTERPRETATION.** Resource finitude and material identity are causally real but visually understated. The current pile communicates quantity poorly and has little interesting physical behavior of its own.

**OPEN.** Does construction stock need richer physical storage/handling to become experimentally consequential, or is the current abstraction sufficient until a run demonstrates otherwise?

### Route collapse and stranded workers

**OBSERVED.** A constructed member was seen falling after loss of geological support.

**OBSERVED.** Inspection of the resulting network showed that route failure can leave workers separated from valid access.

**IMPLEMENTED.** A member whose geological foot is sufficiently removed becomes inactive. Its traversal edge closes and the member becomes subject to inherited gravity.

**IMPLEMENTED.** If a worker's active path loses an edge, the path is invalidated and the worker can enter `isolated after support loss`. E1 provides no teleport or automatic return-to-network repair.

**INTERPRETATION.** Infrastructure is not merely accumulated scenery or a record of successful progress. Later activity can depend on it, and failure can turn earlier construction into a persistent constraint or trap.

**OPEN.** Which stranded states are recoverable through the existing physical vocabulary, and which expose missing capabilities?

### Access semantics

**IMPLEMENTED.** E1 distinguishes at least three materially different notions that could otherwise be collapsed into “reachable”:

1. graph-connected access;
2. access traversed while carrying material;
3. access repeatedly demonstrated in both directions under load and subsequently relied upon by later work.

**INTERPRETATION.** This distinction may provide a useful semantic handle for later reasoning systems because it records evidence of logistical use rather than inferring capability from topology alone.

**OPEN.** Which access distinctions remain useful across different geology, populations, and later perturbations, and which are artifacts of E1's bounded apparatus?

## Findings produced by execution rather than prior design

**IMPLEMENTED / VERIFIED.** Restricting member support to the member's actual physical footprint changed where spoil fell and delayed the causal milestone compared with an earlier implementation.

**INTERPRETATION.** A small correction to physical truth altered material flow and therefore later history. Preserving the correction rather than the faster demonstration is consistent with the experiment's separation of semantic intention from deterministic consequence.

**OBSERVED.** The constructed route developed turns, landings, long supported spans, and switchback-like geometry without a preauthored `SwitchbackSystem`.

**INTERPRETATION.** At least in seed 741, local loaded-grade, reach, support, terrain, and material constraints were sufficient to produce recognizable infrastructure form. This does not yet establish robustness across geology or seeds.

**OBSERVED.** Physical spoil can leave the intended working surface under gravity.

**INTERPRETATION.** Material generated by work can acquire a spatial history not chosen by the workers. Lost or displaced spoil may become relevant to later access rather than functioning only as a bookkeeping output.

## Known E1 boundaries

These are experimental boundaries, not defects that must automatically be repaired.

- The geology is an open surface section represented by one highest surface per X/Z location; there are no enclosed stacked cave floors.
- Worker foot locomotion is kinematic over verified surfaces.
- Structural support uses simplified endpoint-foot and length checks rather than stress, buckling, or finite-element analysis.
- Construction bundles abstract walking surface and bracing; their units do not model cut lengths or material mass.
- Excavation emits finite representative bearings rather than a calibrated mass-conserving continuum.
- One shared local commitment avoids competing work races.
- Carried spoil is position-synchronized to the worker rather than manipulated through articulated body/tool physics.
- The current visual language does not make every causally represented state equally legible.
- E1 does not contain the later green-material perturbation.

## Open questions

These are questions for execution, not a commitment to implement features merely because they are listed.

- What happens to spoil that escapes the accessible network?
- Can accumulated spoil materially change later route selection?
- How often does spoil clearance become necessary under different physical histories?
- What happens as the finite member stock approaches exhaustion?
- Does the existing local heuristic produce qualitatively different infrastructure under different deterministic geology?
- Which recognizable infrastructure forms recur without being named in advance?
- Can infrastructure failure produce recoverable situations using only already-earned physical actions?
- When does recovery require a genuinely new capability?
- What minimal physical manipulation vocabulary makes carrying perceptually legible?
- Should construction stock itself participate more fully in gravity, storage, obstruction, loss, and recovery?
- When does a collection of local access decisions begin to exhibit stable infrastructure patterns rather than one-off geometry?
- Which existing semantic handles are sufficient for later model reasoning?
- What additional semantic information would a model genuinely need rather than merely find convenient?
- How much can semantic intention perturb worker priorities while deterministic physical consequence remains sovereign?
- Which E1 abstractions become obstacles when exploration leaves the open surface section?
- How much of E1's behavior survives changes in population size, geology, available material, and initial conditions?
- Can the apparatus distinguish useful infrastructure from merely surviving infrastructure without introducing a global planner?

## Notebook entries

### E1 acceptance and first post-acceptance inspection

The E1 candidate was accepted after its reported success conditions and verification evidence were inspected. Canonical promotion was intentionally a separate act from autonomous implementation.

After promotion, ordinary visual exploration exposed two behaviors that had not been prominent in the acceptance discussion: granular spoil visibly rolling away under gravity, and supported route collapse capable of isolating workers. Code inspection then showed that spoil hauling, finite construction stock, provenance, support-dependent topology, and stranded-worker state were already present but not all equally visible.

This is useful evidence for the notebook protocol itself: **post-acceptance observation can reveal existing experimental surface that neither the handoff summary nor first visual inspection made salient.** A completed expedition can therefore remain an active object of study without immediately becoming a new implementation task.

---

When later evidence changes an interpretation, preserve enough chronology to show what changed and why. Do not rewrite uncertainty into inevitability.
