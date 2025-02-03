# EE 10th Anniversary Workshop Signups - PoC Specification

## 1. Project Overview

### Project Name
EE 10th Anniversary Workshop Signups

### Brief Description
A platform that enables community members to propose and host workshops, while allowing attendees to discover and sign up for workshops during the EE 10th Anniversary event.

### Core Purpose
To facilitate community-driven workshop creation and attendance management for the EE 10th Anniversary celebration.

### Primary Objectives
1. Enable community members to propose and publish workshops
2. Provide an easy workshop discovery and signup system for attendees
3. Manage workshop capacity and schedules
4. Track attendance and registrations

### Target Audience
- Workshop Hosts (Community Members)
- Workshop Attendees
- Event Administrators

## 2. Key Features & Functionality

### Workshop Creation
- Workshop proposal submission form
- Fields for title, description, capacity, duration, prerequisites
- Host profile and credentials
- Time slot preferences

### Workshop Discovery & Registration
- Browsable workshop catalog
- Search and filter capabilities
- Automatic waitlist when registration exceeds 20 people
- No restriction on number of workshops users can join
- Capacity management

### Management Features
- Open workshop submission system (no pre-approval required)
- Schedule management
- Attendance tracking
- Email notifications for:
  - Workshop submission confirmation
  - Registration confirmation
  - Waitlist status updates
  - Schedule changes

## 3. Technical Approach

### Technology Stack
- **Front-end**: React (for interactive UI components)
- **Back-end**: Node.js with Express
- **Database**: PostgreSQL (for relational data like users, workshops, registrations)
- **Authentication**: Auth0 or similar
- **Email Service**: SendGrid

### High-Level Architecture
- Single page application (SPA) for dynamic user experience
- RESTful API for data operations
- Real-time registration counts and waitlist management
- Event-driven email notifications

### Data Model
- **Users**
  - Basic profile info
  - Workshop hosting/attendance history
- **Workshops**
  - Details (title, description, etc.)
  - Capacity (hard limit at 20)
  - Schedule information
- **Registrations**
  - User-Workshop relationship
  - Waitlist position (if applicable)
  - Registration timestamp

## 4. Implementation Plan

### Milestones

1. **Foundation Setup** 
   - Expected Deliverables:
     - Project repository setup
     - Basic React app structure
     - Express server setup
     - Database schema implementation
     - Authentication integration
   - Duration: 5 days

   #### User Story 1: Authentication System
   As a user
   I want to be able to create an account and log in
   So that I can access the workshop platform securely

   Acceptance Criteria:
   ```gherkin
   Scenario: User Registration
     Given I am on the registration page
     When I fill in my details and submit
     Then I should receive a confirmation email
     And be able to log in with my credentials

   Scenario: User Login
     Given I am a registered user
     When I enter my credentials
     Then I should be logged in
     And see my personalized dashboard
   ```

   Technical Design:
   - Implement Auth0 integration
   - Create user profile schema
   - API endpoints:
     - POST /api/auth/register
     - POST /api/auth/login
     - GET /api/auth/profile

   #### User Story 2: Database Schema
   As a system administrator
   I want to have a properly structured database
   So that workshop and user data can be stored efficiently

   Acceptance Criteria:
   ```gherkin
   Scenario: Data Storage
     Given the system is running
     When data is submitted
     Then it should be stored in the correct tables
     And maintain referential integrity
   ```

   Technical Design:
   - PostgreSQL schema with tables:
     - users (id, email, name, created_at)
     - workshops (id, title, description, capacity, host_id, schedule)
     - registrations (id, user_id, workshop_id, status, position)
     - waitlist (id, user_id, workshop_id, position)

2. **Core Features**
   - Expected Deliverables:
     - Workshop creation flow
     - Workshop listing and search
     - Basic registration system
     - Email notification setup
   - Duration: 10 days

   #### User Story 3: Workshop Creation
   As a workshop host
   I want to create and publish a workshop
   So that attendees can discover and register for it

   Acceptance Criteria:
   ```gherkin
   Scenario: Workshop Submission
     Given I am logged in as a host
     When I submit a workshop with required details
     Then it should appear in the workshop catalog
     And I should receive a confirmation

   Scenario: Workshop Validation
     Given I am submitting a workshop
     When I enter invalid details
     Then I should see appropriate error messages
   ```

   Technical Design:
   - Create workshop submission form
   - Implement validation logic
   - API endpoints:
     - POST /api/workshops
     - GET /api/workshops
     - PUT /api/workshops/{id}

   #### User Story 4: Workshop Registration
   As an attendee
   I want to browse and register for workshops
   So that I can participate in the event

   Acceptance Criteria:
   ```gherkin
   Scenario: Workshop Registration
     Given I am logged in
     When I register for an available workshop
     Then I should receive a confirmation
     And see it in my schedule

   Scenario: Capacity Management
     Given a workshop is at capacity
     When I try to register
     Then I should be added to the waitlist
   ```

   Technical Design:
   - Implement registration system with capacity checks
   - Create waitlist management
   - API endpoints:
     - POST /api/workshops/{id}/register
     - GET /api/user/registrations
     - DELETE /api/workshops/{id}/register

3. **Advanced Features**
   - Expected Deliverables:
     - Waitlist functionality
     - Real-time capacity updates
     - Email notifications for status changes
     - User dashboard
   - Duration: 5 days

   #### User Story 5: Waitlist Management
   As an attendee
   I want to join a waitlist for full workshops
   So that I can potentially attend if spots become available

   Acceptance Criteria:
   ```gherkin
   Scenario: Waitlist Position
     Given I am on a waitlist
     When I check my status
     Then I should see my current position

   Scenario: Spot Available
     Given I am on a waitlist
     When a spot becomes available
     Then I should be automatically promoted
     And receive a notification
   ```

   Technical Design:
   - Implement waitlist queue system
   - Create automated waitlist promotion
   - API endpoints:
     - POST /api/workshops/{id}/waitlist
     - GET /api/workshops/{id}/waitlist-position

4. **Testing & Polish**
   - Expected Deliverables:
     - User acceptance testing
     - Bug fixes
     - Performance optimization
     - Documentation
   - Duration: 5 days

   #### User Story 6: System Testing
   As a system administrator
   I want to ensure the platform works under load
   So that users have a smooth experience during the event

   Acceptance Criteria:
   ```gherkin
   Scenario: Concurrent registrations
     Given multiple users are registering simultaneously
     When they submit registrations
     Then the system should handle requests correctly
     And maintain data consistency
   ```

   Technical Design:
   - Implement end-to-end testing suite
   - Set up load testing scenarios
   - Create monitoring dashboard
   - Document API endpoints and error handling

## 5. Risk Assessment & Constraints

### Potential Risks

1. **High Concurrent Users**:
   - Mitigation: Implement request queuing and rate limiting
   
2. **Email Delivery Issues**:
   - Mitigation: Add retry logic and delivery status tracking

3. **Double Bookings**:
   - Mitigation: Implement transaction locks for registrations

### Constraints

- Must handle concurrent workshop registrations
- Email service limited to 100 emails/day on free tier
- Mobile-responsive design required
- Must work across major browsers

## 6. Success Criteria

### Key Performance Indicators (KPIs)
1. Workshop submission success rate > 95%
2. Registration system uptime > 99%
3. Email notification delivery rate > 95%
