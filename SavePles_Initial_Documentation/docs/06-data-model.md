# Initial data model

This is a conceptual model, not a deployed schema.

| Entity | Main fields and relationships |
| --- | --- |
| User | id, identity subject, display name, account status |
| Organization | id, name, type, parent organization, verification status |
| OrganizationMembership | user, organization, role, status, appointment evidence reference |
| Project | id, owner, organization, title, discipline, lifecycle state, access policy |
| ProjectMembership | user, project, resource permissions, membership status |
| ResearchRevision | project, revision number, structured content, creator, timestamp |
| FileVersion | project, logical file id, object key, checksum, media type, size, quarantine status |
| DatasetVersion | file version, schema, de-identification declaration, access classification |
| Submission | project, type, research revision, submitted-by, timestamp, state |
| SubmissionArtifact | submission, exact file or dataset version |
| ReviewAssignment | submission, reviewer, verified scope, conflict declaration |
| ReviewDecision | assignment, decision, reasons, timestamp |
| Clearance | project, authority, requirement, status, evidence reference, scope, validity dates |
| AnalysisRun | dataset version, method, parameters, cleaning steps, library version, status, outputs |
| ProjectMemory | project, approved method or preference, source, consent and deletion status |
| ArchiveRelease | project, approved submission, public identifier, visibility, rights, release status |
| ReleaseArtifact | release, selected file version, permitted access |
| ConsultationSource | organization, official URL, applicability, verification date |
| AuditEvent | actor, action, resource, outcome, timestamp, request reference |

## Constraints

- Organization memberships are unique per user and organization.
- Project memberships are unique per user and project.
- Organization-scoped records must match the project's organization; cross-organization collaboration uses explicit project grants.
- Submissions reference immutable revisions. Decisions reference a review assignment and exact submission.
- Clearance evidence has separate access restrictions; a public report does not expose consent forms.
- An approved submission is necessary but insufficient for a public release.
- Private files cannot become public merely because their parent project has public metadata.
- Analysis runs retain the input checksum and software versions required to reproduce results.
- Deletion and retention policies cover file bytes, metadata, search indexes, assistant memory and backups.
- Audit records must exclude report bodies, participant identifiers, access tokens and credentials.

## Search fields

Index title, abstract, author display names, affiliation, discipline, keywords, release year and review label for authorized public releases only. Treat filenames, draft abstracts and organization membership as private unless deliberately released.

