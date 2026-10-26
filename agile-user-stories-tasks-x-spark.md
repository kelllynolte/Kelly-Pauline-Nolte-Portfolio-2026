# X Spark Agile User Stories and Tasks

## 1. Project Information

- **Company:** X Spark
- **Project:** BeeHive and Purple Bee Integration
- **Project Type:** Industry Placement / Company Project
- **Development Approach:** Agile
- **Document:** User Stories and Tasks

## 2. Project Overview

The project focuses on integrating BeeHive, an internal meeting application, with Purple Bee, a work-management application. The proposed first version allows an authorised Project Lead to send confirmed meeting action items from BeeHive to Purple Bee as tasks through secure server-to-server API communication.

The integration is intended to reduce manual task creation and help teams track meeting action items in their work-management system.

## 3. User Stories and Tasks

### User Story 1: Submit a Meeting Action Item

**User story**

As an authorised Project Lead, I want to send a confirmed action item from BeeHive to Purple Bee so that the action item can be managed as a task.

**Acceptance criteria**
- The user must have an active Admin or Manager role.
- The action item must contain the required information.
- The system must validate the action item before submitting it.
- The user must receive an appropriate success or error response.

**Tasks**
- Confirm the required action-item fields.
- Validate the user's role and permissions.
- Prepare the action item for API submission.
- Handle success and failure responses.

### User Story 2: Validate Task Information

**User story**

As a system, I want to validate the action item's required fields so that incomplete or invalid tasks are not created in Purple Bee.

**Acceptance criteria**
- A title, project, assignee, priority, and valid due date must be provided.
- Past due dates must be rejected.
- Invalid submissions must return an appropriate validation error.

**Tasks**
- Identify mandatory fields.
- Implement or document validation rules.
- Check due-date and field validation.
- Record validation errors for the user.

### User Story 3: Create a Task in Purple Bee

**User story**

As a Project Lead, I want a valid BeeHive action item to create a task in Purple Bee so that I can track the work after the meeting.

**Acceptance criteria**
- The task is submitted through the agreed server-to-server HTTPS API.
- The created task uses the supplied project, assignee, priority, title, and due date.
- The task starts with a To Do status and 0% progress.
- The task is not recurring by default.

**Tasks**
- Confirm the Purple Bee API contract.
- Map BeeHive action-item fields to Purple Bee task fields.
- Submit validated task data.
- Verify the resulting task information.

### User Story 4: Prevent Duplicate Tasks

**User story**

As a system, I want to identify repeated submissions of the same action item so that retries do not create duplicate tasks.

**Acceptance criteria**
- Each submission uses the agreed idempotency key format: `beehive:{meeting_id}:{action_item_id}`.
- Repeated submissions with the same key and unchanged content are handled idempotently.
- Reuse of the same key with changed content returns a conflict response (HTTP 409).

**Tasks**
- Agree on idempotency-key handling.
- Store and check the submission receipt.
- Handle repeated requests.
- Test duplicate and changed-content scenarios.

### User Story 5: Store the Created Task Reference

**User story**

As a system, I want BeeHive to store the Purple Bee task UUID so that the original action item can be linked to the created task.

**Acceptance criteria**
- The Purple Bee task UUID is stored after successful creation.
- The reference is associated with the correct BeeHive action item.
- Failed submissions are handled without storing an invalid task reference.

**Tasks**
- Confirm where the reference will be stored in BeeHive.
- Save the returned Purple Bee task UUID.
- Handle unsuccessful API responses.
- Verify the stored reference.

### User Story 6: Notify the Assigned User

**User story**

As an assignee, I want to receive an assignment notification when a task is successfully created so that I know work has been assigned to me.

**Acceptance criteria**
- The assignment notification is triggered as part of the successful task-creation workflow.
- Failed task creation does not produce a misleading success notification.
- Notification behaviour follows the agreed Purple Bee implementation.

**Tasks**
- Confirm the notification mechanism.
- Connect successful task creation to the notification workflow.
- Check notification behaviour.
- Test success and failure cases.

### User Story 7: Protect Integration Communication

**User story**

As a system administrator, I want communication between BeeHive and Purple Bee to be secure so that only authorised systems can exchange task information.

**Acceptance criteria**
- Communication uses HTTPS.
- Server-to-server authentication follows the agreed security design.
- The integration uses the correct development, staging, or production environment.
- The integration does not directly connect the two application databases.

**Tasks**
- Confirm the authentication requirements.
- Configure the appropriate environment settings.
- Verify secure API communication.
- Check that the integration uses the approved API rather than direct database access.

## 4. Scope Notes

The first version is limited to sending confirmed BeeHive action items to Purple Bee when initiated by an authorised Project Lead.

The following are outside the confirmed first-version scope:
- Automatic task creation without Project Lead initiation.
- Two-way synchronisation between BeeHive and Purple Bee.
- Direct database-to-database integration.
- Integration of meeting recordings.

## 5. Agile Status Tracking

The user stories and tasks above are based on the project requirements. They are not confirmation that every feature has been implemented.

Update the status of each task with the project team.

Suggested statuses:
- To Do
- In Progress
- Done
- Blocked

## 6. Reflection

Preparing these user stories helps translate the integration requirements into user-focused outcomes and smaller development tasks. The acceptance criteria clarify how each feature should behave and provide a basis for testing.

This process also highlights the importance of secure API communication, input validation, duplicate prevention, and clear task ownership. As the project progresses, the stories and tasks should be reviewed with the team and updated to reflect agreed priorities and actual implementation progress.
