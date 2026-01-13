# Task 2: Building from Scratch with Spec-Driven Development

## Scenario

You are continuing in your role as a Graduate Developer at Datacom. Your manager has entrusted you with building a "Kudos" system for the internal employee portal. The initial request is simple: "We need a way for people to give kudos to each other." Your job is to take on the role of an AI Architect, using a spec-driven development process to transform this ambiguous idea into a robust feature.

## Learning Objectives

- The fundamental difference between interactive "vibe coding" and structured, planning-first methodology
- The practical workflow for translating high-level feature requests into formal specifications
- The critical role of the developer in reviewing, refining, and augmenting AI-generated requirements
- How to manage and execute development plans based on pre-defined task lists

## Deliverables

1. **A link to a new, public Git repository** containing the full project source code
2. **`SPECIFICATION.md`** - The final, refined requirements and technical design used to generate the code

## Step-by-Step Instructions

### Step 1: Initiate the Specification

1. In your chosen AI development environment, initiate the process for generating a new feature from a high-level description
2. Enter the initial prompt:
   ```
   Create a feature for our internal web app that allows users to give 'kudos' to their colleagues. A user should be able to select another user from a list, write a short message of appreciation, and submit it. There should also be a public feed on the main dashboard where all recently submitted kudos are visible.
   ```

### Step 2: Review and Refine the Specification

The AI will process your request and generate a formal specification, likely including functional requirements and a technical design.

#### Your Task (Requirements): Add Content Moderation

The initial request did not consider content moderation. As the architect, you must add this:

- Edit the generated requirements to add a new user story for an administrator to be able to hide or delete inappropriate kudos messages
- Consider edge cases like spam, inappropriate content, or duplicate submissions

#### Your Task (Design): Update Database Schema

Review the proposed database schema. To support the moderation feature, the design needs to be updated:

- Edit the design document to add a new field to the Kudos table, such as `is_visible` (boolean, default: true)
- Consider additional fields that might be needed for moderation (e.g., `moderated_by`, `moderated_at`, `reason_for_moderation`)

### Step 3: Approve the Specification and Execute Implementation

1. Once you have refined the specification to be complete and correct, formally approve it within your development environment
2. This approval will trigger the AI agent to begin the implementation phase, following the plan it generated based on your approved spec
3. Observe as it creates files and writes the code

### Step 4: Commit and Push to Repository

1. Once the AI has completed the implementation, your feature is complete
2. Save the final requirements and design you approved into a single `SPECIFICATION.md` file
3. Initialize a new Git repository, add all the generated files (including your `SPECIFICATION.md`), and create an initial commit
4. Create a new public repository on a platform like GitHub or GitLab and push your local repository to it

## Specification Requirements Checklist

### Functional Requirements Should Include:

- [ ] User authentication and authorization
- [ ] User selection from a list of colleagues
- [ ] Kudos message creation and submission
- [ ] Public feed display of recent kudos
- [ ] Content moderation capabilities
- [ ] Input validation and error handling
- [ ] Responsive design for different screen sizes

### Technical Design Should Include:

- [ ] Database schema with all necessary tables and relationships
- [ ] API endpoints and their specifications
- [ ] Frontend components and their interactions
- [ ] Security considerations (authentication, authorization, input sanitization)
- [ ] Performance considerations (pagination, caching, etc.)
- [ ] Error handling and logging strategies

### Implementation Plan Should Include:

- [ ] Step-by-step breakdown of development tasks
- [ ] Dependencies between tasks
- [ ] Testing strategy
- [ ] Deployment considerations

## Example Specification Structure

Your `SPECIFICATION.md` should follow this structure:

```markdown
# Kudos System Specification

## Functional Requirements

### User Stories

1. As a user, I can select another user from a dropdown list
2. As a user, I can write a message of appreciation (max 500 characters)
3. As a user, I can submit the kudos which gets stored in the database
4. As a user, I can view a feed of recent kudos on the dashboard
5. As an administrator, I can hide or delete inappropriate kudos messages

### Acceptance Criteria

- [Detailed criteria for each user story]

## Technical Design

### Database Schema

- [Table definitions with fields, types, and relationships]

### API Endpoints

- [List of endpoints with methods, parameters, and responses]

### Frontend Components

- [Component hierarchy and interactions]

## Implementation Plan

- [Step-by-step task breakdown]
```

## Key Principles to Remember

1. **Specification First**: Don't start coding until the specification is complete and approved
2. **Human-in-the-Loop**: You are responsible for ensuring the AI understands the business requirements correctly
3. **Iterative Refinement**: The specification may need multiple rounds of review and refinement
4. **Completeness**: Ensure all edge cases and requirements are captured before implementation

## Reflection Questions

After completing the task, consider:

1. **How did the structured approach to specification change your development process compared to traditional coding?**

2. **What was the most challenging part of reviewing and refining the AI-generated specification?**

3. **How did having a complete specification before implementation affect the quality and completeness of the final code?**

## Tips for Success

- Take time to thoroughly review the AI-generated specification
- Don't hesitate to add missing requirements or modify the design
- Consider edge cases and error scenarios
- Ensure the specification is detailed enough for the AI to implement correctly
- Remember that your role as Architect is to think strategically, not tactically

This structured process highlights a fundamental shift in the developer's role. The highest-value work is performed during the specification and review phases. By ensuring the blueprint is correct, you guarantee that the subsequent AI-driven implementation will be successful.
