# Helmuth-von-Moltke-the-Elder-Planning-for-Coding
The nineteenth-century Prussian military planner—not his nephew of the same name.

Moltke connected objectives to resources, timing and other people’s decisions. Applied to coding, his method calls for a plan that explains how changes achieve the required behavior, what they depend on, and when to revise them.

## 1. Concentrate on what decides success

**Moltke:** In 1866, he proposed concentrating against the principal opponent, Austria, while reserves covered secondary defenses.

**Coding:** Define observable success, scope and acceptance conditions. Identify constraints such as authorization, data integrity and compatibility. Prioritize the prerequisite or failure that could defeat the objective. This directs effort toward the conditions that determine success.

## 2. Explain how the plan can work

**Moltke:** His 2 April 1866 memorandum estimated concentration times from railway routes and available forces. Strength mattered when and where it became usable.

**Coding:** Trace the affected behavior through code, callers, data, tests and deployment. Separate observations from assumptions; reuse suitable existing mechanisms. Make each major change’s reasoning open to challenge: “This achieves X because Y, provided Z holds.” Check consequential assumptions before relying on them.

## 3. Sequence by dependencies and capacity

**Moltke:** He recognized that access to a Bavarian railway could shorten Austria’s concentration and change Prussia’s timing advantage.

**Coding:** Identify what currently limits progress and order work around its prerequisites. Check actual readiness in the target environment: can the worker read the persisted upload, and can the database sustain expected writes? Resolve blocking dependencies before expanding work that relies on them.

## 4. Match precision to what can be known

**Moltke:** He prepared initial concentration closely; later operations depended on enemy decisions and unfolding events.

**Coding:** Settle shared interfaces and failure semantics before dependent components diverge. For an importer, decide whether partial imports are allowed; prevent retries of the same import from duplicating database effects. Detail the next executable steps; keep uncertain implementation choices conditional. Stable contracts let separate components progress coherently.

## 5. Prepare consequential alternatives

**Moltke:** He considered alternative Austrian and Saxon responses and how they changed deployments and force balances.

**Coding:** For an assumption that could change correctness or architecture, specify the smallest useful check, the decision it resolves and the condition for switching approach. Investigate early when a wrong choice would be costly to reverse. Preparing alternatives this way limits wasted work without requiring every fallback to be built.

## 6. Delegate intent and own integration

**Moltke:** He gave commanders broad purposes and discretion in execution. Misunderstood intentions and poor coordination could still undermine the plan.

**Coding:** Give each developer or agent an outcome, owned area, constraints, shared contract and completion evidence. Parallelize separable work and assign an integration owner. Connect a small real path through the components early; coordinate changes that affect other tasks. This exposes incompatible assumptions while corrections are still cheap.

## 7. Revise decisions from observed results

**Moltke:** Changed circumstances required fresh decisions as operations unfolded.

**Coding:** Give milestones observable completion conditions. Choose evidence that could expose the relevant defect: inspection, focused tests, failure or retry cases, or representative measurements. Check affected existing behavior; invite counterexamples and simpler alternatives for consequential designs. Revise the affected assumptions, design and sequence while preserving agreed behavior and scope.

## 8. Plan through continued operation

**Moltke:** Effective railway concentration coexisted with receiving congestion and supply problems. This lesson corrects a limitation of his planning.

**Coding:** Finish at the agreed delivery state. Where relevant, plan downstream capacity, migration compatibility, diagnostics, rollout and recovery of accepted work. Distinguish stopping new work, handling partial execution and repairing data: reverting code does not undo committed writes or external effects. Report what was delivered, verified and remains uncertain. Initial success must be sustainable.

**Working rule:** For each consequential change, connect **objective, mechanism, prerequisite, evidence and revision condition**. Scale detail to uncertainty, dependencies and consequences: a small fix may need one paragraph and a focused check; a persistent workflow needs explicit failure and recovery decisions.
