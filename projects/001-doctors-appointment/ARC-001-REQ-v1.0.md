# Project Requirements: NHS Doctors Online Appointment System

> **Document Status**: DRAFT | **Version**: 1.0 | **Command**: `/arckit.requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.0 |
| **Document Type** | Business & Technical Requirements Specification |
| **Project** | NHS Doctors Online Appointment System (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-01-28 |
| **Last Modified** | 2026-01-28 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-28 |
| **Owner** | Product Owner, NHS Digital |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Project Team, NHS Digital, GDS Assessment Team, Clinical Safety Officer |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-28 | ArcKit AI | Initial creation from `/arckit.requirements` command | PENDING | PENDING |

## Document Purpose

This document specifies the complete business, functional, and non-functional requirements for the NHS Doctors Online Appointment System. It serves as the primary reference for design, development, testing, and acceptance criteria. All requirements trace to stakeholder needs and architecture principles defined in ARC-000-PRIN-v1.0.

---

## Executive Summary

### Business Context

The NHS faces significant challenges in GP appointment access. Patients struggle to book appointments through overloaded phone lines, particularly during Monday morning surges. Practice staff spend excessive time on telephone bookings rather than patient care. The current fragmented booking landscape creates inconsistent patient experiences across different GP practices.

The Doctors Online Appointment System will provide a unified, accessible digital channel for patients to book, manage, and cancel GP appointments. By integrating with NHS Spine for patient demographics and GP Connect for appointment availability, the system will offer real-time booking across participating practices while maintaining clinical safety and data protection standards.

This initiative supports NHS Long Term Plan objectives to expand digital access to primary care and aligns with GDS Service Standard requirements for user-centered public services.

### Objectives

- **OBJ-1**: Enable patients to book GP appointments online 24/7 without telephone queues
- **OBJ-2**: Reduce practice staff workload for appointment bookings by 40%
- **OBJ-3**: Improve patient access equity through accessible digital and assisted channels
- **OBJ-4**: Integrate seamlessly with existing GP clinical systems via NHS Digital standards
- **OBJ-5**: Meet GDS Service Standard for Alpha, Beta, and Live assessments

### Expected Outcomes

- **Patient satisfaction**: Achieve 80% satisfaction score for online booking experience within 6 months of launch
- **Digital uptake**: 30% of eligible appointments booked online within 12 months
- **Staff efficiency**: Reduce telephone booking time by 40%, freeing 2 hours/day per practice
- **Access equity**: No decrease in appointment access for non-digital users
- **System reliability**: 99.9% availability during core hours (8am-8pm)

### Project Scope

**In Scope**:
- Patient appointment booking, viewing, and cancellation
- NHS Login authentication for patients
- Integration with NHS Spine (PDS) for patient demographics
- Integration with GP Connect for appointment slot availability
- SMS and email appointment reminders
- Accessibility to WCAG 2.2 AA standard
- Welsh language support
- Assisted digital pathway for non-digital users

**Out of Scope**:
- Video consultations (separate NHS programme)
- Prescription ordering (existing NHS App functionality)
- Access to medical records (existing NHS App functionality)
- Private healthcare provider appointments
- Specialist hospital appointments (future phase)
- Practice administration functions

---

## Stakeholders

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| NHS Digital Director | Executive Sponsor | NHS Digital | Decision maker |
| Product Owner | Product Owner | NHS Digital | Requirements definition |
| Clinical Safety Officer | Clinical Governance | NHS Digital | Clinical safety approval |
| GP Practice Manager | Business User | Primary Care | User acceptance |
| Patient Representative | End User | Patient Groups | User research |
| Enterprise Architect | Technical Oversight | NHS Digital | Architecture review |
| Security Lead | Security Governance | NHS Digital | Security approval |
| IG Lead | Information Governance | NHS Digital | DPIA, data handling |
| GDS Assessor | Service Assessment | GDS | Service Standard compliance |

---

## Business Requirements

### BR-1: Online Appointment Booking

**Description**: Patients must be able to book available GP appointments through an online self-service channel without telephone contact.

**Rationale**: Telephone booking creates bottlenecks, particularly Monday mornings. Digital self-service improves access and reduces staff workload.

**Success Criteria**:
- Patients can complete booking in under 3 minutes
- Booking available 24/7 (subject to slot availability)
- Real-time slot availability from GP systems

**Priority**: MUST_HAVE

**Stakeholder**: NHS Digital Director, Patient Representative

---

### BR-2: Appointment Management

**Description**: Patients must be able to view their upcoming appointments and cancel bookings they no longer need.

**Rationale**: Unused appointments (DNAs) cost the NHS significantly. Easy cancellation enables slot reuse.

**Success Criteria**:
- View all upcoming appointments in one place
- Cancel with at least 24 hours notice
- Cancelled slots immediately available for rebooking

**Priority**: MUST_HAVE

**Stakeholder**: GP Practice Manager

---

### BR-3: NHS Identity Integration

**Description**: The system must use NHS Login for patient authentication to ensure correct patient identification and prevent booking fraud.

**Rationale**: NHS Login is the mandated patient authentication service. It provides identity proofing and prevents impersonation.

**Success Criteria**:
- NHS Login integration at appropriate identity proofing level
- Patient identity verified before booking
- No separate registration process

**Priority**: MUST_HAVE

**Stakeholder**: Security Lead, Clinical Safety Officer

---

### BR-4: GP System Integration

**Description**: The system must integrate with GP clinical systems via GP Connect to access real-time appointment availability.

**Rationale**: Appointments must reflect actual availability in GP systems. Manual synchronisation creates booking conflicts.

**Success Criteria**:
- Real-time slot availability (within 30 seconds of GP system)
- Bookings confirmed in GP system immediately
- Support for major GP system suppliers

**Priority**: MUST_HAVE

**Stakeholder**: Enterprise Architect, GP Practice Manager

---

### BR-5: Appointment Reminders

**Description**: Patients must receive reminders before their appointments to reduce non-attendance.

**Rationale**: Appointment reminders reduce DNA rates by up to 30%. SMS and email reach patients effectively.

**Success Criteria**:
- Reminder sent 48 hours before appointment
- Reminder sent 2 hours before appointment
- Patient can opt out of reminders

**Priority**: SHOULD_HAVE

**Stakeholder**: GP Practice Manager

---

### BR-6: Accessibility for All

**Description**: The service must be accessible to all patients including those with disabilities, limited English, or low digital literacy.

**Rationale**: Public services must be accessible under Equality Act 2010. NHS serves entire population including vulnerable groups.

**Success Criteria**:
- WCAG 2.2 Level AA compliance
- Welsh language availability
- Assisted digital pathway available
- Screen reader compatible

**Priority**: MUST_HAVE

**Stakeholder**: Patient Representative, GDS Assessor

---

### BR-7: Clinical Safety

**Description**: The system must be clinically safe and not introduce risks to patient care through incorrect bookings or missed appointments.

**Rationale**: DCB0129 and DCB0160 mandate clinical safety for health IT. Booking errors could delay urgent care.

**Success Criteria**:
- Clinical Risk Management File approved
- Hazard log maintained and reviewed
- No patient safety incidents from system errors

**Priority**: MUST_HAVE

**Stakeholder**: Clinical Safety Officer

---

## Functional Requirements

### User Personas

#### Persona 1: Sarah - Working Parent
- **Role**: Full-time working parent, age 35
- **Goals**: Book GP appointments outside work hours, for herself and children
- **Pain Points**: Cannot call practice during work, phone lines busy at 8am
- **Technical Proficiency**: High - comfortable with apps and online services

#### Persona 2: Arthur - Elderly Patient
- **Role**: Retired, age 78, multiple chronic conditions
- **Goals**: Book regular check-ups, manage appointments
- **Pain Points**: Finds technology challenging, prefers face-to-face
- **Technical Proficiency**: Low - needs simple interface, may need assisted digital

#### Persona 3: Priya - Practice Receptionist
- **Role**: GP practice receptionist, manages appointment book
- **Goals**: Reduce phone calls, see online bookings in clinical system
- **Pain Points**: Monday morning call surge, double bookings, DNAs
- **Technical Proficiency**: Medium - uses clinical system daily

#### Persona 4: Dr. Chen - GP Partner
- **Role**: GP Partner responsible for practice digital transformation
- **Goals**: Improve patient access metrics, reduce DNAs, protect urgent slots
- **Pain Points**: Appointment types misused, urgent slots booked for routine
- **Technical Proficiency**: Medium - uses clinical system, limited time for new systems

---

### Use Cases

#### UC-1: Book Routine Appointment

**Actor**: Patient (Sarah)

**Preconditions**:
- Patient is registered at participating GP practice
- Patient has NHS Login account
- Routine appointment slots available

**Main Flow**:
1. Patient navigates to appointment booking service
2. System prompts for NHS Login authentication
3. Patient authenticates with NHS Login
4. System retrieves patient demographics from PDS
5. System displays patient's registered GP practice
6. Patient selects "Book appointment"
7. System retrieves available slots from GP Connect
8. Patient selects preferred date/time
9. Patient selects reason for appointment (from approved list)
10. System confirms booking details
11. Patient confirms booking
12. System creates booking in GP system via GP Connect
13. System displays booking confirmation with reference number
14. System sends confirmation email/SMS to patient

**Postconditions**:
- Appointment booked in GP clinical system
- Slot no longer available to other patients
- Patient has confirmation with appointment details
- Audit record created

**Alternative Flows**:
- **Alt 7a**: No slots available - System displays message and offers to join waiting list
- **Alt 9a**: Patient unsure of reason - System offers guidance or suggests phone booking

**Exception Flows**:
- **Ex 1**: NHS Login fails - Display error, offer retry or phone booking alternative
- **Ex 2**: GP Connect unavailable - Display service unavailable, suggest trying later
- **Ex 3**: Slot taken during booking - Inform patient, return to slot selection

**Business Rules**:
- Patients can only book at their registered practice
- Maximum 2 advance bookings per patient (configurable per practice)
- Certain appointment types restricted (e.g., urgent, home visits)

**Priority**: CRITICAL

---

#### UC-2: Cancel Appointment

**Actor**: Patient (Sarah)

**Preconditions**:
- Patient has existing booking
- Patient is authenticated

**Main Flow**:
1. Patient navigates to "My appointments"
2. System displays upcoming appointments
3. Patient selects appointment to cancel
4. System displays appointment details
5. Patient confirms cancellation
6. System cancels booking in GP system via GP Connect
7. System displays cancellation confirmation
8. System sends cancellation confirmation to patient
9. Cancelled slot becomes available for rebooking

**Postconditions**:
- Appointment removed from GP system
- Slot available for other patients
- Patient notified of cancellation

**Alternative Flows**:
- **Alt 3a**: Appointment within 2 hours - Warn patient, suggest phone call instead

**Priority**: HIGH

---

#### UC-3: View Appointments

**Actor**: Patient (Arthur)

**Preconditions**:
- Patient is authenticated

**Main Flow**:
1. Patient navigates to "My appointments"
2. System retrieves appointments from GP Connect
3. System displays upcoming appointments with date, time, clinician, location
4. Patient can view details of each appointment

**Postconditions**:
- Patient informed of upcoming appointments

**Priority**: HIGH

---

### Functional Requirements Detail

#### FR-1: NHS Login Authentication

**Description**: The system must authenticate patients using NHS Login at the appropriate identity proofing level (P5 or P9).

**Relates To**: BR-3, UC-1

**Acceptance Criteria**:
- [ ] Given a patient with NHS Login, when they access booking, then they are redirected to NHS Login
- [ ] Given successful NHS Login authentication, when returning to service, then patient identity is established
- [ ] Given NHS Login session expires, when patient takes action, then they are prompted to re-authenticate
- [ ] Given NHS Login unavailable, when patient attempts login, then friendly error message displayed with alternatives

**Data Requirements**:
- **Inputs**: NHS Login token, identity claims
- **Outputs**: Authenticated session, patient NHS number
- **Validations**: Token signature valid, not expired, correct audience

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: NHS Login service availability

---

#### FR-2: Patient Demographics Retrieval

**Description**: The system must retrieve patient demographics from NHS Spine PDS using the authenticated NHS number.

**Relates To**: BR-3, BR-4, UC-1

**Acceptance Criteria**:
- [ ] Given authenticated patient, when session established, then demographics retrieved from PDS
- [ ] Given PDS returns patient record, when displaying to patient, then name and GP practice shown
- [ ] Given PDS unavailable, when demographics needed, then cached data used with staleness indicator
- [ ] Given patient not found in PDS, when booking attempted, then error displayed, suggest contacting practice

**Data Requirements**:
- **Inputs**: NHS Number
- **Outputs**: Patient name, DOB, registered GP practice (ODS code)
- **Validations**: NHS Number format valid, patient record active

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-1 (NHS Login), NHS Spine connectivity

---

#### FR-3: Appointment Slot Retrieval

**Description**: The system must retrieve available appointment slots from the patient's GP practice via GP Connect.

**Relates To**: BR-4, UC-1

**Acceptance Criteria**:
- [ ] Given authenticated patient at registered practice, when viewing availability, then slots retrieved from GP Connect
- [ ] Given slots available, when displayed, then show date, time, clinician name, slot type
- [ ] Given no slots available in date range, when displayed, then inform patient with next available date
- [ ] Given GP Connect unavailable, when slots requested, then display service temporarily unavailable
- [ ] Given slots retrieved, when cached, then cache expires after 5 minutes

**Data Requirements**:
- **Inputs**: ODS code, date range, appointment type filter
- **Outputs**: List of available slots with schedule/slot IDs
- **Validations**: ODS code valid, date range within booking window

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-2, GP Connect Access Record Appointments capability

---

#### FR-4: Appointment Booking

**Description**: The system must create appointment bookings in the GP clinical system via GP Connect.

**Relates To**: BR-1, UC-1

**Acceptance Criteria**:
- [ ] Given patient selects available slot, when confirmed, then booking created in GP system
- [ ] Given booking successful, when response received, then confirmation displayed with reference
- [ ] Given slot no longer available, when booking attempted, then inform patient and return to slot selection
- [ ] Given booking fails, when error occurs, then display friendly error, log details, do not leave partial booking
- [ ] Given booking created, when audit logged, then include patient NHS number, slot ID, timestamp

**Data Requirements**:
- **Inputs**: Slot ID, patient NHS number, booking reason code
- **Outputs**: Booking reference, confirmed appointment details
- **Validations**: Slot still available, patient eligible, reason code valid

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-3, GP Connect Book Appointment capability

---

#### FR-5: Appointment Cancellation

**Description**: The system must allow patients to cancel their appointments, freeing the slot for others.

**Relates To**: BR-2, UC-2

**Acceptance Criteria**:
- [ ] Given patient with booking, when viewing appointments, then cancel option available
- [ ] Given patient cancels, when confirmed, then cancellation sent to GP system via GP Connect
- [ ] Given cancellation successful, when complete, then confirmation displayed and sent to patient
- [ ] Given appointment within 2 hours, when cancel attempted, then warn patient to phone practice
- [ ] Given cancellation fails, when error occurs, then inform patient and suggest phone contact

**Data Requirements**:
- **Inputs**: Appointment ID, cancellation reason (optional)
- **Outputs**: Cancellation confirmation
- **Validations**: Appointment exists, belongs to patient, not already cancelled

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-4

---

#### FR-6: Appointment Viewing

**Description**: The system must display the patient's upcoming appointments retrieved from their GP practice.

**Relates To**: BR-2, UC-3

**Acceptance Criteria**:
- [ ] Given authenticated patient, when viewing appointments, then all future appointments displayed
- [ ] Given appointments retrieved, when displayed, then show date, time, clinician, appointment type
- [ ] Given no upcoming appointments, when displayed, then inform patient with booking option
- [ ] Given appointment details requested, when selected, then show location, preparation instructions

**Data Requirements**:
- **Inputs**: Patient NHS number, ODS code
- **Outputs**: List of appointments with details
- **Validations**: Only patient's own appointments shown

**Priority**: MUST_HAVE

**Complexity**: LOW

**Dependencies**: FR-3

---

#### FR-7: Appointment Reminders

**Description**: The system must send appointment reminder notifications to patients via SMS and email.

**Relates To**: BR-5

**Acceptance Criteria**:
- [ ] Given appointment booked with patient contact details, when 48 hours before, then reminder sent
- [ ] Given appointment booked, when 2 hours before, then reminder sent
- [ ] Given patient opts out, when reminder due, then no reminder sent
- [ ] Given reminder fails to send, when retry exhausted, then log failure for monitoring
- [ ] Given reminder content, when sent, then include date, time, clinician, cancel link

**Data Requirements**:
- **Inputs**: Appointment details, patient contact details, preferences
- **Outputs**: SMS/email notifications
- **Validations**: Contact details valid format, consent for channel

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-4, SMS gateway, email service

---

#### FR-8: Booking Confirmation

**Description**: The system must send booking confirmation to patients via their preferred channel.

**Relates To**: BR-1, UC-1

**Acceptance Criteria**:
- [ ] Given booking successful, when complete, then confirmation sent via email
- [ ] Given patient mobile number available, when booking complete, then SMS confirmation sent
- [ ] Given confirmation content, when sent, then include appointment details and reference
- [ ] Given confirmation sent, when received, then include link to view/cancel booking

**Data Requirements**:
- **Inputs**: Booking details, patient contact details
- **Outputs**: Email/SMS confirmation
- **Validations**: Email/mobile format valid

**Priority**: MUST_HAVE

**Complexity**: LOW

**Dependencies**: FR-4

---

#### FR-9: Welsh Language Support

**Description**: The system must provide Welsh language option for all patient-facing content.

**Relates To**: BR-6

**Acceptance Criteria**:
- [ ] Given user selects Welsh, when viewing any page, then content displayed in Welsh
- [ ] Given Welsh selected, when errors occur, then error messages in Welsh
- [ ] Given Welsh selected, when notifications sent, then sent in Welsh
- [ ] Given language preference, when stored, then remembered for future sessions

**Data Requirements**:
- **Inputs**: Language preference
- **Outputs**: Localised content
- **Validations**: All user-facing strings translated

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: None

---

#### FR-10: Assisted Digital Pathway

**Description**: The system must support assisted digital booking where practice staff book on behalf of patients who cannot self-serve.

**Relates To**: BR-6

**Acceptance Criteria**:
- [ ] Given practice staff authenticated, when assisting patient, then can search for patient
- [ ] Given patient found, when booking, then staff can book appointment on patient's behalf
- [ ] Given assisted booking, when audit logged, then record staff identity and assisted booking flag
- [ ] Given assisted booking, when confirmation due, then confirmation sent to patient not staff

**Data Requirements**:
- **Inputs**: Staff authentication, patient NHS number
- **Outputs**: Booking on behalf of patient
- **Validations**: Staff authorised, patient consents to assisted booking

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-4, staff authentication

---

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-1: Response Time

**Requirement**: System must respond within performance targets under normal load.
- Page load time: < 3 seconds (95th percentile)
- Slot availability retrieval: < 2 seconds (95th percentile)
- Booking confirmation: < 3 seconds (95th percentile)

**Measurement Method**: Application Performance Monitoring (APM) with synthetic monitoring

**Load Conditions**:
- Normal load: 10,000 concurrent users
- Peak load (Monday 8am): 50,000 concurrent users
- Booking transactions: 100 per second at peak

**Priority**: CRITICAL

---

#### NFR-P-2: Throughput

**Requirement**: System must handle Monday morning booking surge without degradation.

**Capacity Requirements**:
- 50,000 concurrent users at peak
- 100 bookings per second sustained
- 10x normal load capacity

**Scalability**: Must scale horizontally to support 3x growth over 2 years

**Priority**: CRITICAL

---

### Availability and Resilience Requirements

#### NFR-A-1: Availability Target

**Requirement**: System must achieve 99.9% uptime during core hours (8am-8pm, 7 days).
- Maximum planned downtime: 4 hours/month (outside core hours)
- Maximum unplanned downtime: 43 minutes/month

**Maintenance Windows**: Sundays 2am-6am only for planned maintenance

**Priority**: CRITICAL

---

#### NFR-A-2: Disaster Recovery

**RPO (Recovery Point Objective)**: 5 minutes - maximum acceptable data loss

**RTO (Recovery Time Objective)**: 1 hour - maximum acceptable downtime

**Backup Requirements**:
- Continuous replication to secondary region
- Daily snapshots retained 30 days
- Geographic backup in separate UK region

**Failover Requirements**:
- Automatic failover to secondary region: YES
- Failover time: < 15 minutes

**Priority**: CRITICAL

---

#### NFR-A-3: Fault Tolerance

**Requirement**: System must gracefully degrade when NHS Spine or GP Connect is unavailable.

**Degraded Mode Behaviour**:
- NHS Spine unavailable: Use cached patient demographics (max 24 hours stale)
- GP Connect unavailable: Display service unavailable, suggest phone booking
- SMS gateway unavailable: Queue reminders for retry, email fallback

**Resilience Patterns Required**:
- [x] Circuit breaker for NHS Spine and GP Connect
- [x] Retry with exponential backoff (max 3 retries)
- [x] Timeout on all network calls (5 seconds default, 30 seconds for GP Connect)
- [x] Bulkhead isolation for booking vs. viewing functions
- [x] Graceful degradation with reduced functionality

**Priority**: CRITICAL

---

### Security Requirements

#### NFR-SEC-1: Authentication

**Requirement**: Patient authentication via NHS Login (OIDC) at P5+ identity proofing level.

**Multi-Factor Authentication**:
- Required for: Initial registration, high-risk actions
- MFA methods: As provided by NHS Login (authenticator app, SMS)

**Session Management**:
- Session timeout: 20 minutes of inactivity
- Absolute session timeout: 4 hours
- Re-authentication required for: Booking changes after session refresh

**Priority**: CRITICAL

---

#### NFR-SEC-2: Authorization

**Requirement**: Patients can only access their own appointments. Staff access role-based with audit.

**Roles**:
- Patient: View/book/cancel own appointments only
- Practice Staff: View/book/cancel for patients at their practice
- System Admin: Configuration only, no patient data access

**Principle**: Least privilege - no access beyond role requirement

**Priority**: CRITICAL

---

#### NFR-SEC-3: Data Encryption

**Requirement**: All patient data encrypted in transit and at rest.

**Encryption Standards**:
- Data in transit: TLS 1.3 only, strong cipher suites (NHS Digital approved)
- Data at rest: AES-256 encryption for all data stores
- Key management: Dedicated key management service, keys rotated annually

**Encryption Scope**:
- [x] Database encryption at rest
- [x] Backup encryption
- [x] Log encryption (patient identifiers pseudonymised in logs)
- [x] Field-level encryption for NHS Number at application layer

**Priority**: CRITICAL

---

#### NFR-SEC-4: Audit Logging

**Requirement**: Comprehensive audit trail for all patient data access.

**Audit Log Contents**:
- Who: User identity (NHS Number for patients, staff ID for staff)
- What: Action performed (view, book, cancel)
- When: Timestamp (UTC, millisecond precision)
- Where: System component
- Why: Request correlation ID
- Result: Success/failure

**Log Retention**: 8 years (NHS Records Management Code)

**Log Integrity**: Tamper-evident logging with cryptographic chaining

**Priority**: CRITICAL

---

#### NFR-SEC-5: Data Protection (UK GDPR)

**Requirement**: Compliance with UK GDPR, health data as special category.

**Data Protection Requirements**:
- [x] Legal basis documented (healthcare provision, explicit consent for reminders)
- [x] Privacy notice accessible from all pages
- [x] Data subject rights: Access, rectification, erasure (where permitted)
- [x] Data breach notification: ICO within 72 hours
- [x] DPIA completed (see ARC-001-DPIA-v1.0.md)

**Data Residency**: All patient data stored in UK only

**Data Retention**: Booking records retained 8 years, then archived

**Priority**: CRITICAL

---

### Compliance Requirements

#### NFR-C-1: NHS Data Security and Protection Toolkit (DSPT)

**Requirement**: Organisation must meet DSPT standards for handling NHS patient data.

**DSPT Assertions**:
- All mandatory assertions completed
- Evidence uploaded annually
- Published on DSPT register

**Priority**: CRITICAL

---

#### NFR-C-2: Clinical Safety (DCB0129/DCB0160)

**Requirement**: Clinical safety compliance as health IT manufacturer and deployer.

**Clinical Safety Deliverables**:
- Clinical Safety Management System
- Hazard Log with all identified hazards
- Clinical Risk Management File
- Clinical Safety Officer sign-off

**Hazard Examples**:
- Patient books wrong appointment type (routine instead of urgent)
- Booking lost, patient believes they have appointment
- Wrong patient record accessed (identity confusion)
- Appointment reminder fails, patient misses appointment

**Priority**: CRITICAL

---

#### NFR-C-3: GDS Service Standard

**Requirement**: Pass GDS Service Standard assessments at Alpha, Beta, and Live phases.

**Service Standard Points** (all 14 required):
1. Understand users and their needs - User research with patients and staff
2. Solve a whole problem - End-to-end booking journey
3. Provide joined up experience - Consistent with NHS App, website
4. Make the service simple - Minimal steps to book
5. Make sure everyone can use it - WCAG 2.2 AA, assisted digital
6. Have a multidisciplinary team - UCD, tech, clinical, IG
7. Use agile ways of working - Sprints, retros, continuous delivery
8. Iterate and improve - Beta feedback incorporation
9. Create a secure service - NHS Login, encryption, DSPT
10. Define success metrics - KPIs, performance dashboard
11. Choose right tools and technology - NHS approved, open standards
12. Make code open - Open source where appropriate
13. Use open standards - FHIR, GP Connect, NHS Login
14. Operate reliable service - 99.9% availability, monitoring

**Priority**: CRITICAL

---

### Usability Requirements

#### NFR-U-1: User Experience

**Requirement**: Service intuitive for users with varying digital literacy.

**UX Standards**:
- Consistent with NHS Design System
- Reading age: Maximum 9 years (NHS standard)
- Mobile-first responsive design
- Maximum 3 clicks to complete booking

**Browser Support**: Chrome, Firefox, Safari, Edge (last 2 versions)

**Priority**: CRITICAL

---

#### NFR-U-2: Accessibility

**Requirement**: WCAG 2.2 Level AA compliance (legal requirement under Equality Act 2010).

**Accessibility Features**:
- [x] Keyboard navigation for all functions
- [x] Screen reader compatibility (NVDA, JAWS, VoiceOver)
- [x] High contrast mode
- [x] Adjustable font sizes (up to 200%)
- [x] No reliance on colour alone
- [x] Focus indicators visible
- [x] Form labels and error messages clear

**Testing**: Automated accessibility testing (axe) in CI/CD + manual testing with assistive technology users

**Accessibility Statement**: Published, reviewed quarterly

**Priority**: CRITICAL

---

#### NFR-U-3: Localisation

**Requirement**: Support for English and Welsh languages.

**Localisation Scope**:
- [x] All UI text translated
- [x] Error messages translated
- [x] Email/SMS content translated
- [x] Date format: dd/MM/yyyy (UK standard)
- [x] Time format: 24-hour with optional 12-hour

**Priority**: MUST_HAVE

---

### Maintainability Requirements

#### NFR-M-1: Observability

**Requirement**: Comprehensive telemetry for monitoring and troubleshooting.

**Telemetry Requirements**:
- **Logging**: Structured JSON logs, centralised aggregation
- **Metrics**: Request rate, error rate, latency (RED metrics)
- **Tracing**: Distributed tracing across NHS integrations
- **Dashboards**: Real-time operational dashboards
- **Alerts**: SLO-based alerting with runbooks

**Priority**: HIGH

---

#### NFR-M-2: Documentation

**Requirement**: Comprehensive documentation for operators and developers.

**Documentation Types**:
- [x] Architecture documentation (C4 model)
- [x] API documentation (OpenAPI 3.0)
- [x] Runbooks for operational procedures
- [x] Incident response playbooks
- [x] User guides

**Priority**: HIGH

---

---

## Integration Requirements

### INT-1: NHS Login Integration

**Purpose**: Patient authentication and identity verification.

**Integration Type**: OIDC (OpenID Connect)

**Data Exchanged**:
- **From NHS Login to System**: ID token with NHS Number, name, identity proofing level
- **From System to NHS Login**: Authentication request, scope

**Authentication**: OIDC client credentials

**SLA**: 99.9% availability, <2 second response time

**Owner**: NHS Login team, NHS Digital

**Priority**: CRITICAL

---

### INT-2: NHS Spine (PDS) Integration

**Purpose**: Patient demographic lookup and GP registration verification.

**Integration Type**: FHIR R4 REST API

**Data Exchanged**:
- **From System to PDS**: Patient lookup by NHS Number
- **From PDS to System**: Patient demographics, registered GP practice

**Authentication**: NHS Spine connection, mutual TLS

**Error Handling**: Cache demographics for 24 hours if PDS unavailable

**SLA**: As per NHS Spine SLA

**Owner**: NHS Spine team, NHS Digital

**Priority**: CRITICAL

---

### INT-3: GP Connect Integration

**Purpose**: Appointment slot availability and booking management.

**Integration Type**: FHIR STU3 REST API (GP Connect specification)

**Capabilities Required**:
- Access Record: Appointments
- Appointment Management: Book, cancel, retrieve

**Data Exchanged**:
- **From System to GP Connect**: Slot queries, booking requests, cancellations
- **From GP Connect to System**: Available slots, booking confirmations

**Authentication**: NHS Spine connection, JWT with practitioner context

**Error Handling**: Circuit breaker, display unavailable message if GP Connect down

**SLA**: Dependent on GP system supplier, typically 99.5%

**Owner**: GP Connect team, NHS Digital; GP system suppliers

**Priority**: CRITICAL

---

### INT-4: Notification Services

**Purpose**: Send appointment confirmations and reminders.

**Integration Type**: REST API

**Channels**:
- Email: Gov.uk Notify
- SMS: Gov.uk Notify

**Data Exchanged**:
- **From System to Notify**: Message content, recipient details
- **From Notify to System**: Delivery status callbacks

**Authentication**: API key

**Error Handling**: Retry with exponential backoff, fallback to alternative channel

**Priority**: HIGH

---

---

## Data Requirements

### Data Entities

#### Entity: Booking

**Description**: Record of an appointment booking made through the system.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique booking reference | Primary key |
| nhs_number | String(10) | Yes | Patient NHS Number | Encrypted, indexed |
| practice_ods_code | String(10) | Yes | GP practice ODS code | Indexed |
| gp_connect_appointment_id | String | Yes | ID in GP system | Indexed |
| appointment_datetime | Timestamp | Yes | Appointment date/time | Indexed |
| clinician_name | String(255) | No | Clinician name | |
| slot_type | String(50) | Yes | Appointment type | |
| status | Enum | Yes | Booking status | ['confirmed', 'cancelled'] |
| created_at | Timestamp | Yes | Booking creation time | Indexed |
| cancelled_at | Timestamp | No | Cancellation time | |
| reminder_sent_48h | Boolean | Yes | 48hr reminder sent | Default false |
| reminder_sent_2h | Boolean | Yes | 2hr reminder sent | Default false |

**Data Volume**:
- Year 1: 5 million bookings
- Year 3: 15 million bookings

**Data Classification**: OFFICIAL (patient identifiable)

**Data Retention**: 8 years, then archived

---

#### Entity: AuditLog

**Description**: Immutable audit record of all patient data access.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique audit ID | Primary key |
| timestamp | Timestamp | Yes | Event timestamp (UTC) | Indexed |
| user_type | Enum | Yes | User type | ['patient', 'staff', 'system'] |
| user_id | String | Yes | User identifier | Indexed |
| action | String(50) | Yes | Action performed | Indexed |
| resource_type | String(50) | Yes | Resource accessed | |
| resource_id | String | No | Resource identifier | |
| request_id | UUID | Yes | Correlation ID | Indexed |
| result | Enum | Yes | Outcome | ['success', 'failure'] |
| error_code | String | No | Error code if failed | |
| ip_address | String | Yes | Client IP | |
| user_agent | String | Yes | Client user agent | |

**Data Volume**:
- Year 1: 100 million records
- Year 3: 500 million records

**Data Classification**: OFFICIAL (may contain patient context)

**Data Retention**: 8 years (immutable)

---

### Data Quality Requirements

**Data Accuracy**: NHS Number validated against PDS before use

**Data Completeness**: All bookings must have NHS Number, practice, appointment datetime

**Data Consistency**: Booking status synchronised with GP system

**Data Timeliness**: PDS data refreshed each session, GP Connect data real-time

---

---

## Constraints and Assumptions

### Technical Constraints

**TC-1**: Must use NHS Login for patient authentication (no custom patient identity)

**TC-2**: Must use GP Connect for appointment management (no direct GP system integration)

**TC-3**: Must comply with NHS Spine connection requirements

**TC-4**: Must host within UK boundaries (data residency)

**TC-5**: Must use Gov.uk Notify for government notifications

---

### Business Constraints

**BC-1**: Beta assessment must pass before public launch

**BC-2**: Clinical Safety sign-off required before each release

**BC-3**: GP practices must opt-in and enable GP Connect

**BC-4**: Service must not reduce access for non-digital patients

---

### Assumptions

**A-1**: NHS Login will maintain current availability SLA (99.9%)

**A-2**: GP Connect will be enabled at sufficient practices for viable service

**A-3**: Gov.uk Notify will support required message volumes

**A-4**: Patients have access to email or mobile phone for confirmations

**A-5**: GP practices will configure appropriate appointment types for online booking

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|-------------------|
| Online booking uptake | 0% | 30% of eligible | 12 months | Analytics |
| Patient satisfaction | N/A | 80% positive | 6 months | Post-booking survey |
| Practice staff time saved | 0 | 40% reduction in booking calls | 12 months | Practice survey |
| DNA rate (online booked) | 8% (phone) | 5% | 12 months | GP system data |

---

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| System availability (core hours) | 99.9% | Uptime monitoring |
| Booking response time (p95) | < 3 seconds | APM |
| Error rate | < 0.1% | Log aggregation |
| Monday peak capacity | 50,000 concurrent users | Load testing |
| Accessibility compliance | WCAG 2.2 AA | Automated + manual testing |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Status | Impact if Delayed |
|------------|-------------|-------|--------|-------------------|
| NHS Login | Patient authentication service | NHS Digital | Available | CRITICAL - Cannot launch |
| GP Connect | Appointment API | NHS Digital | Available | CRITICAL - Cannot launch |
| NHS Spine | Patient demographics | NHS Digital | Available | HIGH - Degraded experience |
| Gov.uk Notify | Notifications | GDS | Available | MEDIUM - No reminders |
| Practice enablement | GP practices enable GP Connect | Practices | In progress | HIGH - Limited coverage |

---

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-1 | GP Connect adoption slower than expected | MEDIUM | HIGH | Early practice engagement, incentives | Product Owner |
| R-2 | NHS Login capacity issues at peak | LOW | CRITICAL | Capacity planning with NHS Login team | Tech Lead |
| R-3 | GP system supplier issues | MEDIUM | HIGH | Multi-supplier testing, escalation paths | Tech Lead |
| R-4 | Clinical safety incident | LOW | CRITICAL | Robust testing, CSO sign-off | Clinical Safety Officer |
| R-5 | GDS assessment failure | MEDIUM | HIGH | Early GDS engagement, mock assessments | Service Owner |

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| TBD | Product Owner | [ ] Approved | | |
| TBD | Clinical Safety Officer | [ ] Approved | | |
| TBD | Enterprise Architect | [ ] Approved | | |
| TBD | Security Lead | [ ] Approved | | |
| TBD | IG Lead | [ ] Approved | | |

---

## Appendices

### Appendix A: Glossary

| Term | Definition |
|------|------------|
| DNA | Did Not Attend - patient misses appointment |
| GP Connect | NHS Digital API standard for GP system integration |
| NHS Login | NHS patient authentication service |
| NHS Spine | National NHS infrastructure including PDS |
| ODS Code | Organisation Data Service code - unique practice identifier |
| PDS | Patient Demographics Service |
| WCAG | Web Content Accessibility Guidelines |

### Appendix B: Reference Documents

- ARC-000-PRIN-v1.0.md - Architecture Principles
- NHS Digital GP Connect Specification
- NHS Login Integration Guide
- GDS Service Standard
- DCB0129/DCB0160 Clinical Safety Standards
- NHS Design System

---

**Generated by**: ArcKit `/arckit.requirements` command
**Generated on**: 2026-01-28
**ArcKit Version**: 1.0.0
**Project**: NHS Doctors Online Appointment System (Project 001)
**AI Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
