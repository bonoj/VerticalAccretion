# VERTICAL ACCRETION / DESCENT LAB

**Model-ready design document for independent realization from Foundry**

> **Status:** Implementation contract for an exploratory laboratory expedition. The supplied raster is perceptual reference evidence; Foundry is the inherited executable apparatus. This document intentionally fixes some engineering constraints while preserving open research questions.

## 1. Expedition intent

Build a simulation in which a small population progressively makes inaccessible downward space operationally reachable by physically changing the world.

The interesting object is not the final mine, settlement, cave, or construction. It is the accumulated physical history of decisions that made continued descent possible.

The supplied raster is perceptual evidence for a plausible mature state: geology/materials/structural-engineering forward; enormous vertical scale; darkness; sparse warm working light; crude accumulated structural works; tiny actors where visible; terrain and construction interpenetrating; no fantasy architecture or decorative magical language. The simulation must earn anything resembling that image.

## 2. Research questions

### Primary question

> Can deterministic embodied agents autonomously convert inaccessible nearby space into persistently usable space by altering terrain and constructed geometry, while leaving behind enough physical and causal history that the resulting environment can be read afterward as the record of how exploration occurred?

### Secondary question

> Can that deterministic physical substrate expose sufficiently stable spatial semantics that a later model can reason about meaningful regions, relationships, opportunities, and constraints without becoming authoritative over physical consequence?

Neither question requires semantic-model intervention in the first successful expedition.

## 3. Simulation posture

Simulation first. There is initially no player-builder, hero, colony-management interface, quest structure, or authored progression path.

Agents act. Terrain changes. Material moves. Structures accumulate. Gravity matters. Yesterday's solution may become tomorrow's obstruction, shortcut, support, hazard, or reusable infrastructure.

Human intervention belongs initially in laboratory/debug affordances rather than the core world grammar.

Determinism is important: identical initial state, seed, rules, and interventions should produce identical physical history.

## 4. Foundry is the inherited apparatus

> **Do not improve or replace inherited Foundry systems merely because another implementation would be cleaner, more general, more realistic, or more elegant. Change inherited machinery only when observed behavior prevents the requirements of this expedition from being satisfied.**

Foundry already provides working machinery we want to exploit:

- deformable signed-density terrain and retained terrain mesh rebuilding;
- terrain-owned physical deformation;
- gravity and support consequences;
- physical granular matter represented by bearings;
- material moving and accumulating through deformable space;
- world-space entities and physical payload machinery;
- an existing ECS introduced because cross-cutting physical invariants earned it;
- camera/orbit/pan/pinch inspection behavior;
- device-responsive rendering and interaction;
- visible runtime/WebGL failure diagnostics and recovery;
- deterministic/procedural machinery and accumulated implementation archaeology.

Treat these as working inherited capabilities, not expedition objectives.

Astra may modify them where Vertical Accretion produces concrete evidence that modification is necessary. It should not spend the expedition replacing Foundry's terrain system with a "better terrain system," its bearings with a new particle framework, its camera with a new camera, or its ECS with a preferred architecture.

## 5. ECS requirement

> **The active simulation must use and extend Foundry's existing ECS rather than retreating into payload-specific monolithic actors.**

ECS is an extensibility mechanism, not an ontology generator. Do not predeclare a large component taxonomy because a mining or construction simulation might someday need it. Promote capabilities into components and systems when multiple entities genuinely require independently composable behavior.

Likely pressure may emerge around embodiment, gravity/support, locomotion, carrying, work intention, perception, structural participation, material identity, provenance, illumination, and semantic addressability. These are not a required component list.

The important invariant is that adding a new kind of worker, machine, material, structure, or later semantic intervention should not require rewriting the simulation around a new special-case actor class.

## 6. Traversal means safe bidirectional logistics

**Natural geometry is first-class traversal infrastructure.**

Agents should traverse suitable existing terrain directly. Construction and deformation are responses to insufficient access, not prerequisites for movement. Astra owns the concrete criteria for what is traversable.

Traversal is logistical, not merely topological. A region is not meaningfully opened merely because an agent can somehow reach it. Developing works should support sufficiently safe, repeatable movement of agents and relevant material both downward and back upward.

Existing slopes, ledges, tunnels, rock floors, and other suitable surfaces may be used directly. Problematic grade, exposure, discontinuity, carrying requirements, or severe verticality should create engineering pressure for physical solutions.

Switchback routes and moving lift apparatus are expected examples of solutions to verticality, not mandatory pre-authored construction classes. Astra may determine when they become appropriate and how they are physically realized.

