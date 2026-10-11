# Architecture decision — zero-cost ScopeCanvas MVP

**Status:** proposed for implementation  
**Decision:** Build a static, dependency-free demonstration first; place persistence, authentication, and shareable reviews behind explicit adapters before enabling real client data.

## Why

The product’s differentiator is trustworthy scope change control, not a generic task board. The first vertical slice must make one full synthetic workflow credible without committing the project to an unverified platform or paid dependency.

## Deployment path

1. **Current demo:** plain HTML/CSS/JavaScript. It runs from any static host (including GitHub Pages) and stores synthetic work locally in the browser.
2. **Production MVP adapter:** Next.js + TypeScript user interface, PostgreSQL-backed persistence, and server-side authorization. Use only a verified free tier or self-hosted deployment; do not connect client data until the provider, limits, backup policy, and access model are accepted.
3. **No vendor lock-in:** repository interfaces own the data model; database, mail, and URL-signing implementations remain adapters.

## Core model

- Project
- Brief
- Deliverable
- Milestone
- ScopeVersion
- ChangeRequest
- Approval
- ReviewLink

An approved `ScopeVersion` is append-only. A new change always creates a candidate version; no approved record is edited.

## Deterministic impact engine

- Each deliverable has a stable immutable ID.
- Version comparison is a set diff by ID: added, removed, and modified.
- Modified fields are compared after canonicalizing whitespace and ordering criteria.
- Milestones form a directed acyclic graph. Impact is propagated through dependent milestones using breadth-first traversal; creation rejects cycles.
- Price and schedule are explicit entered assumptions. The system sums visible line items; it never fabricates a quote or date.
- Snapshot integrity uses a SHA-256 hash of canonical scope JSON when server persistence is enabled.

## Security and quality gates

- Server-side authorization for every project and review operation.
- Signed, expiring and revocable review links; store only hashes of tokens.
- Synthetic fixtures only in source control.
- Keyboard-operable primary path, visible focus, high contrast, and meaningful loading/empty/error/success states.
- Tests: version-diff unit tests, DAG/cycle tests, access-link integration tests, and an end-to-end approval flow.

## Explicit non-goals

Contracts, tax advice, automatic pricing guarantees, and full project-management features remain outside this MVP.
