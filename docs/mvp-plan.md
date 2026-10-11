# ScopeCanvas MVP delivery plan

Baseline: [product brief](../README.md)  
Status basis: repository contains the brief only; no prior code, issues, or pull requests.

| ID | Deliverable | State | Dependency | Definition of done |
|---|---|---|---|---|
| SC-01 | Architecture and domain contract | In progress | Product brief | Version, change and approval invariants documented |
| SC-02 | Synthetic vertical-slice demo | In progress | SC-01 | Brief → approve → change → compare → approve runs locally |
| SC-03 | Durable project data and authorization | Ready | SC-01 | Server-side access checks and persisted projects |
| SC-04 | Expiring/revocable client review links | Ready | SC-03 | Expired/revoked links reject access and audit approval |
| SC-05 | Impact engine and tests | Ready | SC-03 | Deterministic diff, DAG propagation, cycle detection covered |
| SC-06 | Accessibility and failure states | Ready | SC-02 | Keyboard flow and loading/empty/error/success evidence |
| SC-07 | Demo, deploy and handoff | Ready | SC-02–06 | Repeatable walkthrough, screenshots, limits, setup notes |

## Milestones

1. **Definition:** finalize data contract and unknowns; no date commitment yet.
2. **Vertical slice:** synthetic local demo proving the full business conversation.
3. **Trust:** persistence, review-link access, audit trail, tests.
4. **Client demonstration:** deployed demo, walkthrough, limitations and recovery path.
5. **Handoff:** reproducible setup and maintenance notes.

## Risks

| Risk | Impact | Mitigation |
|---|---|---|
| “Zero cost” becomes a hidden vendor commitment | Medium | Keep service adapters and validate free-tier terms before real data |
| Estimated change cost appears authoritative | High | Label every cost/date as a user-entered assumption pending approval |
| Demo becomes generic PM software | High | Enforce the five-step scope-change workflow as the primary experience |
| Shared-link access is implemented client-side | High | Treat local demo links as non-production; require server-side adapter before client use |
