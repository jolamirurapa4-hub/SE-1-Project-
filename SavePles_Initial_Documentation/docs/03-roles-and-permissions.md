# Roles and permissions

Permissions combine platform role, verified organization membership, project membership, resource visibility and workflow state. Deny access unless an explicit rule allows it.

## Roles

| Role | Authority |
| --- | --- |
| Visitor | Browse and download permitted public releases. |
| Researcher | Create projects, manage owned drafts and request review or publication. |
| Project collaborator | Read or edit assigned project resources according to the membership grant. |
| Student coordinator | Coordinate a research group and submit on its behalf when delegated. |
| Organization administrator | Manage organization membership and configuration; cannot self-verify institutional authority. |
| Verified supervisor / HoD / reviewer | Review assigned submissions within a verified institutional scope. |
| Archive moderator | Handle publication checks, reports, restrictions and withdrawals. |
| Platform administrator | Maintain the service, verify role appointments and handle documented support cases. |

## Permission matrix

| Action | Researcher / collaborator | Coordinator | Organization admin | Assigned verified reviewer | Moderator |
| --- | --- | --- | --- | --- | --- |
| Edit project | If granted | If granted | Only if separately granted | No, unless separately granted | No |
| Invite project members | Owner or delegated manager | If delegated | No automatic grant | No | No |
| Submit a version | Owner or delegated submitter | If delegated | No automatic grant | No | No |
| Record institutional decision | No | No | No automatic grant | Yes, within scope | No |
| Change project visibility | Owner within policy | If delegated | No automatic grant | No | May restrict release |
| Release approved report | Request release | If delegated | No automatic grant | No automatic grant | Complete release checks |
| Read raw dataset | Explicit dataset grant | Explicit dataset grant | No automatic grant | Explicit dataset grant | No automatic grant |

## Rules

- Membership in a faculty or organization does not expose every private project.
- Student leader nominations require acceptance and do not confer institutional review powers.
- Institutional roles require evidence of appointment and verification by an authorized independent administrator.
- Reviewers cannot approve their own work. Conflicts of interest require reassignment.
- Granting, revoking and verifying roles creates an audit event.
- Revoked access applies to future requests and downloads; previously downloaded copies cannot be recalled.
- Platform administrator status is not a research approval credential. Any exceptional private-data access must be scoped, justified and audited.
- Organization ownership transfer requires a verified replacement and a recorded handover.

