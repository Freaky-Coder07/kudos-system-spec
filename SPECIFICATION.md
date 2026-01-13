# Kudos System Specification

## Overview

The Kudos System is a feature for Datacom’s internal employee portal that allows employees to recognise and appreciate their colleagues through short public messages. These kudos messages appear in a shared feed on the main dashboard to promote a positive and supportive workplace culture.

To ensure appropriate use of the platform, administrators can moderate content by hiding or deleting inappropriate kudos messages.

---

## Functional Requirements

### User Stories

1. **Give Kudos**  
   As a user, I can select a colleague from a list, write a short message of appreciation, and submit it.

2. **View Kudos Feed**  
   As a user, I can view a public feed of recently submitted kudos on the main dashboard.

3. **Authentication**  
   As a user, I must be logged in to submit kudos.

4. **Content Moderation (Admin)**  
   As an administrator, I can hide or delete inappropriate kudos messages.

5. **Prevent Abuse**  
   As the system, I should prevent spam, duplicate submissions, and inappropriate content.

---

### Acceptance Criteria

#### Give Kudos
- Users can select another employee from a searchable list  
- Messages are limited to 250 characters  
- Kudos are stored in the database  
- A confirmation message is shown after submission  

#### View Feed
- Only visible kudos appear in the public feed  
- Each kudos displays sender, recipient, message, and timestamp  
- The feed is ordered by most recent first  

#### Content Moderation
- Admins can view all kudos, including hidden ones  
- Admins can hide kudos without deleting them  
- Admins can permanently delete kudos  
- Hidden kudos do not appear in the public feed  
- Moderation actions are logged  

#### Security
- Only authenticated users can submit kudos  
- Only admins can moderate content  
- User input is sanitized to prevent malicious content  

---

## Technical Design

### Database Schema

#### Users Table
| Field | Type | Description |
|------|------|-------------|
| id | UUID | Primary key |
| name | String | User name |
| email | String | User email |
| role | Enum | user / admin |

#### Kudos Table
| Field | Type | Description |
|------|------|-------------|
| id | UUID | Primary key |
| sender_id | UUID | Foreign key to Users |
| recipient_id | UUID | Foreign key to Users |
| message | String | Kudos message |
| created_at | Timestamp | Time of submission |
| is_visible | Boolean | Default: true |
| moderated_by | UUID | Admin user ID |
| moderated_at | Timestamp | Time of moderation |
| reason_for_moderation | String | Optional |

---

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/kudos | Submit a kudos |
| GET | /api/kudos | Get visible kudos |
| GET | /api/kudos/all | Admin: view all kudos |
| PATCH | /api/kudos/:id/hide | Hide a kudos |
| DELETE | /api/kudos/:id | Delete a kudos |
| GET | /api/users | Get list of users |

---

### Frontend Components

#### User Interface
- KudosForm (submit kudos)  
- KudosFeed (display kudos)  
- UserSelector (select colleague)  

#### Admin Interface
- ModerationDashboard  
- KudosTable  
- ModerationActions (hide/delete)  

---

### Security Considerations

- JWT authentication  
- Role-based access control  
- Input sanitization  
- Rate limiting for submissions  

---

### Performance Considerations

- Pagination for kudos feed  
- Indexed timestamps  
- Caching recent kudos  

---

## Implementation Plan

1. Set up project structure  
2. Configure database  
3. Implement authentication  
4. Create Kudos API  
5. Build frontend form  
6. Build feed display  
7. Add moderation panel  
8. Implement admin API  
9. Testing  
10. Deployment  

---

## Testing Strategy

- Unit tests for API endpoints  
- Integration tests for moderation  
- UI tests for kudos submission  
- Security testing  

---

## Deployment

- Docker container  
- Environment variables  
- CI/CD pipeline  
- Database migrations  

---

## Final Notes

This specification was created using a spec-driven development approach.  
All functional requirements, content moderation, technical design, and implementation planning were completed before any coding began.  
This ensures clarity, consistency, and quality in the final system.
