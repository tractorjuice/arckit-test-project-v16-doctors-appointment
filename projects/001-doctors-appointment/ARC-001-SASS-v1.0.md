# GDS Service Assessment Preparation Report
# NHS Doctors Online Appointment System

> **Template Status**: Live | **Version**: 1.0.0 | **Command**: `/arckit.service-assessment`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SASS-v1.0 |
| **Document Type** | GDS Service Assessment Preparation Report |
| **Project** | NHS Doctors Online Appointment System (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-01-28 |
| **Last Modified** | 2026-01-28 |
| **Review Cycle** | Per Assessment Phase |
| **Next Review Date** | Before Alpha Assessment |
| **Owner** | Product Owner, NHS Digital |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Product Owner, Delivery Manager, GDS Assessment Team, NHS Digital Director, Enterprise Architect |
| **Assessment Phase** | Alpha |
| **Assessment Date** | Not Yet Scheduled |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-28 | ArcKit AI | Initial creation from `/arckit.service-assessment` command | PENDING | PENDING |

---

## Executive Summary

### Assessment Overview

This document prepares the NHS Doctors Online Appointment System for its **Alpha** GDS Service Standard assessment. It maps existing architecture artifacts as evidence against each of the 14 Service Standard points, identifies gaps in evidence, assigns RAG (Red/Amber/Green) ratings, and provides actionable recommendations for achieving a successful assessment outcome.

### Overall Readiness

**Overall RAG Rating: AMBER**

The project has strong foundations in security (Point 9), data protection, and stakeholder analysis (Point 1), but has notable gaps in user research evidence, operational readiness, and technology documentation that must be addressed before assessment.

### RAG Summary

| Rating | Count | Points |
|--------|-------|--------|
| GREEN | 3 | 5, 9, 13 |
| AMBER | 8 | 1, 2, 3, 4, 6, 7, 10, 12 |
| RED | 3 | 8, 11, 14 |
| **Total** | **14** | |

### Key Strengths

- **Comprehensive security posture** (Point 9): DPIA complete, Secure by Design assessment conducted, NCSC CAF 11/14 objectives achieved, risk register with 16 risks managed under Orange Book methodology
- **Accessibility planning** (Point 5): WCAG 2.2 AA requirements defined, assisted digital pathway designed, Welsh language support specified
- **Open standards commitment** (Point 13): FHIR R4/STU3, NHS Login (OIDC), GP Connect, Gov.uk Notify, SNOMED CT clinical coding

### Critical Gaps

- **No user research evidence** (Points 1, 8): Stakeholder analysis exists but no user research session outputs, usability testing results, or iteration evidence
- **No technology architecture documentation** (Point 11): No HLD, DLD, architecture diagrams, or technology selection records
- **No operational readiness evidence** (Point 14): No runbooks, monitoring dashboards, or incident response testing results
- **No working service or prototype** (Point 8): Cannot demonstrate iteration without something to iterate on

### Key Recommendation

**Prioritise conducting user research sessions with patients and practice staff, and develop a working prototype or proof-of-concept before the Alpha assessment.** These are the most critical gaps that GDS assessors will scrutinise.

---

## Evidence Inventory

### Available ArcKit Artifacts

| Document ID | Title | Type | Version | Relevance |
|-------------|-------|------|---------|-----------|
| ARC-000-PRIN-v1.0 | Architecture Principles | Principles | 1.0 | Foundation - 19 principles including GDS alignment |
| ARC-001-STKE-v1.3 | Stakeholder Drivers & Goals | Stakeholder Analysis | 1.3 | 21 stakeholders, 10 drivers, 7 goals, 4 outcomes |
| ARC-001-REQ-v1.0 | Requirements Specification | Requirements | 1.0 | 7 BRs, 10 FRs, 15+ NFRs, 4 integrations |
| ARC-001-DATA-v1.0 | Data Model | Data Model | 1.0 | 9 entities, 68 attributes, GDPR compliance |
| ARC-001-DPIA-v1.0 | Data Protection Impact Assessment | DPIA | 1.0 | 10 risks, ICO screening, PROCEED recommendation |
| ARC-001-SECD-v1.0 | Secure by Design Assessment | Security | 1.0 | NCSC CAF 11/14, Cyber Essentials in progress |
| ARC-001-RISK-v1.1 | Risk Register | Risk | 1.1 | 16 risks, Orange Book compliant, 4Ts framework |

### Missing Artifacts (Evidence Gaps)

| Expected Artifact | Type Code | Impact on Assessment | Priority |
|-------------------|-----------|---------------------|----------|
| Project Plan | PLAN | Points 6, 7, 8 - No team structure or agile evidence | HIGH |
| Strategic Outline Business Case | SOBC | Point 10 - No success metrics framework | MEDIUM |
| High-Level Design | HLD | Point 11 - No technology architecture | CRITICAL |
| Detailed Design | DLD | Point 11 - No implementation design | HIGH |
| Architecture Diagrams | DIAG | Points 2, 3, 11 - No visual architecture | HIGH |
| Technology Code of Practice | TCOP | Point 12 - No open source assessment | MEDIUM |
| Wardley Maps | WARD | Point 11 - No strategic technology analysis | LOW |
| Research / Vendor Evaluation | EVAL | Point 11 - No build vs buy evidence | MEDIUM |
| Architecture Decision Records | ADR | Point 11 - No decision rationale captured | MEDIUM |
| Traceability Matrix | TRAC | All - No cross-artifact traceability | LOW |
| User Research Outputs | N/A | Points 1, 4, 8 - No research evidence | CRITICAL |
| Prototype / Working Software | N/A | Points 4, 8 - Nothing to demonstrate | CRITICAL |

---

## Service Standard Assessment: All 14 Points

---

### Point 1: Understand users and their needs

> *Develop a deep understanding of users and the problem you're trying to solve for them.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Evidence of user research conducted with real users
- Understanding of different user groups and their needs
- User personas based on research (not assumptions)
- User journey maps showing pain points
- Research plan for Beta phase

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **21 stakeholders identified** with roles, influence, interest, and engagement strategies | ARC-001-STKE-v1.3 Section "Stakeholder Identification" | STRONG |
| **10 stakeholder drivers** analysed (SD-1 to SD-10) with root causes, enablers, and blockers | ARC-001-STKE-v1.3 Section "Stakeholder Drivers Analysis" | STRONG |
| **Power-Interest Grid** mapping stakeholders to engagement strategies | ARC-001-STKE-v1.3 Section "Stakeholder Power-Interest Grid" | MODERATE |
| **4 user personas** (Sarah - Working Parent, Arthur - Elderly Patient, Priya - Receptionist, Dr. Chen - GP) | ARC-001-REQ-v1.0 Section "User Personas" | MODERATE |
| **3 use cases** (Book Routine Appointment, Cancel Appointment, View Appointments) with detailed flows | ARC-001-REQ-v1.0 Section "Use Cases" | MODERATE |
| **Conflict analysis** between stakeholder drivers (Speed vs Safety, National vs Local, Innovation vs Stability) | ARC-001-STKE-v1.3 Section "Conflict Analysis" | STRONG |
| **Vulnerable user groups identified** (elderly, disabled, children, mental health, learning disabilities) | ARC-001-DPIA-v1.0 Section 2.2, ARC-001-STKE-v1.3 | STRONG |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No user research sessions conducted** | CRITICAL - GDS assessors require evidence of research with real users, not documented assumptions | CRITICAL | Conduct minimum 12 user research sessions (6 patients, 3 practice staff, 3 clinicians) before assessment |
| **Personas appear assumption-based** | HIGH - Personas should be derived from research, not created as archetypes | HIGH | Validate and refine personas through user research |
| **No user journey maps** | HIGH - Assessors expect visual journeys showing pain points and opportunities | HIGH | Create as-is and to-be journey maps from research findings |
| **No accessibility research with disabled users** | HIGH - Required for Point 5 evidence | HIGH | Include users of assistive technology in research plan |
| **No evidence of research with diverse demographics** | MEDIUM - GDS expects research across age, ability, digital literacy, ethnicity | MEDIUM | Ensure research sample includes diverse patient groups |

#### What to Present at Assessment

1. Show the comprehensive stakeholder analysis with 21 stakeholders and 10 drivers
2. Present the 4 user personas (but acknowledge they need validation through research)
3. Demonstrate understanding of vulnerable user groups from DPIA analysis
4. Show the conflict analysis between stakeholder needs (speed vs safety)
5. **Present user research plan** for remaining Alpha and Beta phases

#### Recommended Actions

- [ ] **Conduct 12+ user research sessions** with patients, practice staff, and clinicians - Product Owner - Before assessment
- [ ] **Create user journey maps** for booking, cancellation, and viewing flows - User Researcher - Before assessment
- [ ] **Validate personas** against research findings and update - User Researcher - Before assessment
- [ ] **Document research findings** with quotes, insights, and design implications - User Researcher - Before assessment
- [ ] **Develop research plan** for Beta phase showing continued research commitment - User Researcher - Before assessment

---

### Point 2: Solve a whole problem for users

> *Work towards creating a service that solves a whole problem for users, collaborating across organisational boundaries where necessary.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Understanding of the end-to-end problem (not just the digital bit)
- Awareness of other services in the landscape (NHS App, practice websites, phone booking)
- Plan for how the service fits into the broader NHS ecosystem
- Understanding of what happens before and after the digital interaction

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Project scope** clearly defines in-scope and out-of-scope functionality | ARC-001-REQ-v1.0 Section "Project Scope" | MODERATE |
| **NHS integration points** documented (NHS Spine, NHS Login, GP Connect, MESH) | ARC-000-PRIN-v1.0 Principle 4 "NHS Interoperability" | STRONG |
| **Integration requirements** with 4 NHS systems (NHS Login, PDS, GP Connect, Gov.uk Notify) | ARC-001-REQ-v1.0 Section "Integration Requirements" | STRONG |
| **Stakeholder ecosystem** showing 21 stakeholders across NHS, patients, suppliers, regulators | ARC-001-STKE-v1.3 | STRONG |
| **Assisted digital pathway** designed for non-digital users | ARC-001-REQ-v1.0 FR-10 | MODERATE |
| **Phone channel preserved** - system supplements rather than replaces phone booking | ARC-001-STKE-v1.3, ARC-001-DPIA-v1.0 | STRONG |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No service landscape map** | HIGH - Assessors need to see how this fits with NHS App, 111, practice websites | HIGH | Create service landscape diagram showing all booking channels |
| **No architecture diagrams** showing integration points | MEDIUM - Visual representation of NHS ecosystem integration needed | HIGH | Create C4 context diagram showing system boundaries |
| **No end-to-end journey** showing before/after digital interaction | MEDIUM - Need to show what happens at the practice end | MEDIUM | Map the full journey including practice reception workflow |

#### What to Present at Assessment

1. Show understanding of the broader NHS booking landscape (NHS App, 111, phone, walk-in)
2. Demonstrate NHS integration design (Spine, Login, GP Connect)
3. Explain how phone booking is preserved alongside digital
4. Show the assisted digital pathway for non-digital users
5. Explain scope boundaries and why certain things are out of scope

#### Recommended Actions

- [ ] **Create service landscape diagram** showing all appointment booking channels - Enterprise Architect - Before assessment
- [ ] **Create C4 context diagram** showing system boundaries and integrations - Enterprise Architect - Before assessment
- [ ] **Map end-to-end journey** including practice reception workflow - User Researcher - Before assessment

---

### Point 3: Provide a joined up experience across all channels

> *Work towards creating a service that works well across all the channels a user might use.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Plan for how the service works across channels (online, phone, in-person)
- Understanding of how users move between channels
- Consistent experience regardless of channel
- No "digital by default" forcing users to use online

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Multi-channel approach** - online booking supplements phone, not replaces it | ARC-001-STKE-v1.3, ARC-001-REQ-v1.0 | STRONG |
| **Assisted digital pathway** (FR-10) for staff-assisted booking | ARC-001-REQ-v1.0 FR-10 | MODERATE |
| **GP Connect integration** ensures bookings appear in GP system regardless of channel | ARC-001-REQ-v1.0 INT-3 | STRONG |
| **Constraint BC-4**: "Service must not reduce access for non-digital users" | ARC-001-REQ-v1.0 | STRONG |
| **Gov.uk Notify** for SMS/email across channels | ARC-001-REQ-v1.0 INT-4 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No channel shift strategy** | MEDIUM - Need to show planned migration from phone to digital | MEDIUM | Document channel shift plan with metrics |
| **No cross-channel journey maps** | MEDIUM - Show how users move between online and phone | MEDIUM | Map cross-channel scenarios (e.g., book online, query by phone) |

#### What to Present at Assessment

1. Explain that phone booking is preserved as a first-class channel
2. Show how GP Connect ensures consistency between channels
3. Present the assisted digital pathway for staff-assisted booking
4. Demonstrate understanding of why some users will always prefer phone
5. Explain constraint BC-4 protecting non-digital access

#### Recommended Actions

- [ ] **Create cross-channel journey maps** showing phone-to-digital and digital-to-phone scenarios - User Researcher - Before assessment
- [ ] **Document channel shift strategy** with realistic adoption targets - Product Owner - Before assessment

---

### Point 4: Make the service simple to use

> *Build a service that's simple to use so that users succeed first time, without needing to understand the workings of government.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Evidence of a simple, clear design approach
- Use of GOV.UK / NHS Design System patterns
- Content written in plain English
- Evidence from usability testing

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **"Maximum 3 clicks to complete booking"** requirement | ARC-001-REQ-v1.0 NFR-U-1 | MODERATE |
| **Reading age maximum 9 years** (NHS standard) | ARC-001-REQ-v1.0 NFR-U-1 | STRONG |
| **NHS Design System** specified as UX standard | ARC-001-REQ-v1.0 NFR-U-1 | MODERATE |
| **Mobile-first responsive design** | ARC-001-REQ-v1.0 NFR-U-1 | MODERATE |
| **Browser support** defined (Chrome, Firefox, Safari, Edge - last 2 versions) | ARC-001-REQ-v1.0 NFR-U-1 | MODERATE |
| **Booking in under 3 minutes** success criterion | ARC-001-REQ-v1.0 BR-1 | MODERATE |
| **Use case flows** showing step-by-step booking process (14 steps) | ARC-001-REQ-v1.0 UC-1 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No prototype or working software** | CRITICAL - Cannot demonstrate simplicity without something to show | CRITICAL | Build interactive prototype for assessment |
| **No usability testing results** | CRITICAL - Assessors need evidence that real users find it simple | CRITICAL | Conduct usability testing with prototype |
| **No content design work** | HIGH - Plain English content not yet written | HIGH | Engage content designer to write service content |
| **No design mockups or wireframes** | HIGH - Visual evidence of design approach needed | HIGH | Create design mockups using NHS Design System |

#### What to Present at Assessment

1. Show commitment to NHS Design System and GOV.UK patterns
2. Present the "3 clicks to book" design principle
3. Show use case flows demonstrating simplicity intent
4. **Present prototype** (if built before assessment)
5. Explain reading age requirement and content approach

#### Recommended Actions

- [ ] **Build interactive prototype** using NHS Design System - Interaction Designer - Before assessment (CRITICAL)
- [ ] **Conduct usability testing** with 6+ participants using prototype - User Researcher - Before assessment (CRITICAL)
- [ ] **Engage content designer** to write service content at reading age 9 - Content Designer - Before assessment
- [ ] **Create design mockups** showing key screens - Interaction Designer - Before assessment

---

### Point 5: Make sure everyone can use the service

> *Provide a service that everyone can use, including disabled people and people with other legally protected characteristics.*

#### RAG Rating: GREEN

#### What GDS Assessors Expect at Alpha

- Clear commitment to WCAG 2.2 AA
- Understanding of different user accessibility needs
- Plan for accessibility testing
- Assisted digital support pathway
- Accessibility statement plan

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **WCAG 2.2 Level AA** mandated as legal requirement | ARC-001-REQ-v1.0 NFR-U-2, ARC-000-PRIN-v1.0 Principle 13 | STRONG |
| **Comprehensive accessibility features** specified (keyboard nav, screen reader, high contrast, font size, focus indicators, form labels) | ARC-001-REQ-v1.0 NFR-U-2 | STRONG |
| **Welsh language support** (FR-9) with full translation | ARC-001-REQ-v1.0 FR-9 | STRONG |
| **Assisted digital pathway** (FR-10) for staff-assisted booking | ARC-001-REQ-v1.0 FR-10 | STRONG |
| **Vulnerable groups identified** in DPIA (elderly, disabled, children, learning disabilities, mental health) | ARC-001-DPIA-v1.0 Section 2.2 | STRONG |
| **Accessibility testing plan** (automated axe in CI/CD + manual with assistive technology users) | ARC-001-REQ-v1.0 NFR-U-2 | STRONG |
| **Screen reader testing** with NVDA, JAWS, VoiceOver specified | ARC-001-REQ-v1.0 NFR-U-2 | MODERATE |
| **NHS-specific accessibility** (large text, BSL video, Easy Read) in architecture principles | ARC-000-PRIN-v1.0 Principle 13 | MODERATE |
| **Phone channel preserved** for users who cannot or choose not to use digital | ARC-001-REQ-v1.0 BC-4 | STRONG |
| **Equality Act 2010** compliance cited as legal requirement | ARC-000-PRIN-v1.0 Principle 13, ARC-001-REQ-v1.0 NFR-U-2 | STRONG |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No accessibility audit results** | MEDIUM - Planning is strong but no test results yet (acceptable at Alpha) | MEDIUM | Begin accessibility testing when prototype available |
| **No testing with assistive technology users** | MEDIUM - Plan exists but not yet executed (acceptable at Alpha) | MEDIUM | Include in Beta research plan |

#### What to Present at Assessment

1. Show comprehensive WCAG 2.2 AA requirements and accessibility features list
2. Present the assisted digital pathway for non-digital users
3. Show Welsh language support commitment
4. Present vulnerable user analysis from DPIA
5. Explain phone channel preservation (constraint BC-4)
6. Show accessibility testing plan (automated + manual)
7. Reference Equality Act 2010 compliance commitment

#### Recommended Actions

- [ ] **Begin accessibility testing** when prototype available - Accessibility Lead - Before Beta
- [ ] **Plan accessibility research** with assistive technology users for Beta - User Researcher - Before assessment
- [ ] **Draft accessibility statement** template - Content Designer - Before Beta

---

### Point 6: Have a multidisciplinary team

> *Put in place a sustainable multidisciplinary team that can design, build, and operate the service.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Evidence of a multidisciplinary team with appropriate skills
- Team includes user researchers, designers, developers, and subject matter experts
- Team has appropriate clinical and security expertise for NHS context

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **RACI matrix** defining roles across 13 decision types including clinical, security, accessibility | ARC-001-STKE-v1.3 Section "Decision Authority Matrix" | STRONG |
| **Roles identified**: Product Owner, Clinical Safety Officer, Enterprise Architect, Security Lead, IG Lead, User Researcher, Accessibility Lead | ARC-001-STKE-v1.3, ARC-001-REQ-v1.0 | MODERATE |
| **Escalation path**: Product Owner -> NHS Digital Director -> NHS England Director -> Minister | ARC-001-STKE-v1.3 Section "Escalation Path" | MODERATE |
| **Specialist roles**: Clinical Safety Officer with halt authority, Security Lead, IG Lead, DPO | ARC-001-SECD-v1.0, ARC-001-RISK-v1.1 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No team roster or org chart** | HIGH - Assessors want to see named team members with roles | HIGH | Create team roster with named individuals |
| **No project plan** showing team structure | HIGH - No PLAN artifact exists | HIGH | Document team structure, capacity, and reporting |
| **No evidence of user research capability** | HIGH - User researcher mentioned but no evidence of activity | HIGH | Demonstrate active user researcher in team |
| **No content designer identified** | MEDIUM - Content design is critical for NHS services | MEDIUM | Recruit or assign content designer |
| **No interaction/service designer identified** | MEDIUM - Design capability not evidenced | MEDIUM | Recruit or assign interaction designer |

#### What to Present at Assessment

1. Show the RACI matrix with decision authority across domains
2. Present the team structure with named individuals (when available)
3. Highlight specialist NHS roles (CSO, Security Lead, IG Lead)
4. Show how clinical safety expertise is embedded in the team
5. Present plans for user research and design capability

#### Recommended Actions

- [ ] **Create team roster** with named individuals, roles, and FTE allocation - Delivery Manager - Before assessment (HIGH)
- [ ] **Confirm user researcher** is active in team with research schedule - Product Owner - Before assessment (HIGH)
- [ ] **Recruit content designer** and interaction designer - Delivery Manager - Before assessment
- [ ] **Document team ways of working** including standup, sprint review, retro cadence - Delivery Manager - Before assessment

---

### Point 7: Use agile ways of working

> *Create the service using agile, iterative, user-centred methods.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Evidence of agile methodology in use
- Sprint cadence, ceremonies, and artifacts
- Backlog management with user stories
- Demonstrate learning from each iteration

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Agile/DevOps** methodology stated for development | ARC-001-SECD-v1.0 Section 4.1 | WEAK |
| **GDS Agile phases** referenced (Discovery, Alpha, Beta, Live) | CLAUDE.md workflow | MODERATE |
| **NFR-C-3**: "Use agile ways of working - Sprints, retros, continuous delivery" | ARC-001-REQ-v1.0 NFR-C-3 | WEAK |
| **Architecture Principle 19**: "Continuous Deployment with NHS Change Control" | ARC-000-PRIN-v1.0 Principle 19 | MODERATE |
| **Sprint cadence** implied through CAB approval process | ARC-000-PRIN-v1.0 Principle 19 | WEAK |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No evidence of agile practices in use** | HIGH - Stating agile is different from demonstrating it | HIGH | Document sprint history, velocity, and retrospective outcomes |
| **No backlog or user stories** | HIGH - No prioritised backlog artifact exists | HIGH | Create and share product backlog |
| **No sprint review/retrospective outputs** | HIGH - Key agile ceremony evidence needed | HIGH | Document sprint ceremonies and outputs |
| **No project plan** with agile milestones | MEDIUM - No PLAN artifact showing delivery phases | MEDIUM | Create lightweight delivery roadmap |

#### What to Present at Assessment

1. Show evidence of agile ceremonies (stand-ups, sprint reviews, retrospectives)
2. Present product backlog with prioritised user stories
3. Show sprint cadence and how decisions are made
4. Demonstrate how architecture artifacts were iterated (e.g., STKE v1.0 to v1.3)
5. Show how user feedback drives backlog prioritisation

#### Recommended Actions

- [ ] **Document sprint history** with key decisions and learning - Delivery Manager - Before assessment (HIGH)
- [ ] **Create product backlog** with user stories derived from requirements - Product Owner - Before assessment (HIGH)
- [ ] **Record retrospective outcomes** showing team learning - Scrum Master - Before assessment
- [ ] **Create lightweight delivery roadmap** showing Alpha, Beta, Live milestones - Delivery Manager - Before assessment

---

### Point 8: Iterate and improve frequently

> *Make sure you have the capacity, resources, and technical flexibility to iterate and improve the service frequently.*

#### RAG Rating: RED

#### What GDS Assessors Expect at Alpha

- Evidence of prototyping and iteration
- Show how user research has changed the design
- Demonstrate technical flexibility to make changes
- Evidence of learning from testing and research

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Document iteration evidence** - Stakeholder analysis iterated from v1.0 to v1.3 (4 versions with clear change rationale) | ARC-001-STKE revision history | MODERATE |
| **Risk register iteration** from v1.0 to v1.1 with format improvements | ARC-001-RISK revision history | WEAK |
| **Architecture Principle 8**: "Iterate and improve frequently" listed in GDS Service Standard mapping | ARC-000-PRIN-v1.0 Principle 14 | WEAK |
| **CI/CD pipeline** designed for continuous deployment | ARC-000-PRIN-v1.0 Principle 19 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No prototype or working software to iterate on** | CRITICAL - Cannot demonstrate iteration without a product | CRITICAL | Build and iterate on a prototype before assessment |
| **No evidence of design changes based on research** | CRITICAL - Core of Point 8 is showing learning-driven change | CRITICAL | Conduct research, design, test, iterate cycle |
| **No A/B testing or design comparison** | MEDIUM - Assessors like to see alternative approaches explored | MEDIUM | Document design decisions with alternatives considered |
| **Document iterations are governance, not user-driven** | MEDIUM - STKE versions changed format, not based on user feedback | MEDIUM | Show user-driven iteration examples |

#### What to Present at Assessment

1. Show the iteration cycle planned for the service
2. Present technical flexibility (containerised, IaC, CI/CD) enabling rapid change
3. Show how architecture documents have been iterated (limited evidence)
4. **Present prototype iteration evidence** (if available before assessment)
5. Show the feedback mechanisms planned for Beta

#### Recommended Actions

- [ ] **Build prototype and iterate** based on user research findings - Design Team - Before assessment (CRITICAL)
- [ ] **Document design decisions** with alternatives explored and rationale - Design Team - Before assessment (CRITICAL)
- [ ] **Show at least 2 iterations** of a key user journey based on testing - Design Team - Before assessment
- [ ] **Plan Beta iteration process** including feedback loops and metrics - Product Owner - Before assessment

---

### Point 9: Create a secure service which protects users' privacy

> *Evaluate what data and information the service will be collecting, storing, and providing. Put appropriate legal, privacy, and security measures in place.*

#### RAG Rating: GREEN

#### What GDS Assessors Expect at Alpha

- Threat assessment and risk management approach
- Data protection approach (DPIA if needed)
- Understanding of data the service handles
- Security approach appropriate to the risk
- Privacy considerations embedded in design

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Complete DPIA** with 10 risks assessed, all mitigated to MEDIUM or LOW | ARC-001-DPIA-v1.0 | STRONG |
| **Secure by Design assessment** - NCSC CAF 11/14 objectives achieved | ARC-001-SECD-v1.0 | STRONG |
| **Comprehensive data model** with 9 entities, 68 attributes, PII inventory (12 PII attributes across 6 entities) | ARC-001-DATA-v1.0 | STRONG |
| **Special category data identified** - booking reason codes as health data under Article 9 | ARC-001-DPIA-v1.0, ARC-001-DATA-v1.0 | STRONG |
| **Encryption**: AES-256 at rest, TLS 1.3 in transit, field-level NHS Number encryption | ARC-001-SECD-v1.0, ARC-001-DATA-v1.0 | STRONG |
| **Risk register**: 16 risks including 5 technology/data risks, managed under Orange Book | ARC-001-RISK-v1.1 | STRONG |
| **Architecture Principle 5**: "Security by Design (NON-NEGOTIABLE)" with zero-trust pillars | ARC-000-PRIN-v1.0 Principle 5 | STRONG |
| **NHS Login** authentication at P5/P9 identity proofing | ARC-001-REQ-v1.0 NFR-SEC-1 | STRONG |
| **RBAC** with least privilege (patients own data only, staff practice only) | ARC-001-REQ-v1.0 NFR-SEC-2 | STRONG |
| **Audit logging** with 8-year retention, tamper-evident with cryptographic chaining | ARC-001-REQ-v1.0 NFR-SEC-4, ARC-001-DATA-v1.0 E-006 | STRONG |
| **UK-only data residency** - Azure UK South primary, UK West DR | ARC-001-SECD-v1.0, ARC-001-DATA-v1.0 | STRONG |
| **OWASP Top 10** all addressed in SDLC | ARC-001-SECD-v1.0 Section 4.1 | STRONG |
| **DevSecOps** with SAST, SCA, container scanning, IaC scanning, secrets scanning | ARC-001-SECD-v1.0 Section 4.2 | STRONG |
| **Cyber Essentials Plus** targeting before Beta | ARC-001-SECD-v1.0 Section 2 | MODERATE |
| **ICO consultation not required** - all residual risks MEDIUM or LOW | ARC-001-DPIA-v1.0 Section 7 | STRONG |
| **Data subject rights** implementation documented (SAR, rectification, erasure, portability) | ARC-001-DPIA-v1.0 Section 12 | STRONG |
| **Data retention schedule** defined per entity (5 minutes to 8 years) | ARC-001-DATA-v1.0 | STRONG |
| **Consent management** with granular opt-in, timestamp, version tracking | ARC-001-DATA-v1.0 E-007, ARC-000-PRIN-v1.0 Principle 9 | STRONG |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **Penetration testing not completed** | MEDIUM at Alpha (CRITICAL for Beta/Live) - Noted as gap but acceptable at Alpha stage | HIGH | Commission CHECK-approved pen test before Beta |
| **SIRO approval pending** for 4 risks exceeding appetite | MEDIUM - Governance in progress | MEDIUM | Obtain SIRO approval before assessment |
| **DSPT self-assessment not completed** | MEDIUM - Required before Live | MEDIUM | Begin DSPT self-assessment |

#### What to Present at Assessment

1. Present the complete DPIA with 10 risks, all mitigated to acceptable levels
2. Show the Secure by Design assessment with NCSC CAF 11/14
3. Present the data model with PII inventory and encryption approach
4. Show special category health data handling with Article 9(2)(h) legal basis
5. Demonstrate security architecture (NHS Login, RBAC, encryption, audit logging)
6. Present the risk register with security risks and mitigation plans
7. Show DevSecOps pipeline with security scanning
8. Explain UK-only data residency commitment

#### Recommended Actions

- [ ] **Commission penetration testing** before Beta - Security Lead - Before Beta
- [ ] **Obtain SIRO approval** for risks exceeding appetite - Security Lead - Before assessment
- [ ] **Begin DSPT self-assessment** - IG Lead - Before Beta

---

### Point 10: Define what success looks like and publish performance data

> *Work out what success looks like for your service and identify metrics which will tell you what's working and what can be improved.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Defined KPIs and success metrics
- Plan for measuring and publishing performance data
- Understanding of the 4 mandatory KPIs (cost per transaction, user satisfaction, completion rate, digital take-up)

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Business success metrics** defined (30% uptake, 80% satisfaction, 40% phone reduction, 5% DNA rate) | ARC-001-REQ-v1.0 Section "Success Criteria and KPIs" | STRONG |
| **Technical success metrics** defined (99.9% availability, <3s response, <0.1% error rate, 50K concurrent) | ARC-001-REQ-v1.0 Section "Technical Success Metrics" | STRONG |
| **7 stakeholder goals** with measurable outcomes (G-1 to G-7) | ARC-001-STKE-v1.3 Section "Driver-to-Goal Mapping" | STRONG |
| **4 outcomes** with KPIs, baselines, targets, measurement methods | ARC-001-STKE-v1.3 Section "Goal-to-Outcome Mapping" | STRONG |
| **Leading and lagging indicators** defined for each outcome | ARC-001-STKE-v1.3 Outcomes O-1 to O-4 | MODERATE |
| **Timeline phasing** for outcome achievement (Beta, Early Live, Full Live, Sustainment) | ARC-001-STKE-v1.3 Outcome O-1 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **4 mandatory GDS KPIs not explicitly mapped** | HIGH - GDS requires cost per transaction, user satisfaction, completion rate, digital take-up | HIGH | Map existing metrics to 4 mandatory GDS KPIs |
| **No performance dashboard** designed | MEDIUM - Plan for publishing data needed | MEDIUM | Design performance dashboard approach |
| **No SOBC** with cost-benefit analysis | MEDIUM - No formal business case to derive cost per transaction | MEDIUM | Generate SOBC or calculate cost per transaction estimate |
| **No analytics implementation plan** | MEDIUM - How will metrics be collected? | MEDIUM | Document analytics approach |

#### What to Present at Assessment

1. Show comprehensive business success metrics (uptake, satisfaction, phone reduction, DNA rate)
2. Present technical performance targets (availability, response time, error rate)
3. Show stakeholder outcome framework with leading/lagging indicators
4. Map to 4 mandatory GDS KPIs
5. Present plan for performance dashboard and data publication

#### Recommended Actions

- [ ] **Map to 4 mandatory GDS KPIs** (cost per transaction, satisfaction, completion rate, digital take-up) - Product Owner - Before assessment (HIGH)
- [ ] **Design performance dashboard** approach - Product Owner - Before assessment
- [ ] **Document analytics approach** for collecting metrics - Technical Lead - Before assessment
- [ ] **Plan for publishing performance data** on GOV.UK dashboard - Product Owner - Before Beta

---

### Point 11: Choose the right tools and technology

> *Choose tools and technology that let you create a high quality service in a cost effective way.*

#### RAG Rating: RED

#### What GDS Assessors Expect at Alpha

- Technology choices made and justified
- Open, interoperable technology stack
- Understanding of hosting and deployment approach
- Evidence that technology choices support the team's capability

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Cloud hosting**: Azure UK South (primary), UK West (DR) | ARC-001-SECD-v1.0 Section 5, ARC-001-DATA-v1.0 | MODERATE |
| **Database**: PostgreSQL 15+ recommended with rationale | ARC-001-DATA-v1.0 Implementation Guidance | MODERATE |
| **Containerised deployment** with IaC (Terraform) | ARC-001-SECD-v1.0 Section 4.2 | MODERATE |
| **NHS Digital approved integrations** (NHS Login OIDC, GP Connect FHIR, NHS Spine FHIR R4) | ARC-001-REQ-v1.0 Integration Requirements | STRONG |
| **Gov.uk Notify** for notifications | ARC-001-REQ-v1.0 INT-4 | STRONG |
| **Open standards**: FHIR R4, FHIR STU3, OIDC, SNOMED CT, dm+d | ARC-000-PRIN-v1.0 Principle 4 | STRONG |
| **19 architecture principles** guiding technology decisions | ARC-000-PRIN-v1.0 | MODERATE |
| **DevSecOps pipeline** with CI/CD, SAST, SCA, IaC scanning | ARC-001-SECD-v1.0 Section 4.2 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No High-Level Design (HLD)** | CRITICAL - No architecture documentation showing technology stack, components, or patterns | CRITICAL | Create HLD with component architecture and technology selections |
| **No architecture diagrams** | CRITICAL - No C4, deployment, or integration diagrams | CRITICAL | Create C4 model (context, container, component diagrams) |
| **No Architecture Decision Records (ADRs)** | HIGH - No documented rationale for technology choices | HIGH | Document key ADRs (cloud provider, database, framework, hosting) |
| **No build vs buy analysis** | HIGH - No research artifact exists | HIGH | Document build vs buy decisions with rationale |
| **No Detailed Design (DLD)** | MEDIUM - Acceptable gap at Alpha | MEDIUM | Plan DLD for Beta phase |
| **Programming language/framework not stated** | HIGH - No mention of application language (Node.js? Python?) | HIGH | Document application technology stack |

#### What to Present at Assessment

1. Show architecture principles guiding technology decisions
2. Present NHS-mandated technology choices (NHS Login, GP Connect, NHS Spine)
3. Show cloud hosting approach (Azure UK) with DR
4. Present database selection rationale (PostgreSQL)
5. **Show architecture diagrams** (if created before assessment)
6. Explain open standards approach (FHIR, OIDC, SNOMED CT)

#### Recommended Actions

- [ ] **Create High-Level Design** with technology stack, component architecture, deployment model - Enterprise Architect - Before assessment (CRITICAL)
- [ ] **Create C4 architecture diagrams** (context, container, component) - Enterprise Architect - Before assessment (CRITICAL)
- [ ] **Document ADRs** for key decisions (cloud, database, framework, hosting) - Enterprise Architect - Before assessment (HIGH)
- [ ] **Document full technology stack** including application language/framework - Technical Lead - Before assessment (HIGH)
- [ ] **Conduct build vs buy analysis** for key components - Enterprise Architect - Before assessment

---

### Point 12: Make new source code open

> *Make all new source code open and reusable, and publish it under appropriate licences.*

#### RAG Rating: AMBER

#### What GDS Assessors Expect at Alpha

- Plan for making source code open
- Understanding of what can and cannot be open
- Appropriate licence chosen

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **Architecture Principle 14**: "Make new source code open" listed in GDS Service Standard mapping | ARC-000-PRIN-v1.0 Principle 14 | WEAK |
| **NFR-C-3**: "Make code open - Open source where appropriate" | ARC-001-REQ-v1.0 NFR-C-3 | WEAK |
| **SBOM** (Software Bill of Materials) generated in CI/CD pipeline | ARC-001-SECD-v1.0 Section 7.2 | MODERATE |
| **License compliance checks** automated in pipeline | ARC-001-SECD-v1.0 Section 7.2 | MODERATE |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No open source strategy** | HIGH - Need to articulate what will be open, what won't, and why | HIGH | Document open source strategy with rationale |
| **No repository or code available** | MEDIUM - Acceptable at Alpha, but plan needed | MEDIUM | Create public repository with appropriate licence |
| **No TCOP assessment** | MEDIUM - Technology Code of Practice assessment not conducted | MEDIUM | Consider generating TCOP artifact |
| **Licence not chosen** | MEDIUM - Need to select appropriate open source licence | MEDIUM | Select licence (MIT, Apache 2.0, or OGL recommended) |

#### What to Present at Assessment

1. State commitment to open source code
2. Explain what will and won't be open (and why - e.g., security configurations)
3. Show licence compliance checking in CI/CD
4. Present plan for public repository
5. Explain SBOM generation for dependency transparency

#### Recommended Actions

- [ ] **Document open source strategy** stating what will be open and what won't - Technical Lead - Before assessment (HIGH)
- [ ] **Select licence** (recommend MIT or OGL v3.0 for NHS) - Technical Lead - Before assessment
- [ ] **Create public repository** on GitHub (can be empty initially) - Technical Lead - Before assessment
- [ ] **Plan code publication** timeline - Technical Lead - Before Beta

---

### Point 13: Use and contribute to open standards, common components and patterns

> *Build on open standards and common components and patterns from GOV.UK and other parts of government.*

#### RAG Rating: GREEN

#### What GDS Assessors Expect at Alpha

- Use of established NHS/government standards and components
- Use of GOV.UK Design System / NHS Design System
- Use of government common components (Notify, Pay, etc.)
- Contributing back where possible

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **FHIR R4** for NHS Spine PDS integration | ARC-001-REQ-v1.0 INT-2 | STRONG |
| **FHIR STU3** for GP Connect integration | ARC-001-REQ-v1.0 INT-3 | STRONG |
| **NHS Login (OIDC)** for patient authentication | ARC-001-REQ-v1.0 INT-1, NFR-SEC-1 | STRONG |
| **GP Connect** standard for appointment management | ARC-001-REQ-v1.0 INT-3 | STRONG |
| **Gov.uk Notify** for notifications | ARC-001-REQ-v1.0 INT-4 | STRONG |
| **SNOMED CT** for clinical coding (booking reason) | ARC-000-PRIN-v1.0 Principle 4, ARC-001-DATA-v1.0 | STRONG |
| **NHS Data Dictionary** for terminology | ARC-000-PRIN-v1.0 Principle 4 | MODERATE |
| **NHS Design System** specified for UI | ARC-001-REQ-v1.0 NFR-U-1 | MODERATE |
| **Architecture Principle 4**: "NHS Interoperability (MANDATORY)" prohibiting proprietary integration | ARC-000-PRIN-v1.0 Principle 4 | STRONG |
| **Architecture Principle 10**: "Loose Coupling with NHS Systems" using published APIs | ARC-000-PRIN-v1.0 Principle 10 | STRONG |
| **NHS Number** as primary patient identifier (no local IDs) | ARC-000-PRIN-v1.0 Principle 4 | STRONG |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No contribution plan** | LOW - Assessors like to see contribution back to NHS/GOV.UK patterns | LOW | Document planned contributions |

#### What to Present at Assessment

1. Show comprehensive use of NHS open standards (FHIR, GP Connect, NHS Login, SNOMED CT)
2. Present Gov.uk Notify integration for common component reuse
3. Show NHS Design System commitment
4. Present Architecture Principle 4 mandating NHS standards
5. Explain prohibition on proprietary integration approaches
6. Show NHS Number as universal identifier following NHS standards

#### Recommended Actions

- [ ] **Document contributions plan** - contributions to NHS patterns, GP Connect specification feedback, etc. - Technical Lead - Before Beta

---

### Point 14: Operate a reliable service

> *Minimise service downtime and have a plan to deal with it when it does happen.*

#### RAG Rating: RED

#### What GDS Assessors Expect at Alpha

- Plan for how the service will be operated
- Understanding of availability requirements
- Incident management and support approach
- Monitoring and alerting strategy

#### Evidence Available

| Evidence | Source | Strength |
|----------|--------|----------|
| **99.9% availability target** during core hours (8am-8pm) | ARC-001-REQ-v1.0 NFR-A-1 | MODERATE |
| **RTO 1 hour, RPO 5 minutes** | ARC-001-REQ-v1.0 NFR-A-2 | MODERATE |
| **Fault tolerance** requirements with circuit breakers, retry, graceful degradation | ARC-001-REQ-v1.0 NFR-A-3 | MODERATE |
| **Multi-region DR** (Azure UK South + UK West) with automatic failover | ARC-001-SECD-v1.0, ARC-001-DATA-v1.0 | MODERATE |
| **Observability requirements** (logging, metrics, tracing, dashboards, alerts) | ARC-001-REQ-v1.0 NFR-M-1, ARC-000-PRIN-v1.0 Principle 6 | MODERATE |
| **Incident response plan** at NHS Digital level (72-hour ICO notification) | ARC-001-SECD-v1.0 D1 | MODERATE |
| **Backup strategy** (continuous replication, daily snapshots, immutable backups) | ARC-001-SECD-v1.0 Section 8 | MODERATE |
| **Monday peak capacity** planning (50,000 concurrent, 10x surge) | ARC-001-REQ-v1.0 NFR-P-2 | MODERATE |
| **Maintenance windows** defined (Sundays 2am-6am) | ARC-001-REQ-v1.0 NFR-A-1 | WEAK |

#### Gaps Identified

| Gap | Impact | Priority | Recommendation |
|-----|--------|----------|----------------|
| **No operational runbooks** | CRITICAL - No documented procedures for operating the service | CRITICAL | Create runbooks for common operational scenarios |
| **No monitoring dashboards** designed | HIGH - Requirements exist but no implementation plan | HIGH | Design monitoring dashboard with key operational metrics |
| **No support model** defined | HIGH - Who provides L1/L2/L3 support? | HIGH | Define support model and on-call rota |
| **No incident response tested** for this service | HIGH - NHS Digital plan exists but not service-specific | HIGH | Conduct tabletop incident exercise |
| **No load testing results** | HIGH - Capacity planned but not validated | HIGH | Plan load testing for Beta phase |
| **No SLOs/SLIs defined** | MEDIUM - Requirements reference SLOs but none formally defined | MEDIUM | Define SLOs with error budgets |
| **Project-specific IR runbooks** noted as gap in SECD | HIGH - Secure by Design assessment identifies this gap | HIGH | Complete service-specific runbooks |

#### What to Present at Assessment

1. Show availability, RTO, RPO targets
2. Present fault tolerance design (circuit breakers, graceful degradation)
3. Show multi-region DR architecture
4. Present observability requirements (logging, metrics, tracing)
5. Show backup and recovery strategy
6. Present Monday peak capacity planning
7. **Acknowledge operational readiness gaps** and present plan for Beta

#### Recommended Actions

- [ ] **Create operational runbooks** for key scenarios (deployment, rollback, incident, failover) - Technical Lead - Before Beta (CRITICAL)
- [ ] **Design monitoring dashboards** with RED metrics (rate, error, duration) - Technical Lead - Before assessment (HIGH)
- [ ] **Define support model** with L1/L2/L3 responsibilities and on-call rota - Delivery Manager - Before Beta (HIGH)
- [ ] **Define SLOs/SLIs** with error budgets - Technical Lead - Before Beta
- [ ] **Plan load testing** for Beta phase - Technical Lead - Before assessment
- [ ] **Conduct tabletop incident exercise** - Security Lead - Before Beta

---

## Assessment Day Guidance

### Panel Composition

**Expected assessors:**
- Lead assessor (service design background)
- Technical assessor
- User research assessor
- Design assessor

**NHS-specific**: May include assessor with health domain experience given special category data and clinical safety requirements.

### Presentation Strategy

#### Opening (10 minutes)

1. **Service overview**: NHS Doctors Online Appointment Booking System - enabling patients to book, view, and cancel GP appointments online
2. **Problem statement**: Monday 8am phone chaos, working patients unable to call, health inequity in appointment access
3. **User groups**: Patients (including elderly, disabled, working parents), GP practice staff, clinicians
4. **Phase**: Alpha - exploring the problem space, prototyping solutions, validating with users

#### Body (45 minutes - structured around 14 points)

**Lead with strengths:**
- Point 9 (Security) - Comprehensive DPIA, Secure by Design assessment, NCSC CAF compliance
- Point 5 (Accessibility) - WCAG 2.2 AA, assisted digital, Welsh language, phone preservation
- Point 13 (Open Standards) - FHIR, GP Connect, NHS Login, Gov.uk Notify, SNOMED CT

**Address honestly:**
- Point 1 (User needs) - Strong stakeholder analysis, acknowledge research sessions needed
- Point 10 (Success metrics) - Comprehensive KPI framework, map to 4 mandatory GDS metrics

**Acknowledge gaps with plans:**
- Points 8, 11, 14 - Present clear plans for Beta phase with milestones

#### Closing (5 minutes)

1. Key risks and how you're managing them (reference risk register)
2. Beta plans and timeline
3. Team commitment to user-centred design

### Common Questions to Prepare For

| Question | Suggested Response | Evidence Reference |
|----------|-------------------|-------------------|
| "How many user research sessions have you conducted?" | State actual number; show research plan; present stakeholder analysis depth | ARC-001-STKE-v1.3 |
| "How do you handle users who can't use the digital service?" | Phone booking preserved; assisted digital pathway (FR-10); constraint BC-4 | ARC-001-REQ-v1.0 |
| "What happens if GP Connect is unavailable?" | Circuit breakers, graceful degradation, user message to call practice | ARC-001-REQ-v1.0 NFR-A-3 |
| "How do you protect health data?" | AES-256, TLS 1.3, NHS Login P5/P9, RBAC, audit logging, DPIA completed | ARC-001-DPIA-v1.0, ARC-001-SECD-v1.0 |
| "What are your success metrics?" | 30% uptake, 80% satisfaction, 40% phone reduction, 99.9% availability | ARC-001-REQ-v1.0, ARC-001-STKE-v1.3 |
| "How have you iterated based on research?" | Document iteration evidence; show design changes from testing | Need to generate before assessment |
| "What technology have you chosen and why?" | Azure UK, PostgreSQL, FHIR, containerised; show ADRs | ARC-001-DATA-v1.0, ARC-001-SECD-v1.0 |
| "How does this fit with the NHS App?" | Separate but complementary; GP Connect ensures consistency; scope boundaries clear | ARC-001-REQ-v1.0 |
| "What clinical safety governance is in place?" | CSO appointed with halt authority; DCB0129/0160 compliance; hazard log | ARC-001-RISK-v1.1 R-002 |
| "How do you handle Welsh language?" | Full Welsh translation (FR-9); language preference stored; notifications in Welsh | ARC-001-REQ-v1.0 FR-9 |

### Evidence Portfolio

**Bring to assessment:**

| Evidence Type | Document | Key Section |
|---------------|----------|-------------|
| User needs | ARC-001-STKE-v1.3 | Stakeholder Drivers SD-1 to SD-10, User Personas |
| User needs | User research findings | Findings from sessions (NEEDED) |
| Accessibility | ARC-001-REQ-v1.0 | NFR-U-2, FR-9, FR-10 |
| Security | ARC-001-DPIA-v1.0 | Full DPIA with 10 risks mitigated |
| Security | ARC-001-SECD-v1.0 | NCSC CAF assessment, OWASP Top 10 |
| Risk management | ARC-001-RISK-v1.1 | 16 risks with Orange Book governance |
| Data model | ARC-001-DATA-v1.0 | 9 entities, PII inventory, retention schedule |
| Principles | ARC-000-PRIN-v1.0 | 19 principles including GDS alignment |
| Requirements | ARC-001-REQ-v1.0 | BRs, FRs, NFRs, integrations |
| Success metrics | ARC-001-STKE-v1.3 | Goals G-1 to G-7, Outcomes O-1 to O-4 |
| Technology | HLD (NEEDED) | Architecture decisions and stack |
| Prototype | Working prototype (NEEDED) | Demonstrable service design |

---

## Prioritised Recommendations

### CRITICAL Priority (Must complete before Alpha assessment)

| # | Action | Point(s) | Owner | Rationale |
|---|--------|----------|-------|-----------|
| 1 | **Conduct 12+ user research sessions** with patients and practice staff | 1, 4, 8 | User Researcher | GDS will not pass Alpha without user research evidence |
| 2 | **Build interactive prototype** using NHS Design System | 4, 8 | Interaction Designer | Cannot demonstrate simplicity or iteration without a prototype |
| 3 | **Create High-Level Design** with C4 architecture diagrams | 2, 11 | Enterprise Architect | Technology choices must be documented and justified |
| 4 | **Conduct usability testing** with prototype (6+ participants) | 1, 4, 8 | User Researcher | Must show evidence of testing and learning |

### HIGH Priority (Strongly recommended before assessment)

| # | Action | Point(s) | Owner | Rationale |
|---|--------|----------|-------|-----------|
| 5 | **Create team roster** with named individuals and roles | 6 | Delivery Manager | Assessors need to see a real team |
| 6 | **Document sprint history** and agile practices | 7 | Delivery Manager | Must demonstrate agile ways of working |
| 7 | **Map to 4 mandatory GDS KPIs** | 10 | Product Owner | Required metrics framework |
| 8 | **Document open source strategy** and select licence | 12 | Technical Lead | Clear plan for code publication |
| 9 | **Document ADRs** for key technology decisions | 11 | Enterprise Architect | Justify technology choices |
| 10 | **Create user journey maps** from research findings | 1, 2 | User Researcher | Visual evidence of user understanding |

### MEDIUM Priority (Recommended for strong assessment)

| # | Action | Point(s) | Owner | Rationale |
|---|--------|----------|-------|-----------|
| 11 | **Create cross-channel journey maps** | 3 | User Researcher | Show multi-channel understanding |
| 12 | **Design monitoring dashboard** approach | 14 | Technical Lead | Show operational thinking |
| 13 | **Create product backlog** with user stories | 7 | Product Owner | Show agile artifacts |
| 14 | **Document analytics approach** | 10 | Technical Lead | Show how metrics will be collected |
| 15 | **Plan Beta research programme** | 1, 8 | User Researcher | Show forward planning |
| 16 | **Create service landscape diagram** | 2 | Enterprise Architect | Show wider context understanding |

---

## Risk Assessment for Assessment Outcome

### Likely Assessment Outcome

**Current prediction: AMBER (Met with Conditions)**

GDS Alpha assessments typically result in one of:
- **Met**: All points satisfactorily evidenced
- **Met with conditions**: Points evidenced but specific actions required before Beta assessment
- **Not met**: Significant gaps requiring re-assessment

**Most likely conditions (if critical actions completed):**
1. Increase volume and diversity of user research before Beta
2. Demonstrate iteration based on user research findings
3. Complete penetration testing before Beta assessment
4. Develop operational runbooks and support model
5. Publish source code in public repository

**Risk of "Not Met" if:**
- No user research sessions conducted (Points 1, 4, 8)
- No prototype or working software to demonstrate (Points 4, 8)
- No technology architecture documentation (Point 11)

### Key Risks

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| No user research completed before assessment | Medium | Critical (Not Met) | Prioritise research sessions immediately |
| No prototype available | Medium | High (conditions) | Build minimum viable prototype |
| Assessment date set before evidence ready | Medium | High (Not Met) | Do not schedule until critical actions complete |
| Team roster gaps (user researcher, designer) | Medium | Medium (conditions) | Recruit immediately |

---

## Traceability Matrix

### Evidence Mapping: Points x Artifacts

| Point | PRIN | STKE | REQ | DATA | DPIA | SECD | RISK | Gap |
|-------|------|------|-----|------|------|------|------|-----|
| 1. User needs | Principle 1 | SD-1 to SD-10, Personas | Personas, Use Cases | | Vulnerable groups | | | User research sessions |
| 2. Whole problem | Principle 4 | Ecosystem | Scope, Integrations | | | | | Architecture diagrams |
| 3. Joined up | Principle 10, 11 | Multi-channel | FR-10, BC-4, INT-4 | | | | | Channel maps |
| 4. Simple to use | Principle 1 | | NFR-U-1, UC-1 | | | | | Prototype, testing |
| 5. Everyone can use | Principle 13 | Vulnerable groups | NFR-U-2, FR-9, FR-10 | | DPIA-010 | | R-008 | |
| 6. Multidisciplinary | | RACI | Stakeholders | | | | | Team roster |
| 7. Agile | Principle 14 | | NFR-C-3 | | | | | Sprint evidence |
| 8. Iterate | | Iteration history | | | | | | Prototype, research |
| 9. Secure | Principle 5, 7 | SD-8, SD-10 | NFR-SEC-1 to 5 | Full model | Full DPIA | Full SECD | R-004, R-009, R-010 | |
| 10. Success metrics | | G-1 to G-7, O-1 to O-4 | KPIs | | | | | GDS 4 KPIs |
| 11. Right technology | Principle 4, 17, 19 | | Integrations | PostgreSQL | | Cloud, DevSecOps | | HLD, ADRs |
| 12. Open code | Principle 14 | | NFR-C-3 | | | SBOM, licence | | OS strategy |
| 13. Open standards | Principle 4, 10 | | FHIR, OIDC, SNOMED | | | | | |
| 14. Reliable | Principle 2, 3, 16 | | NFR-A-1 to 3, NFR-P | | | DR, backup | | Runbooks, SLOs |

---

## Appendix A: GDS Service Standard Reference

### The 14 Points

1. Understand users and their needs
2. Solve a whole problem for users
3. Provide a joined up experience across all channels
4. Make the service simple to use
5. Make sure everyone can use the service
6. Have a multidisciplinary team
7. Use agile ways of working
8. Iterate and improve frequently
9. Create a secure service which protects users' privacy
10. Define what success looks like and publish performance data
11. Choose the right tools and technology
12. Make new source code open
13. Use and contribute to open standards, common components and patterns
14. Operate a reliable service

### Alpha Assessment Expectations

At Alpha, assessors expect:
- Evidence of understanding user needs through research
- Prototypes tested with users
- Technical approach explored and justified
- Plans for Beta with clear evidence of learning
- Accessibility and security considered from the start
- NOT a fully built service - but evidence of thinking and testing

---

## Appendix B: Source Artifacts

| Artifact | Location | Version |
|----------|----------|---------|
| Architecture Principles | `projects/000-global/ARC-000-PRIN-v1.0.md` | 1.0 |
| Stakeholder Analysis | `projects/001-doctors-appointment/ARC-001-STKE-v1.3.md` | 1.3 |
| Requirements | `projects/001-doctors-appointment/ARC-001-REQ-v1.0.md` | 1.0 |
| Data Model | `projects/001-doctors-appointment/ARC-001-DATA-v1.0.md` | 1.0 |
| DPIA | `projects/001-doctors-appointment/ARC-001-DPIA-v1.0.md` | 1.0 |
| Secure by Design | `projects/001-doctors-appointment/ARC-001-SECD-v1.0.md` | 1.0 |
| Risk Register | `projects/001-doctors-appointment/ARC-001-RISK-v1.1.md` | 1.1 |

---

## Appendix C: Glossary

| Term | Definition |
|------|------------|
| **GDS** | Government Digital Service - sets the Service Standard for UK government services |
| **RAG** | Red, Amber, Green - traffic light rating system |
| **Service Standard** | 14-point assessment framework for UK government digital services |
| **Alpha** | GDS phase where you prototype and test potential solutions |
| **Beta** | GDS phase where you build a working service and test it in public |
| **Live** | GDS phase where the service is fully operational |
| **WCAG** | Web Content Accessibility Guidelines |
| **FHIR** | Fast Healthcare Interoperability Resources - healthcare data exchange standard |
| **GP Connect** | NHS Digital API standard for GP system integration |
| **NHS Login** | NHS patient authentication service |
| **DPIA** | Data Protection Impact Assessment |
| **NCSC CAF** | National Cyber Security Centre Cyber Assessment Framework |
| **SNOMED CT** | Systematized Nomenclature of Medicine Clinical Terms |
| **ADR** | Architecture Decision Record |
| **HLD** | High-Level Design |
| **C4** | Context, Container, Component, Code - architecture diagram model |
| **SLO/SLI** | Service Level Objective / Service Level Indicator |

---

**Generated by**: ArcKit `/arckit.service-assessment` command
**Generated on**: 2026-01-28
**ArcKit Version**: 1.0.0
**Project**: NHS Doctors Online Appointment System (Project 001)
**AI Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
**Assessment Phase**: Alpha
**Evidence Artifacts Analysed**: 7 (ARC-000-PRIN-v1.0, ARC-001-STKE-v1.3, ARC-001-REQ-v1.0, ARC-001-DATA-v1.0, ARC-001-DPIA-v1.0, ARC-001-SECD-v1.0, ARC-001-RISK-v1.1)
