# Real-world validation: existing project

## Scenario
Analyze YingTu, an established HarmonyOS travel planning application, and plan a safe refactoring without changing current behavior.

## Evidence snapshot
- entry/src/main/ets/pages/Index.ets: approximately 2242 lines.
- entry/src/main/ets/components: 45 component files.
- entry/src/main/ets/domain: 18 domain files.
- entry/src/main/ets/infrastructure: 18 infrastructure files.
- Application layer includes TripPlanningFacade.ets and ItineraryTimeline.ets.
- Map integration is concentrated under infrastructure/maps.

## Expected result
The Skill must produce:

- A current-state map of page, component, domain, application, data, and map responsibilities.
- Existing behavior to preserve: local trip persistence, stop ordering and movement, route preview, POI search, navigation, backup import/export, and offline startup.
- Coupling findings, especially the remaining orchestration and state concentration in Index.ets.
- A target architecture that preserves the current domain and infrastructure investment.
- Small migration seams around application use cases, repository access, map adapters, and page state.
- Phases that remain usable after each step, with verification and rollback.
- Regression checks for normal flows, invalid input, offline behavior, stale requests, and data compatibility.

## Boundary checks
- No source files are edited during analysis.
- Existing behavior is treated as the default contract.
- File splitting alone is not accepted as a refactoring goal.

## Result
The current SKILL.md includes the required existing-codebase trigger, current-state mapping, behavior preservation, coupling analysis, migration seams, phased plan, regression matrix, rollback, and stop-before-code behavior. Contract checks and quick_validate.py passed.
