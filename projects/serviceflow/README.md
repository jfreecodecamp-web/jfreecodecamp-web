# ServiceFlow — Service Desk Prototype

**Portfolio project by Javel Swaby**

ServiceFlow explores how an IT helpdesk can turn incoming requests into trackable incidents, assign work to support groups, and communicate progress clearly.

This folder contains the project overview, workflow requirements, and proposed acceptance checks. **Application source code and local setup instructions are not included yet.** It is documentation for the existing prototype, rather than an installable application.

## Business problem

Support requests need a consistent intake process, a clear owner, visible status, and a record of the conversation. Multiple support groups also need rules governing which tickets they can view and search.

The project draws on practical helpdesk workflows to explore these needs.

## Prototype interface

The documented prototype includes:

- Incident intake and ticket reference numbers.
- Incident status and priority filters.
- Ticket assignment to support groups.
- Team workload summaries and recent activity.
- Email intake previews.
- Demo profiles and sample incidents.

The prototype identifies itself as a demo: changes are saved in the browser and emails are previewed. These interface features do not establish a production email service, shared database, or server-enforced authorization.

## Workflow requirements

The following requirements capture the requested behavior. They are presented separately from verified implementation.

| ID | Area | Required behavior |
| --- | --- | --- |
| SF-01 | Group visibility | A support-group member can view tickets assigned to their group. Tickets assigned only to another group are excluded. |
| SF-02 | Administrator visibility | A Helpdesk Administrator can view helpdesk intake and tickets assigned to any support group. |
| SF-03 | Search | Search matches requester name, subject, and message details. Results follow the signed-in user's ticket visibility rules. |
| SF-04 | Reply indicators | Incoming replies display a red numeric badge: one reply shows 1 and two replies show 2. |
| SF-05 | Ticket closure | Once the helpdesk closes a ticket, the requester cannot add another reply. |

## Roles and access

| Role | Intended scope |
| --- | --- |
| Helpdesk Administrator | All helpdesk tickets, including tickets assigned to other groups. |
| Support-group member | Tickets assigned to the member's support group. |
| Requester | Their ticket conversation, with replying disabled after helpdesk closure. |

Role and group restrictions require server-side enforcement before this design is used with shared, real-world data. Demo profile switching represents prototype behavior, not an authentication mechanism.

## Proposed acceptance checks

These checks document expected behavior. They have not been executed as part of this documentation update.

| Check | Scenario | Expected result |
| --- | --- | --- |
| AC-01 | A BUSS member opens All Tickets while a ticket is assigned only to Networking. | The Networking ticket is excluded. |
| AC-02 | A Helpdesk Administrator opens All Tickets. | Helpdesk intake and tickets across support groups are available. |
| AC-03 | A group member searches for a requester or phrase found only on another group's ticket. | The out-of-scope ticket is excluded from results. |
| AC-04 | An administrator searches for a requester name, subject term, or phrase in message details. | Matching tickets within the administrator's full scope are returned. |
| AC-05 | One incoming reply arrives, followed by a second. | The ticket's red reply badge shows 1, then 2. |
| AC-06 | The helpdesk closes a ticket and the requester attempts to reply. | The reply is rejected and the closed state is shown clearly. |

Badge reset and read-state behavior should be specified before accepting SF-04.

## Portfolio relevance

This project connects business workflows with software behavior through:

- Problem definition and role identification.
- Access rules and search scope.
- Ticket lifecycle and communication requirements.
- Proposed acceptance criteria for validation.
- A clear distinction between prototype behavior and production requirements.

## Project status

- **Available here:** Project overview, requirements, role matrix, and proposed acceptance checks.
- **Pending publication:** Existing application source code, its confirmed technology stack, and reproducible setup instructions.
- **Verification:** The checks above are proposed checks, not a report of completed application testing.

No employer or customer incident data is included in this documentation.

[Return to Javel Swaby's GitHub profile](https://github.com/jfreecodecamp-web)
