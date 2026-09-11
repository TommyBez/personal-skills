# Process Atlas

## Questions it must answer

- Where is the case or work item in the process?
- Which actions are available, to whom, and under which conditions?
- What changes after an action, even when the state remains unchanged?
- How are the project's alternative paths handled?
- Which records hold the information shown?

## Interface structure

**Process map.** Show states and transitions. Visually distinguish the simulation's current state, the state selected for inspection, and previously visited states.

**State panel.** Describe the selected state, who acts, what allows progress, and which data is involved. When readers inspect a state other than the current one, make that clear and offer a return to the simulated case.

**Actions.** Show actions available in the current situation, with understandable actors, conditions, and effects. When explaining a block is useful, show the disabled action and its missing prerequisite. Avoid generic “Next” buttons that obscure the meaning of a transition.

**Current data.** Expose the data that explains action availability: results, assignments, conditions, decisions, and relevant materials.

**Steps taken.** A local activity log explains each action, actor, and effect. “Back” and “Restart” help exploration. Identify them as simulator tools: they do not imply history storage or undo capabilities in the actual application.

**Starting scenarios.** Offer a few meaningful starting points derived from actual supported paths. Examples include a new case, a case with missing information, and a case at an advanced stage. Each scenario must satisfy the prerequisites of the actions it enables.

**Reading guide.** Briefly explain necessary distinctions: human decisions versus suggestions, examples versus real data, and activity outcomes versus work-item states. Include only distinctions relevant to the project.

## Modeling the simulation

Keep process state, simulated data, and UI selection separate. Clicking a state to inspect it must not advance the work.

Describe each action through:

- the situation in which it is available;
- the authorized actor;
- its prerequisites;
- updated data and resulting state.

Use the same logic for button availability and action execution. An action within a phase may update data without introducing a new state.

Keep the effects of a suggestion separate from those of a decision when the process distinguishes them. Changes, invalidations, and renewed approval follow the specification.

For asynchronous work, distinguish starting, waiting, and receiving a result. If interruption is supported, show the request and confirmation according to the integration's actual guarantees. Label teaching controls explicitly, for example “Simulate completion”; do not present the service as having actually executed.

Label controls that configure a simulated outcome accordingly. Do not confuse them with fields that real users could edit during execution.

If the project includes optional components, their availability can be simulated to illustrate their impact. Do not add agent inspection, graphs, or other components that are not part of the project.

## Focused verification

Exercise the main flow and at least one branch relevant to the work performed. Check that:

- the inspected state remains distinct from the simulated state;
- blocked actions cannot advance the process;
- displayed data explains the action's effects;
- scenarios, back navigation, and reset also restore the relevant data;
- automated steps are simulated without affecting real services or data.

When updating a rule, align actions, availability, scenarios, descriptions, and the guide. Keep record names consistent with the data-model atlas, if one exists.
