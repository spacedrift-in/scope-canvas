# ScopeCanvas

Requirements change without a visible effect on deliverables, milestones, and acceptance criteria.

**Status:** Product brief. No working application or performance claims yet.
Built as a Spacedrift portfolio demonstration for **agencies, studios, and teams buying software projects**.

## Client demonstration

Capture a brief → define deliverables → attach acceptance criteria → propose a change → compare versions → approve scope.

Start with a synthetic client brief, approve a scope, propose an extra feature, and show precisely what changed before a second approval.

Use synthetic data, identify the demonstration as a demo, and show failure recovery
alongside the happy path. The objective is a credible discovery conversation with a client.

## MVP scope

- Structured project brief and deliverable editor
- Milestones with dependencies and acceptance criteria
- Immutable approved scope snapshots
- Change requests showing schedule and price assumptions
- Client review links with expiry and revocation

**Outside the first release:** Binding contract generation, tax advice, automatic pricing guarantees, and a general-purpose project management suite.

## Proposed architecture

Next.js, TypeScript, PostgreSQL; accessible server-rendered interface.

Core entities: Project, Brief, Deliverable, Milestone, ScopeVersion, ChangeRequest, Approval.

This stack is a starting recommendation, not an implemented system. The assigned developer
should document alternatives and finalize the architecture before adding dependencies.
Keep authorization server-side, validate inputs, and separate external integrations behind adapters.
Add AI only where its benefit can be measured; review uncertain outputs rather than hiding them.

## Delivery milestones

| Milestone | Required evidence |
| :--- | :--- |
| 1 · Definition | User flow, data model, API or storage contract, and agreed acceptance criteria |
| 2 · Vertical slice | One complete workflow on synthetic fixtures, with setup instructions |
| 3 · Reliability | Relevant failure recovery, access checks, and meaningful automated tests |
| 4 · Demonstration | Repeatable demo, screenshots, short walkthrough, and documented limitations |
| 5 · Handoff | Reproducible setup, deployment or build instructions, and maintenance notes |

The owner estimates effort after milestone 1. Do not promise a date before platform and integration risks are assessed.

## Acceptance criteria

- [ ] Approved versions cannot be edited in place.
- [ ] A change request identifies added, removed, and modified deliverables.
- [ ] Expired or revoked review links reject access.
- [ ] Primary workflows are usable by keyboard with visible focus.
- [ ] Quoted amounts and dates remain explicit assumptions until approved.
- [ ] A new developer can follow the documented setup on a clean environment.
- [ ] Secrets and private client information are absent from code, fixtures, logs, and screenshots.
- [ ] Loading, empty, error, and success states are implemented.
- [ ] Primary screens use black and white, readable contrast, and consistent spacing.
- [ ] The demo includes limitations and measured results rather than unsupported claims.

## Developer handoff

1. Assign a primary owner and a separate reviewer.
2. Open a planning issue linking this brief; resolve unknowns before implementation.
3. Record the architecture decision and create the smallest runnable vertical slice.
4. Replace the placeholder structure with the chosen platform structure.
5. Add actual setup commands only after verifying them; record required versions.
6. Deliver through focused pull requests with validation evidence.

No install, build, or deployment commands are provided yet because application code has not been implemented.
Android releases require an Android toolchain; iOS builds require macOS, Xcode, and appropriate signing.

## Quality and originality

Implement the product from this brief. Track third-party libraries and their licenses.
Attribute reused material and do not copy competitors’ interfaces, proprietary code, or private datasets.
Names are working titles; trademark and package availability have not been cleared.
Keep client names and case-study claims out of the demo unless authorized.

## Repository guide

- `docs/decisions/`: architecture decisions once made.
- `docs/demo.md`: repeatable client demonstration and limitations.
- `tests/fixtures/`: synthetic test inputs only.
- Platform application structure: to be created by the assigned developer.

## Contact and usage

[Spacedrift](https://spacedrift.in) · [Project enquiries](mailto:spacedrift.contact@gmail.com)

Copyright © 2026 Spacedrift. No open-source license is granted in this scaffold.
Select explicit license terms before inviting public code reuse.
