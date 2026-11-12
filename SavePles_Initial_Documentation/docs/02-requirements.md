# Requirements

All capabilities below are planned. P0 is the initial release; P1 follows the core workflow; P2 is a later enhancement.

| ID | Priority | Requirement | Acceptance criterion |
| --- | --- | --- | --- |
| FR-01 | P0 | Account registration and sign-in | Verified users can sign in and sign out; unauthenticated requests cannot read private projects. |
| FR-02 | P0 | Organization creation and invitations | An organizer can invite members; invitations expire and cannot be reused after acceptance. |
| FR-03 | P0 | Verified institutional roles | A student nomination cannot grant HoD, supervisor or institutional reviewer authority. |
| FR-04 | P0 | Structured research workspace | A researcher can save topic, questions, methodology, references and report sections privately. |
| FR-05 | P0 | Project collaboration | Only explicitly permitted members can read or edit a project; organization membership alone grants no private project access. |
| FR-06 | P0 | Versioned uploads | Each uploaded revision retains a unique identifier, checksum, uploader and timestamp. |
| FR-07 | P0 | Proposal submission | Submission freezes an exact revision for an assigned reviewer. |
| FR-08 | P0 | Review decisions | An authorized reviewer can approve, reject or request changes with a reason and audit record. |
| FR-09 | P0 | Clearance records | The project records required, pending, verified, expired or not-applicable clearances with evidence and scope. |
| FR-10 | P0 | Final report review | Final report review is separate from proposal and clearance decisions. |
| FR-11 | P0 | Controlled archive release | Publication requires an approved release version, author authorization, rights checks and permitted visibility. |
| FR-12 | P0 | Public discovery | Search returns public release metadata only and supports discipline, institution, author, year and keywords. |
| FR-13 | P0 | Withdrawal and reporting | Users can report content; authorized moderators can restrict a release with a recorded reason. |
| FR-14 | P1 | Dataset import | CSV and Excel uploads show parsing errors, data types, missing values and a preview before analysis. |
| FR-15 | P1 | Statistical analysis | Each run records input version, method, assumptions, parameters, software version and outputs. |
| FR-16 | P1 | Export | Authorized users can export a report, charts and analysis provenance without exposing restricted files. |
| FR-17 | P1 | Research assistance | Suggestions are distinguishable from researcher-authored content and require acceptance before changing the report. |
| FR-18 | P1 | Consultation guidance | Each suggested organization includes an official source, applicability notes and last verification date. |
| FR-19 | P1 | Project memory | Users can inspect, correct and delete remembered project methods and preferences. |
| FR-20 | P2 | Community feedback | Public comments can be reported and moderated without modifying the underlying report. |

## Quality requirements

- Enforce authorization on the server for every resource and operation.
- Support responsive layouts, keyboard navigation, labelled controls and readable contrast.
- Paginate archive results and avoid requiring full file downloads to view metadata.
- Preserve drafts through recoverable save failures; display upload and job progress.
- Treat retryable background jobs as idempotent.
- Redact personal data, credentials and research content from operational logs.
- Define and test backup, restore, withdrawal and account closure procedures before a pilot.
- Establish measurable latency, upload size, concurrency and recovery targets during implementation; no untested service-level promises are made here.

