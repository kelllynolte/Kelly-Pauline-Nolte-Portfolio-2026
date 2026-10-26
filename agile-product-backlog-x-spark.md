# X Spark Product Backlog

## 1. Project Information

- **Company:** X Spark
- **Project:** BeeHive and Purple Bee Integration
- **Project Type:** Industry Placement / Company Project
- **Development Approach:** Agile
- **Document:** Product Backlog

## 2. Product Vision

The goal of this project is to enable authorised Project Leads to transfer confirmed action items from BeeHive into Purple Bee as tasks through a secure server-to-server API integration.

The integration aims to reduce manual task creation, improve task tracking, and maintain a clear connection between meeting action items and the resulting work-management tasks.

## 3. Product Backlog Items

The following items are prioritised according to their importance to the proposed first version. Priorities and statuses should be reviewed with the project team.

| ID | Backlog Item | Description | Priority | Status |
|---|---|---|---|---|
| PB01 | Role and Permission Validation | Ensure that only authorised users with an active Admin or Manager role can initiate the integration. | High | To Do |
| PB02 | Action Item Validation | Validate the required title, project, assignee, priority, and non-past due date. | High | To Do |
| PB03 | Secure API Communication | Enable communication between BeeHive and Purple Bee through server-to-server HTTPS APIs. | High | To Do |
| PB04 | Task Field Mapping | Map the required BeeHive action-item fields to the corresponding Purple Bee task fields. | High | To Do |
| PB05 | Purple Bee Task Creation | Create a Purple Bee task from a valid, confirmed BeeHive action item when initiated by an authorised Project Lead. | High | To Do |
| PB06 | Default Task Values | Ensure the created task starts with To Do status, 0% progress, and no recurrence. | High | To Do |
| PB07 | Duplicate Submission Prevention | Use the agreed idempotency key to prevent duplicate tasks when the same action item is submitted repeatedly. | High | To Do |
| PB08 | Conflict Handling | Return an HTTP 409 conflict response when the same idempotency key is reused with changed content. | High | To Do |
| PB09 | Task Reference Storage | Store the resulting Purple Bee task UUID against the corresponding BeeHive action item. | High | To Do |
| PB10 | Assignment Notification | Trigger the agreed assignment notification as part of successful task creation. | Medium | To Do |
| PB11 | Error Handling | Handle invalid input, failed API requests, permission failures, and other unsuccessful submissions appropriately. | High | To Do |
| PB12 | Environment Configuration | Support the appropriate development, staging, and production environments without directly connecting their databases. | High | To Do |
| PB13 | Integration Testing | Test successful submissions, invalid data, duplicate requests, conflicts, and API failures. | High | To Do |
| PB14 | Integration Documentation | Document the integration flow, requirements, API behaviour, and known limitations. | Medium | To Do |

## 4. Prioritisation

High-priority items support the core integration workflow, including security, validation, task creation, duplicate prevention, error handling, and testing.

Medium-priority items support notifications and documentation. The final prioritisation must be agreed with the project team.

## 5. Scope and Limitations

The first version covers the manual initiation of confirmed BeeHive action items by an authorised Project Lead and their creation as tasks in Purple Bee.

The following are excluded from the first version:
- Automatic task creation without Project Lead initiation.
- Two-way synchronisation.
- Direct database-to-database integration.
- Meeting recording integration.

## 6. Backlog Maintenance

The product backlog should be reviewed and updated as requirements are clarified and the team agrees on priorities.

Each item should be assigned an agreed status:
- To Do
- In Progress
- Done
- Blocked

The status must reflect the actual project progress. The items listed above are requirements-based backlog proposals and should not be treated as completed features without evidence.

## 7. Reflection

Creating a product backlog helps organise project requirements into manageable pieces of work. Prioritisation helps the team focus on the features required for the core integration before addressing supporting activities.

This backlog also highlights the importance of security, data validation, reliable API communication, duplicate prevention, and testing when integrating two applications. It should be reviewed with the team to ensure that it reflects the agreed scope and current development priorities.
