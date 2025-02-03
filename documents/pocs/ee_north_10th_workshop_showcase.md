# EE North 10th Anniversary Workshop Showcase

# 2. Project Overview

### Project Name
EE North 10th Anniversary Workshop Showcase

### Brief Description
A clean, single-page showcase of all workshops available at the EE North 10th Anniversary celebration. The application presents workshops in an easy-to-scan format, allowing attendees to quickly browse through all offerings.

### Core Purpose
To provide a clear, comprehensive overview of all workshops available during the EE North 10th Anniversary celebration in a single, easy-to-navigate page.

### Primary Objectives
1. Display all workshops in a clean, organized layout on a single page
2. Make it easy to scan and compare different workshop offerings
3. Provide essential workshop information at a glance
4. Create a simple, intuitive user experience

### Target Audience
- EE North anniversary event attendees
- Workshop facilitators and organizers
- EE North community members

# 3. Key Features & Functionality

### Feature 1: Workshop Grid Layout
- Responsive grid of workshop cards
- Each card displays:
  - Workshop title
  - Facilitator name
  - Time and duration
  - Brief description
  - Location
  - Available spots remaining
- Clean, consistent card design
- Automatic responsive layout for all screen sizes

### Feature 2: Workshop Registration
- One-click registration from workshop cards
- Registration status indicators:
  - Available (with spots remaining)
  - Almost Full (less than 20% spots left)
  - Full (waitlist available)
- Simple cancellation process
- Waitlist management for full workshops

### Feature 3: Workshop Creation
- Simple workshop creation form with:
  - Title and description fields
  - Date and time picker
  - Duration selector
  - Location input
  - Maximum capacity setting
  - Facilitator information
- Form validation with helpful error messages
- Preview capability before submission
- Success confirmation with direct link to created workshop
- Edit capability for workshop creators

# 4. Technical Approach

### Technology Stack
- **Front-end**: React with TypeScript, TailwindCSS for styling
- **Back-end**: FastAPI (Python)
- **Database**: SQLite (for simplicity in PoC phase)

### High-Level Architecture
Simple single-page application (SPA):
- Static React frontend
- Minimal API endpoints for workshop data, registration, and creation
- Single database table for workshop information
- Registration management system

### Data Model
1. Workshops
   - ID
   - Title
   - Description
   - Facilitator name
   - Start time
   - Duration
   - Location
   - Maximum capacity
   - Current registration count
   - Waitlist enabled (boolean)
   - Created at
   - Last modified
   - Creator ID

2. Registrations
   - ID
   - Workshop ID
   - Registration timestamp
   - Status (confirmed/waitlisted/cancelled)
   - Confirmation code

# 5. Implementation Plan

### Milestones
1. **Basic Layout & Data Structure**: 
   - Set up project structure
   - Implement basic grid layout
   - Create workshop data schema

2. **Core Functionality**:
   - Workshop card component
   - Workshop creation form
   - Image upload integration
   - Filtering system
   - Responsive design

### Constraints
- Must work well on both desktop and mobile devices
- Should load and render quickly
- Must be accessible and easy to read

# 7. Success Criteria & Measurement

### Goals for Proof of Concept
- All workshops visible and readable on a single page
- Filters working smoothly
- Workshop creation form functioning correctly
- Responsive layout functioning on all common screen sizes
- Clear presentation of workshop information 