A practical synthesis of Leonardo da Vinci, Sébastien Le Prestre de Vauban, Helmuth von Moltke the Elder, George E. Mueller, and software designer David Parnas.

A useful coding plan connects the intended result to the mechanisms, dependencies, decisions and evidence needed to achieve it. It should make the work understandable, expose consequential uncertainty, and remain revisable as knowledge improves. The historical examples below inform the principles; the coding applications are a modern synthesis.

## 1. Define success as a coherent experience

**Leonardo:** His planning for *La Danae* connected an intended theatrical experience with named actors, measured positions, complementary views of the stage and mechanical arrangements. Artistic intention and practical means were considered together. :chatgpt-content-reference{index="0"}

**Coding:** Define observable success, scope and acceptance conditions. Describe what the user, API caller, operator or maintainer should be able to accomplish and understand, including relevant failure and recovery paths. Make concepts, names, behavior and feedback coherent. Identify constraints such as authorization, data integrity and compatibility, and prioritize anything whose failure would defeat the objective. Set a quality bar and stopping condition so clarity and craftsmanship guide the work without becoming endless polishing.

## 2. Make the mechanism open to inspection

**Leonardo:** His Sforza horse studies addressed casting orientation, mould construction and the sequence of furnace operations. Recognizing the groundwater constraint changed his proposed casting method before the decisive operation. :chatgpt-content-reference{index="1"}

**Coding:** Inspect the existing system and trace the affected behavior through code, callers, data, persistence, tests and the target environment. Separate observations, assumptions and proposals. Use the smallest useful representation—a worked example, state table, sketch, interface description or prototype—to expose relationships and unresolved questions. Explain each consequential change: “This achieves X through Y, provided Z holds.” Reuse suitable existing mechanisms and check assumptions that carry significant consequences. A convincing explanation establishes plausibility; evidence establishes whether its premises hold.

## 3. Simplify commitments and contain change

**Vauban and Parnas:** Vauban argued that a fragmented frontier dispersed forces and increased maintenance burdens. Parnas showed that software modules can isolate consequential design decisions, allowing those decisions to change without spreading changes throughout the system. :chatgpt-content-reference{index="2"}

**Coding:** Question whether each proposed feature, component and dependency is necessary. Choose a design that meets the objective with manageable complexity and continuing cost. Organize responsibilities around clear boundaries; keep consequential implementation choices private where other components do not need to know them. Add abstractions when they protect a credible responsibility or change. Distinguish the structure of the software from the order in which it will be built: processing steps alone do not determine good module boundaries.

## 4. Sequence by dependencies and useful learning

**Mueller:** His Apollo testing strategy sought earlier integrated tests of the intended vehicle configuration. His schedule also distinguished delivery from acceptance and made later flight decisions conditional on preceding results. :chatgpt-content-reference{index="3"}

**Coding:** Identify what limits progress and which uncertainties could invalidate substantial work. Obtain the smallest useful evidence before making costly commitments. Check actual readiness: can the worker access the persisted upload, can the service authenticate, and can the database support the expected workload? Build a small representative path through the real interfaces early, alongside focused component checks. Order subsequent work around prerequisites and what the results teach. Expand implementation as confidence in the shared assumptions grows.

## 5. Make shared decisions explicit and prepare alternatives

**Moltke:** His April 1866 memorandum considered alternative Austrian and Saxon actions and how access to a Bavarian railway could change the timing and force balance. His recommendations depended on stated conditions. :chatgpt-content-reference{index="4"}

**Coding:** Specify the shared behavior, data ownership, interfaces and failure semantics needed for dependent work to proceed. For an importer, decide whether partial imports are allowed and how retries avoid duplicate effects. For an assumption that could change correctness or architecture, identify the smallest useful check, the decision it resolves and the condition for switching approach. Detail the next executable steps while keeping unresolved choices conditional. When evidence changes a shared contract, revise it deliberately and update affected work. Preparing an alternative does not require implementing every fallback.

## 6. Delegate intent and own integration

**Moltke:** His operational instructions emphasized communicating the purpose clearly and giving subordinates room to act. They also emphasized cooperation among different forces; individual initiative required a shared understanding of the whole operation. :chatgpt-content-reference{index="5"}

**Coding:** Give each developer or agent an outcome, owned area, constraints, shared contract and completion evidence. Parallelize work whose boundaries permit independent progress. Assign an integration owner responsible for the combined behavior and shared invariants. Connect a small real path through the components early, and coordinate changes that affect other tasks. Increase coordination where actions interfere; allow local implementation choices within agreed boundaries. Completion of separate tasks must be checked against the behavior of the integrated result.

## 7. Challenge assumptions and revise from evidence

**Moltke and Parnas:** Moltke examined defects in the successful 1866 campaign and used the findings to revise operational instructions. Parnas explicitly identified an unnecessary restriction in his own interface example and explained how to remove it. Their records make correction part of the method. :chatgpt-content-reference{index="6"}

**Coding:** Give milestones observable completion conditions. Choose evidence capable of exposing the relevant defect: inspection, focused tests, representative measurements, or failure and retry cases where needed. Check affected existing behavior as well as the new path. Seek counterexamples and simpler alternatives when they could materially change the design. Use tests that assess meaningful behavior, and stop expanding verification once the relevant risks are sufficiently addressed. When evidence contradicts the plan, revise the affected assumptions, design and sequence; make any necessary change to agreed behavior or scope explicit.

## 8. Plan through delivery, recovery and continued operation

**Vauban:** His Canal du Midi recommendations addressed silting and water supply after the existing system developed serious maintenance problems. The planning problem extended beyond constructing an initial working waterway to keeping it usable. :chatgpt-content-reference{index="7"}

**Coding:** Finish at the agreed delivery state. Where relevant, plan downstream capacity, migration compatibility, diagnostics, deployment, maintenance and recovery. Distinguish stopping new work, handling partial execution and repairing completed effects: reverting code does not undo committed writes or external actions. Consider the continuing burden placed on users, operators and future maintainers. Report what was delivered, what was verified and what remains uncertain. The result should remain understandable and supportable after its first successful run.

**Working rule:** For each consequential change, connect **objective, mechanism, prerequisites, evidence and revision condition**. Include the intended experience and the conditions needed to sustain it. Scale planning detail to uncertainty, dependencies, reversibility and consequences: a small fix may need one paragraph and a focused check; a persistent workflow needs explicit failure, integration and recovery decisions.

**Improvement rule:** Keep the framework itself revisable. After an escaped defect, costly surprise, unnecessary delay or demonstrably better approach, identify which assumption or practice needs to change. Evaluate new methods and tools against representative tasks. Keep changes that improve correctness, clarity, delivery or the cost of correction; simplify or remove steps that produce no useful decisions.
