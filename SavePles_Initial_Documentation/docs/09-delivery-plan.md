# Delivery plan

All milestones are planned. Dates and team assignments will be set after scope and availability are confirmed.

| Milestone | Deliverables | Exit criteria |
| --- | --- | --- |
| 0 — Foundation | Brief, requirements, permissions, workflow, architecture and emblem | Team reviews documentation and records unresolved decisions. |
| 1 — Private workspace | Accounts, organization invitations, verified roles, project access and versioned uploads | Cross-user and cross-organization access tests pass; upload quarantine works. |
| 2 — Review workflow | Immutable submissions, assigned reviews, clearance records and audit events | Self-approval is blocked; changes require resubmission; approval does not publish. |
| 3 — Archive | Release checks, public search, selected downloads and withdrawal | Private files are absent from search; withdrawal stops future public access. |
| 4 — Statistics | Dataset preview, cleaning history, descriptive analysis, charts and exports | Reference calculations match expected outputs and runs can be reproduced. |
| 5 — Assistance | Templates, scoped project memory and sourced consultation guidance | No unauthorized retrieval; suggestions remain reviewable; false approval claims are blocked. |
| 6 — Pilot readiness | Faculty walkthrough, accessibility review, operational controls and deployment | Restore exercise succeeds; owners accept pilot scope and remaining limitations. |

## Verification priorities

Use unit checks for permissions and lifecycle transitions, integration checks for file access and job retries, and end-to-end scenarios for researcher and reviewer tasks. Test rejection paths as well as successful submissions.

Core scenarios include revoked membership, guessed object identifiers, cross-organization access, expired download grants, reviewer conflicts, edited submissions, duplicate job delivery and withdrawal during an active download request.

## Risks and responses

| Risk | Response |
| --- | --- |
| Users assume approval guarantees validity | Separate review labels and display limitations. |
| Sensitive data reaches the public archive | Separate datasets from releases and require explicit release checks. |
| Unverified users claim institutional authority | Verify appointments independently and limit scope. |
| Analysis produces misleading conclusions | Record methods and assumptions; require qualified review. |
| Costs grow through uploads or assistant use | Establish quotas, budgets and usage controls before rollout. |
| Connectivity interrupts work | Keep interactions small and support recoverable uploads and saves. |
| Institutional adoption is slower than expected | Start with a consenting pilot group and validate requirements early. |

## Decisions to resolve

- Pilot institution, participating faculty and authorized review contacts.
- Project ownership, maintainer responsibilities and contributor attribution.
- Identity provider, analysis hosting, assistant provider and budget.
- Retention, hosting location, access terms and publication policy.
- File limits, performance targets and recovery objectives.
- Cultural and institutional review of the approved emblem before public launch.

## Next implementation task

Create the application skeleton and development environment, then implement accounts and the private project access model. Do not expose public uploads before authorization and quarantine controls are in place.