A route may be wholly natural, wholly constructed, excavated, or—probably most interestingly—an accumulated hybrid of all three.

**Terminology note:** implementation/debug language may use the ordinary modern "traversable." In expeditionary prose, "traversible" is welcome where its older field-report flavor is useful. Do not encode a semantic distinction unless the simulation earns one.

## 7. Physical vocabulary before architectural vocabulary

Do not begin by implementing stairs, bridges, mines, shafts, scaffolds, buildings, elevators, or settlements as the simulation's fundamental ontology.

Begin with physically meaningful operations from which some of those readings might emerge. A provisional minimal vocabulary is:

- remove
- carry
- place
- support
- traverse
- illuminate

Even this vocabulary is provisional. A sequence of placed material that permits a height transition may eventually be recognized as stairs. A supported span across a void may be recognized as a bridge. A lift may emerge as a moving load-bearing transport apparatus. Those interpretations should not be necessary for the physical substrate to function.

> **The substrate should not need to know that it has an "Upper Works." It should know enough physical truth that another intelligence can discover one.**

## 8. Terrain deformation and construction are peers

Excavation is not merely a mining mechanic and construction is not merely a building mechanic. Both are ways of altering future spatial possibility.

Removing material may create access, headroom, a route, a fall, instability, spoil, drainage, or an obstruction somewhere downstream.

Placing material may create support, elevation, traversal, containment, blockage, storage, or a future working surface.

This shared framing is more important than deciding early whether Vertical Accretion is fundamentally a terrain, construction, colony, agent, archaeology, infrastructure, or spatial-reasoning simulation.

## 9. Agents

Start small. Agents should be deterministic, embodied, situated, and bounded rather than globally optimal construction planners.

They should possess only the knowledge required to act from their local situation. Their behavior should make commitments that persist long enough to generate consequences.

The first agents do not need personalities, dialogue, social simulation, professions, needs hierarchies, or sophisticated AI.

A bad-but-coherent locally reasonable solution may be more valuable than globally optimal path planning, because accumulated compromise is where infrastructure begins to acquire history.

## 10. The first expedition

Do not attempt "the vertical civilization." Construct the smallest apparatus capable of answering the first research question.

A useful starting condition may contain:

- a tiny population;
- one currently reachable working region;
- nearby space that can be perceived but cannot initially be used as a safe logistical route;
- gravity;
- deformable geological material;
- a limited amount of placeable/supporting material;
- darkness and local working illumination;
- enough vertical difference that ordinary locomotion cannot simply solve access.

Then allow the agents to attempt to establish persistent, bidirectional logistical access.

> **The expedition becomes interesting when something built or excavated to solve an earlier problem materially changes the solution space of a later problem.**

That is a stronger milestone than reaching arbitrary depth.

## 11. Material flow matters

Foundry's granular matter is especially valuable here. Excavation should not simply decrement terrain.

Removed material should have somewhere to go. Spoil can accumulate, fall, roll, clog routes, create ramps, bury useful surfaces, require hauling, become reusable fill, or make another operation harder.

This is one place where Foundry's existing physical machinery should be allowed to generate answers rather than replaced by abstract resource counters.

Eventually aggregation may become necessary for performance or legibility. That decision should be earned by the running simulation.

## 12. Structure and gravity

Leave open how sophisticated structural engineering becomes. The expedition needs enough physical truth that construction has consequences. It does not automatically require finite-element simulation, general rigid-body construction physics, or engineering-grade stress analysis.

Potentially useful truths include support, span, load, attachment, center of mass, falling material, obstruction, and loss of support.

A simpler deterministic structural model is preferable if it produces the causal phenomena the research needs.

**Failure is evidence.**

## 13. Infrastructure as memory

Persistent works should accumulate rather than continuously optimizing themselves away.

- An old route may remain even after a better route exists.
- A temporary platform may become structural.
- A spoil pile may determine where later workers can stand.
- An abandoned excavation may become drainage.
- A support installed for one operation may constrain another.
- A natural route may later make constructed infrastructure obsolete without erasing its history.

This is how the mature environment becomes archaeological rather than merely procedural.

We should eventually be able to inspect a mature slice and ask not merely "what is here?" but "why did it end up here?"

## 14. Semantic spatial hooks

Build semantic seams into the substrate early enough that adding model reasoning later does not require replacing physical state. Do not build a semantic world model instead of a physical world.

Useful handles may include stable entity identity, material provenance, support relationships, adjacency, reachability, containment, vertical ordering, working surfaces, connected regions, modification history, and coarse spatial partitions.

