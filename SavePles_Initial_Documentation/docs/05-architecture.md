# Proposed architecture

Status: design proposal. No cloud resources have been provisioned.

## Initial structure

Use a modular application with a single API deployment. Keep identity, organizations, research, reviews, archive, analysis and assistance as separate modules. Introduce independently deployed services only where runtime requirements or measured load justify them.

| Component | Proposed implementation | Responsibility |
| --- | --- | --- |
| Web client | React and TypeScript | Workspace, review interface and archive browsing |
| API | Cloudflare Workers | Authentication integration, authorization, metadata and workflow operations |
| Metadata | Cloudflare D1 | Users, memberships, projects, submissions, releases and audit references |
| Object storage | Private Cloudflare R2 | Papers, datasets, generated reports and charts |
| Job delivery | Cloudflare Queues | Document processing, analysis dispatch and notifications |
| Statistical worker | Separate Python runtime, provider pending | Established statistical libraries and bounded analysis jobs |
| Identity provider | To be selected | Verified accounts, session lifecycle and recovery |
| Assistant provider | To be selected | Constrained research guidance through authorized tools |

Workers serve the web assets and API. Private object requests are authorized before access. Public archive search reads only released metadata; it does not search private drafts.

## Data path

Uploads enter quarantine, undergo type, size and malware checks, and become available only after validation. Store file metadata in D1 and bytes in R2. Use opaque object keys and project/resource authorization.

An analysis request records the dataset version and validated method parameters, creates a job and dispatches it asynchronously. The Python worker receives only a scoped input grant. Results attach to the originating analysis run. Retry handling must not create duplicate runs or duplicate publications.

## Security boundaries

The browser never receives infrastructure credentials. Session verification and authorization occur at the API. Queue messages carry identifiers rather than raw participant data. Download grants are short-lived and scoped; where immediate revocation is required, use an authenticated proxy rather than a reusable signed link.

Assistant access follows the caller's project permissions. Do not mix private and public search indexes. Do not introduce semantic indexing until deletion and access-control behavior is tested.

## Growth and operations

Start with indexed relational queries and pagination. Measure query cost, storage, job duration and concurrent usage before changing databases or introducing sharding. Separate development, staging and production data and credentials. Use synthetic records in test environments.

Backup object data and metadata together with a manifest sufficient to verify restoration. Define retention, recovery objectives, cost ceilings and the hosting region requirements before a production pilot.

## Open decisions

Identity provider, Python hosting, assistant model, email delivery, institutional hosting restrictions, budget and deployment automation remain unresolved. Check current product compatibility, quotas and pricing before provisioning.

Technical references are listed in [References](10-references.md).