Horizontal slice granularity should remain an experimental variable. A later semantic observer might reason about individual objects, local neighborhoods, slices, connected regions, or larger accumulated works.

Semantic handles point to physical state; they do not replace it.

The semantic layer may propose intentions. It does not get to rewrite physical consequences.

> **Model authority ends where deterministic world consequence begins.**

## 15. Green material is a later perturbation

Do not start with the soft green metal visible in the raster.

Once an ordinary construction culture exists, introduce a materially distinct substance with genuinely different physical affordances and observe whether existing agents and infrastructure incorporate it.

The interesting question is not whether Astra can make green-metal buildings. It is whether a new material propagates through an already-developed physical culture.

## 16. Visual realization

The supplied raster is the principal perceptual reference. Preserve its reading, not its literal composition.

Important qualities:

- geological mass and extreme vertical depth;
- construction subordinate to geology;
- accumulated crude structural works;
- darkness functioning as spatial information;
- small pools of warm working light;
- sparse human/agent scale;
- long-distance evidence of continued descent;
- material and structural density increasing through history.

Avoid:

- fantasy ornamentation or glowing magical architecture;
- picturesque dwarven-city shorthand;
- heroic characters;
- decorative ruins;
- excessive steampunk machinery;
- arbitrary spectacle;
- pre-authored monumental architecture.

> **The visual target should communicate: people have been trying to get downward for a very long time. It should not communicate: someone designed a cool underground city.**

The raster depicts a plausible late-stage archaeological reading, not a target T0 and not a mandate that every run converge on the same visual history.

## 17. Inspection and diagnostics

Preserve Foundry's laboratory character.

We need to be able to inspect:

- physical world state;
- agent state;
- current work commitments;
- support and reachability;
- material movement;
- provenance/history where useful;
- deterministic seed/run identity;
- semantic handles when introduced.

Diagnostics should remain visible on failure. Debug views may be ugly. They are laboratory instrumentation, not presentation UI.

The beautiful raster language belongs to normal observation; explanatory overlays belong to inspection.

## 18. Astra's implementation authority

Astra should make ordinary implementation decisions without asking for steering.

Astra owns:

- agent realization and local planning;
- work scheduling and commitments;
- construction representation;
- structural approximation;
- terrain interaction integration;
- path/reachability implementation and the concrete definition of traversable;
- lighting implementation;
- simulation cadence;
- performance strategy;
- procedural visual realization;
- ECS extensions;
- debug instrumentation.

Surface a decision only when choosing one interpretation would materially close an important research question that this document deliberately leaves open.

Proceed through executable evidence: implement, run, inspect, diagnose, refine, and continue. Preserve successful inherited and newly built behavior. If an approach fails, repair or replace it rather than preserving it merely because it already exists.

## 19. Explicit non-goals for the first expedition

- Rebuilding Foundry's already-working terrain, physics, camera, diagnostics, granular material, or ECS without requirement-driven evidence.
- Producing the supplied raster as a static visual approximation.
- Building a complete colony simulation or civilization.
- Adding a player-builder loop.
- Adding personalities, dialogue, quests, lore, or fantasy ontology.
- Starting with the green material perturbation.
- Using a language model to decide physical outcomes.
- Pre-authoring a taxonomy of architectural nouns and forcing the world to instantiate it.
- Optimizing away old infrastructure merely because a better route now exists.

## 20. Success conditions

Success is not depth, resemblance to the raster, number of systems, or architectural sophistication.

> **A successful early Vertical Accretion run gives executable evidence of the following causal chain:**
>
> agents encounter insufficient access → alter the physical environment → establish sufficiently safe, repeatable bidirectional movement for agents and relevant material → use that access → the solution changes the constraints or affordances of subsequent work

Afterward, inspection of the physical state should recover meaningful evidence of how and why that history occurred.

A particularly valuable stopping point is the first time yesterday's solution becomes today's environmental constraint or affordance.

## 21. Handoff posture

Treat Foundry as the working ancestor, this document as the implementation contract, and the supplied raster as perceptual evidence.

**Build the world, not a plan for the world.**

Do not broaden the expedition merely because additional systems are imaginable. The first realization should be the smallest question-bearing apparatus that can generate evidence about autonomous descent, physical modification, bidirectional logistics, accumulated infrastructure, and causal history.

If the simulation discovers a form we did not name, prefer the evidence over the vocabulary in this document. If the implementation contradicts a fixed invariant above, repair the implementation or surface the conflict.
