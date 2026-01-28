# Stakeholder Drivers & Goals Analysis: NHS Doctors Online Appointment System

> **Template Status**: Live | **Version**: 1.0.0 | **Command**: `/arckit.stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.0 |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
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
| **Distribution** | Project Team, NHS Digital Leadership, GDS Assessment Team, Primary Care Representatives |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-28 | ArcKit AI | Initial creation from `/arckit.stakeholders` command | PENDING | PENDING |

---

## Executive Summary

### Purpose
This document identifies key stakeholders for the NHS Doctors Online Appointment System, their underlying drivers (motivations, concerns, pressures), how these drivers manifest into goals, and the measurable outcomes that will satisfy those goals. This analysis ensures stakeholder alignment and provides traceability from individual concerns to project success metrics.

### Key Findings
The project has strong alignment between patient access drivers and NHS Long Term Plan objectives, creating natural momentum. However, significant tension exists between the urgency for digital transformation (Ministerial/NHS England pressure) and the caution required for clinical safety and GP practice adoption. GP practices are the critical enabler - without their active participation in GP Connect enablement, the service cannot deliver value.

The most critical conflict is between speed-to-market (political/strategic drivers) and thorough clinical safety assurance (patient safety drivers). This must be managed through a phased rollout starting with enthusiastic early-adopter practices while clinical safety evidence accumulates.

### Critical Success Factors
- **CSF-1**: GP practice adoption - minimum 500 practices enabled for GP Connect by Beta launch
- **CSF-2**: Clinical safety sign-off - Hazard Log approved with acceptable residual risk before each phase
- **CSF-3**: Patient trust - >70% of users who start booking complete successfully
- **CSF-4**: GDS Service Standard pass - Alpha, Beta, Live assessments passed on first attempt
- **CSF-5**: Accessibility compliance - WCAG 2.2 AA with no critical issues

### Stakeholder Alignment Score
**Overall Alignment**: MEDIUM

While strategic objectives align well across NHS England, NHS Digital, and patient groups, operational stakeholders (GP practices, clinical safety) have legitimate concerns about implementation pace that create friction. Resolution requires phased approach with clear governance.

---

## Stakeholder Identification

### Internal Stakeholders (NHS)

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| NHS England Director of Primary Care | Executive Sponsor | HIGH | HIGH | Steering Committee chair, monthly updates |
| NHS Digital Director of Digital Services | Programme Sponsor | HIGH | HIGH | Weekly stand-ups, decision authority |
| Minister for Health (DHSC) | Ministerial Accountability | HIGH | MEDIUM | Quarterly briefings, parliamentary question prep |
| Product Owner | Product Delivery | MEDIUM | HIGH | Daily involvement, backlog ownership |
| Clinical Safety Officer | Clinical Governance | HIGH | HIGH | Safety reviews, hazard log sign-off |
| Enterprise Architect | Technical Governance | MEDIUM | HIGH | Architecture decisions, design reviews |
| Information Governance Lead | Data Protection | HIGH | MEDIUM | DPIA approval, data handling assurance |
| Security Lead | Cyber Security | HIGH | MEDIUM | Penetration testing, DSPT compliance |
| GP Connect Team | Integration Platform | MEDIUM | HIGH | API integration, supplier liaison |
| NHS Login Team | Identity Platform | MEDIUM | HIGH | Authentication integration, capacity planning |

### External Stakeholders

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| Patients | General Public | Primary Beneficiary | LOW | HIGH |
| GP Practice Managers | Primary Care | Service Enabler | HIGH | HIGH |
| GPs / Clinicians | Primary Care | Clinical Users | MEDIUM | MEDIUM |
| Practice Receptionists | Primary Care | Operational Users | LOW | HIGH |
| GP System Suppliers (EMIS, TPP, etc.) | Commercial | Technology Partners | HIGH | HIGH |
| GDS Assessment Team | Cabinet Office | Service Assessment | HIGH | MEDIUM |
| ICO | Regulator | Data Protection | HIGH | LOW |
| CQC | Regulator | Healthcare Quality | MEDIUM | LOW |
| Patient Advocacy Groups | Third Sector | User Voice | LOW | HIGH |
| Healthwatch | Third Sector | Patient Champion | MEDIUM | HIGH |
| Welsh Government | Devolved Admin | Welsh Services | MEDIUM | MEDIUM |

### Stakeholder Power-Interest Grid

```
HIGH POWER
    │
    │  [Manage Closely]              │  [Keep Satisfied]
    │  - NHS England Director        │  - Minister (DHSC)
    │  - NHS Digital Director        │  - ICO
    │  - Clinical Safety Officer     │  - CQC
    │  - GP System Suppliers         │  - Welsh Government
    │  - GP Practice Managers        │
    │  - GDS Assessment Team         │
────┼────────────────────────────────┼─────────────────────────
    │  [Keep Informed]               │  [Monitor]
    │  - Patients                    │  - Industry Bodies
    │  - Practice Receptionists      │
    │  - Product Owner               │
    │  - Patient Advocacy Groups     │
    │  - Healthwatch                 │
    │                                │
LOW POWER                                              LOW INTEREST
                                                HIGH INTEREST
```

---

## Stakeholder Drivers Analysis

### SD-1: NHS England Director - Deliver NHS Long Term Plan Digital Commitment

**Stakeholder**: NHS England Director of Primary Care

**Driver Category**: STRATEGIC / POLITICAL

**Driver Statement**: Demonstrate visible progress on NHS Long Term Plan commitment to expand digital access to primary care, enabling positive announcements and defending against criticism of NHS digital transformation pace.

**Context & Background**:
The NHS Long Term Plan (2019) committed to expanding digital access to primary care. Parliamentary questions and media scrutiny regularly challenge NHS progress on digital transformation. The Director needs tangible evidence of delivery to maintain credibility with Ministers and the public.

**Driver Intensity**: CRITICAL

**Enablers**:
- Clear delivery milestones that can be publicly announced
- Patient testimonials and success stories
- Measurable uptake statistics for parliamentary answers

**Blockers**:
- Service failures that generate negative media coverage
- Clinical safety incidents requiring pause or rollback
- Poor patient experience undermining the digital access narrative

**Related Stakeholders**: Minister (DHSC), NHS Digital Director, Patient Advocacy Groups

---

### SD-2: Clinical Safety Officer - Protect Patients from Harm

**Stakeholder**: Clinical Safety Officer, NHS Digital

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**: Ensure the system does not introduce clinical risks that could harm patients through booking errors, missed appointments, or identity confusion. Maintain personal professional accountability under DCB0129/DCB0160.

**Context & Background**:
DCB0129 (manufacturer) and DCB0160 (deployer) standards place personal accountability on the Clinical Safety Officer. Any clinical incident traced to the booking system could result in regulatory action, reputational damage, and personal professional consequences. The CSO has seen other NHS digital projects fail safety assessments.

**Driver Intensity**: CRITICAL

**Enablers**:
- Sufficient time for thorough hazard identification and testing
- Clear clinical governance with authority to halt releases
- Independent clinical review of system design

**Blockers**:
- Pressure to accelerate delivery at expense of safety review
- Incomplete testing before release
- Scope creep introducing new unassessed hazards

**Related Stakeholders**: NHS England Director (potential conflict), Product Owner, GPs

---

### SD-3: GP Practice Managers - Reduce Administrative Burden

**Stakeholder**: GP Practice Managers (collective)

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Reduce the overwhelming volume of Monday morning telephone calls and free reception staff from repetitive booking tasks to focus on patient care and practice administration.

**Context & Background**:
GP practices are under severe operational pressure. Monday 8am booking opens create chaos with phone lines overwhelmed, patients frustrated, and staff stressed. Practice managers are personally accountable for staff wellbeing and patient complaints. They've been promised digital solutions before that failed to deliver.

**Driver Intensity**: HIGH

**Enablers**:
- System that actually reduces phone calls (not just adds another channel)
- Seamless integration with existing clinical systems (no dual data entry)
- Patient adoption so online booking becomes primary channel

**Blockers**:
- System that creates more work (reconciling bookings, handling errors)
- Patients still calling because online system is confusing
- GP Connect integration issues with their specific system supplier

**Related Stakeholders**: Practice Receptionists, GPs, GP System Suppliers

---

### SD-4: Patients - Access GP Appointments Without Frustration

**Stakeholder**: Patients (general public)

**Driver Category**: CUSTOMER / PERSONAL

**Driver Statement**: Book GP appointments conveniently without the stress of 8am phone queues, engaged signals, and limited availability - particularly for working people who cannot call during office hours.

**Context & Background**:
Patient surveys consistently show appointment access as the top concern with GP services. Working patients cannot call at 8am. Parents with children have competing demands. Elderly patients find phone queues exhausting. The current system creates health inequity where those with most time and persistence get appointments.

**Driver Intensity**: HIGH

**Enablers**:
- 24/7 availability - book when convenient
- Simple, accessible interface (including for less digital-confident users)
- Real-time slot visibility (not false availability)

**Blockers**:
- Complex registration or authentication processes
- Slots already taken when you try to book
- System only offering appointments far in future

**Related Stakeholders**: Patient Advocacy Groups, Healthwatch, Elderly/Disabled Patient Groups

---

### SD-5: GP System Suppliers - Maintain Market Position

**Stakeholder**: GP System Suppliers (EMIS, TPP, Vision, Microtest)

**Driver Category**: STRATEGIC / FINANCIAL

**Driver Statement**: Support GP Connect integration to maintain NHS contracts and competitive position, while protecting proprietary advantages and managing development costs.

**Context & Background**:
GP system suppliers have contractual obligations to support GP Connect. However, they also compete for GP practice contracts and have business interests in their own patient-facing portals. Supporting a national NHS booking system could cannibalize their own products. They need to balance cooperation with commercial protection.

**Driver Intensity**: MEDIUM

**Enablers**:
- Clear, stable GP Connect specifications (not constantly changing)
- NHS funding for integration development
- Recognition that national system grows overall digital adoption

**Blockers**:
- Unfunded mandates for integration work
- Specifications that favour competitors
- Perception that NHS is competing with their products

**Related Stakeholders**: GP Practice Managers, GP Connect Team, NHS Digital Director

---

### SD-6: GDS Assessment Team - Ensure Service Standard Compliance

**Stakeholder**: GDS Assessment Team, Cabinet Office

**Driver Category**: COMPLIANCE / PROFESSIONAL

**Driver Statement**: Ensure the service meets GDS Service Standard across all 14 points, demonstrating user-centered design, accessibility, security, and operational excellence expected of government digital services.

**Context & Background**:
GDS assessors are accountable for maintaining Service Standard integrity. Passing services that later fail damages GDS credibility. They've seen NHS projects struggle with accessibility and user research. They want to see genuine user-centered design, not checkbox compliance.

**Driver Intensity**: HIGH

**Enablers**:
- Genuine user research with diverse patient groups
- Clear evidence of iteration based on user feedback
- Accessibility testing with real assistive technology users
- Operational metrics and incident response capability

**Blockers**:
- Insufficient user research evidence
- Accessibility issues discovered at assessment
- Lack of performance data or unclear success metrics
- Technology choices that don't follow open standards

**Related Stakeholders**: Product Owner, Patients, Accessibility Specialists

---

### SD-7: Minister for Health - Demonstrate NHS Modernisation

**Stakeholder**: Minister for Health and Social Care

**Driver Category**: POLITICAL / PERSONAL

**Driver Statement**: Announce tangible improvements to NHS services that resonate with voters and demonstrate government commitment to NHS modernisation, while avoiding negative headlines about NHS IT failures.

**Context & Background**:
The Minister faces regular parliamentary questions about GP access. Positive digital transformation stories support the government's NHS narrative. However, NHS IT projects have a history of high-profile failures (NPfIT). The Minister needs success stories but is risk-averse to anything that could become a negative headline.

**Driver Intensity**: HIGH

**Enablers**:
- Positive patient stories for announcements
- Clear statistics showing improvement
- Phased rollout allowing early wins before full commitment

**Blockers**:
- System failures generating media coverage
- Patient complaints reaching MP surgeries
- NAO or PAC criticism of project delivery

**Related Stakeholders**: NHS England Director, NHS Digital Director, Patients

---

### SD-8: Information Governance Lead - Protect Patient Data

**Stakeholder**: Information Governance Lead, NHS Digital

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**: Ensure lawful processing of special category health data under UK GDPR, complete DPIA approval, and avoid data breaches that would require ICO notification and damage patient trust.

**Context & Background**:
Health data is special category under UK GDPR requiring explicit legal basis. The IG Lead is accountable for DPIA sign-off. Any data breach involving patient information would require ICO notification within 72 hours and could result in significant fines. Past NHS data incidents have severely damaged public trust.

**Driver Intensity**: CRITICAL

**Enablers**:
- Privacy by design from project start
- Clear data flows and processing purposes
- UK-only data residency
- Robust consent mechanisms for optional processing

**Blockers**:
- Unclear data flows or processing purposes
- Third-party services with unclear data handling
- Pressure to launch before DPIA approved

**Related Stakeholders**: Clinical Safety Officer, Security Lead, ICO

---

### SD-9: Practice Receptionists - Manageable Workload

**Stakeholder**: Practice Receptionists (collective)

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Have a manageable workload with fewer angry patients, clear processes for online bookings, and systems that work reliably without creating extra reconciliation work.

**Context & Background**:
Receptionists bear the brunt of patient frustration about appointment access. They're often blamed for problems beyond their control. Previous "digital solutions" have sometimes increased their workload by adding another system to check. They need tools that genuinely help, not add complexity.

**Driver Intensity**: MEDIUM

**Enablers**:
- Online bookings appearing automatically in clinical system
- Fewer phone calls from patients who can self-serve
- Clear process for handling online booking queries

**Blockers**:
- System errors requiring manual intervention
- Patients calling to confirm online bookings worked
- Dual entry between online and clinical systems

**Related Stakeholders**: GP Practice Managers, Patients

---

### SD-10: Security Lead - Protect NHS Systems

**Stakeholder**: Security Lead, NHS Digital

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**: Ensure the system meets DSPT requirements, protects patient data from cyber threats, and doesn't introduce vulnerabilities that could be exploited to attack NHS infrastructure.

**Context & Background**:
NHS has been targeted by significant cyber attacks (WannaCry). The Security Lead is accountable for DSPT compliance and penetration testing. Any security incident would have serious consequences for patients, the organisation, and the Security Lead personally.

**Driver Intensity**: HIGH

**Enablers**:
- Security requirements considered from design phase
- Penetration testing before each release
- Incident response plans tested and ready

**Blockers**:
- Pressure to skip security testing for speed
- Third-party components with known vulnerabilities
- Insufficient security expertise in development team

**Related Stakeholders**: IG Lead, NHS Spine Team, GP System Suppliers

---

## Driver-to-Goal Mapping

### Goal G-1: Achieve 30% Online Booking Uptake

**Derived From Drivers**: SD-1 (NHS England - Long Term Plan), SD-3 (Practice Managers - Reduce Burden), SD-4 (Patients - Access)

**Goal Owner**: NHS Digital Director

**Goal Statement**: Achieve 30% of eligible GP appointments booked through the online system within 12 months of Live launch across participating practices.

**Why This Matters**: Demonstrates meaningful shift to digital (satisfies NHS England), reduces phone burden (satisfies Practice Managers), and proves patients find value (validates patient access driver).

**Success Metrics**:
- **Primary Metric**: Percentage of appointments booked online vs total appointments at participating practices
- **Secondary Metrics**:
  - Number of unique patients using online booking
  - Repeat usage rate (patients booking online more than once)
  - Practice staff telephone booking time reduction

**Baseline**: 0% (new service)

**Target**: 30% within 12 months of Live launch

**Measurement Method**: Analytics from booking system cross-referenced with GP Connect appointment data

**Dependencies**:
- Minimum 500 practices enabled for GP Connect
- GP system suppliers maintain stable API availability
- Patient awareness campaign reaches target audience

**Risks to Achievement**:
- GP practice adoption slower than planned
- Patient trust/awareness insufficient
- System performance issues during Monday peaks

---

### Goal G-2: Zero Clinical Safety Incidents

**Derived From Drivers**: SD-2 (Clinical Safety Officer - Protect Patients), SD-7 (Minister - Avoid Headlines)

**Goal Owner**: Clinical Safety Officer

**Goal Statement**: Achieve zero patient safety incidents directly attributable to the booking system throughout Alpha, Beta, and first 12 months of Live operation.

**Why This Matters**: Protects patients (primary purpose), protects CSO professional accountability, and prevents negative headlines that would damage NHS digital reputation.

**Success Metrics**:
- **Primary Metric**: Number of patient safety incidents (target: 0)
- **Secondary Metrics**:
  - Hazard log issues resolved before release
  - Near-miss reports and trend analysis
  - Clinical safety audit findings

**Baseline**: N/A (new service)

**Target**: Zero patient safety incidents

**Measurement Method**: Clinical incident reporting system, hazard log reviews, post-incident investigations

**Dependencies**:
- Thorough hazard identification completed
- Adequate time for clinical safety testing
- Clear clinical governance with halt authority

**Risks to Achievement**:
- Unknown hazards not identified during design
- Pressure to release before safety review complete
- Integration errors with GP systems causing booking conflicts

---

### Goal G-3: Pass GDS Service Assessments

**Derived From Drivers**: SD-6 (GDS - Service Standard), SD-1 (NHS England - Demonstrate Progress)

**Goal Owner**: Product Owner

**Goal Statement**: Pass GDS Service Standard assessments at Alpha, Beta, and Live stages on first attempt.

**Why This Matters**: Mandatory for government services, demonstrates quality of delivery, and enables progression to full public launch.

**Success Metrics**:
- **Primary Metric**: Assessment outcome (Pass/Not Pass)
- **Secondary Metrics**:
  - Number of assessment conditions/recommendations
  - User research sessions completed per phase
  - Accessibility audit results

**Baseline**: N/A

**Target**: Pass all three assessments

**Measurement Method**: GDS assessment panel decision, assessment reports

**Dependencies**:
- Sufficient user research with diverse participants
- Accessibility testing with assistive technology users
- Performance data available for assessment
- Multidisciplinary team in place

**Risks to Achievement**:
- Insufficient time for user research
- Accessibility issues not resolved before assessment
- Lack of performance metrics evidence

---

### Goal G-4: Reduce Practice Phone Booking Time by 40%

**Derived From Drivers**: SD-3 (Practice Managers - Reduce Burden), SD-9 (Receptionists - Workload)

**Goal Owner**: NHS England Director of Primary Care

**Goal Statement**: Reduce time spent by practice staff on telephone appointment bookings by 40% within 12 months at participating practices.

**Why This Matters**: Directly addresses practice operational pressure, frees staff for higher-value patient care, and provides evidence of NHS efficiency improvement.

**Success Metrics**:
- **Primary Metric**: Hours per day spent on telephone bookings (per practice)
- **Secondary Metrics**:
  - Phone call volume to practice
  - Average call duration for bookings
  - Staff satisfaction survey scores

**Baseline**: ~3 hours/day per practice (estimated from practice surveys)

**Target**: 1.8 hours/day per practice (40% reduction)

**Measurement Method**: Practice staff time surveys, phone system analytics where available

**Dependencies**:
- Patients aware of and using online booking
- Online system reliable and easy to use
- GP Connect integration seamless (no dual entry)

**Risks to Achievement**:
- Patients continue calling to verify online bookings
- Technical issues require staff intervention
- Low patient adoption maintains phone demand

---

### Goal G-5: Achieve 80% Patient Satisfaction

**Derived From Drivers**: SD-4 (Patients - Access), SD-7 (Minister - Positive Stories)

**Goal Owner**: Product Owner

**Goal Statement**: Achieve 80% satisfaction rating among patients who use the online booking system within 6 months of Live launch.

**Why This Matters**: Proves the service meets patient needs, provides positive stories for NHS communications, and validates user-centered design approach.

**Success Metrics**:
- **Primary Metric**: Post-booking satisfaction survey score (1-5 scale, target ≥4)
- **Secondary Metrics**:
  - Task completion rate (started vs completed bookings)
  - System Usability Scale (SUS) score
  - Patient feedback themes

**Baseline**: N/A (new service)

**Target**: 80% rating ≥4 out of 5

**Measurement Method**: Post-booking survey, in-service feedback mechanism

**Dependencies**:
- Survey mechanism integrated into service
- Representative sample of users respond
- Service genuinely meets user needs

**Risks to Achievement**:
- Survey response bias (only satisfied users respond)
- System usability issues not discovered in Beta
- Accessibility barriers excluding some users

---

### Goal G-6: Maintain Zero Data Breaches

**Derived From Drivers**: SD-8 (IG Lead - Protect Data), SD-10 (Security Lead - Protect Systems)

**Goal Owner**: Information Governance Lead

**Goal Statement**: Maintain zero personal data breaches requiring ICO notification throughout project lifetime.

**Why This Matters**: Legal requirement under UK GDPR, protects patient trust, and avoids regulatory penalties and reputational damage.

**Success Metrics**:
- **Primary Metric**: Number of data breaches requiring ICO notification (target: 0)
- **Secondary Metrics**:
  - Security vulnerability scan results
  - Penetration test findings remediation time
  - DSPT compliance status

**Baseline**: N/A

**Target**: Zero notifiable breaches

**Measurement Method**: Incident reporting system, security monitoring, DSPT self-assessment

**Dependencies**:
- Security by design implemented
- Penetration testing before each release
- Incident response plan tested

**Risks to Achievement**:
- Unknown vulnerabilities exploited
- Third-party component breach
- Insider threat or human error

---

### Goal G-7: Enable 500+ GP Practices by Beta

**Derived From Drivers**: SD-5 (GP Suppliers - Maintain Position), SD-3 (Practice Managers - Reduce Burden), SD-1 (NHS England - Demonstrate Progress)

**Goal Owner**: GP Connect Team Lead

**Goal Statement**: Enable GP Connect Appointment Management capability at 500+ practices across all major GP system suppliers by Beta launch.

**Why This Matters**: Critical mass of practices needed for meaningful service, demonstrates GP supplier cooperation, and enables geographic coverage for diverse testing.

**Success Metrics**:
- **Primary Metric**: Number of practices enabled for GP Connect Appointment Management
- **Secondary Metrics**:
  - Coverage across GP system suppliers
  - Geographic distribution of practices
  - API availability/reliability metrics

**Baseline**: Current GP Connect enabled practices (varies by capability)

**Target**: 500 practices by Beta, 2000 by Live

**Measurement Method**: GP Connect onboarding tracker, practice registration data

**Dependencies**:
- GP system suppliers implement and support API
- Practices opt-in and configure GP Connect
- NHS funding available for supplier development

**Risks to Achievement**:
- GP system supplier delays
- Practice hesitancy to adopt
- Technical integration issues

---

## Goal-to-Outcome Mapping

### Outcome O-1: Digital Shift in Primary Care Access

**Supported Goals**: G-1 (30% Uptake), G-5 (Patient Satisfaction), G-7 (Practice Enablement)

**Outcome Statement**: Measurable shift from telephone to digital booking demonstrating successful NHS digital transformation in primary care.

**Measurement Details**:
- **KPI**: Online Booking Percentage
- **Current Value**: 0%
- **Target Value**: 30% at participating practices
- **Measurement Frequency**: Weekly
- **Data Source**: Booking system analytics, GP Connect data
- **Report Owner**: NHS Digital Analytics Team

**Business Value**:
- **Financial Impact**: Estimated £12M annual efficiency savings across NHS (staff time)
- **Strategic Impact**: Demonstrates NHS Long Term Plan delivery
- **Operational Impact**: Reduced practice telephone burden
- **Customer Impact**: Improved patient access equity

**Timeline**:
- **Phase 1 (Beta, Months 1-3)**: 5% uptake at pilot practices
- **Phase 2 (Early Live, Months 4-6)**: 15% uptake as rollout expands
- **Phase 3 (Full Live, Months 7-12)**: 30% uptake target achieved
- **Sustainment (Year 2+)**: Growth to 50%+ as default channel

**Stakeholder Benefits**:
- **NHS England Director**: Evidence for parliamentary answers and announcements
- **GP Practice Managers**: Measurable reduction in phone call volume
- **Patients**: Convenient 24/7 booking option
- **Minister**: Positive NHS digital transformation story

**Leading Indicators**:
- Registration/first booking conversion rate
- Week-on-week growth in booking volume
- Practice staff feedback on phone volume

**Lagging Indicators**:
- Final percentage achievement
- Year-on-year comparison
- Sustained usage over time

---

### Outcome O-2: Safe Digital Healthcare Service

**Supported Goals**: G-2 (Zero Incidents), G-6 (Zero Breaches), G-3 (GDS Pass)

**Outcome Statement**: Clinically safe and secure digital service with no patient harm incidents or data breaches.

**Measurement Details**:
- **KPI**: Patient Safety Incident Count
- **Current Value**: N/A
- **Target Value**: 0
- **Measurement Frequency**: Continuous
- **Data Source**: Clinical incident reporting, Security monitoring
- **Report Owner**: Clinical Safety Officer / Security Lead

**Business Value**:
- **Financial Impact**: Avoided regulatory penalties (potential £17.5M ICO maximum)
- **Strategic Impact**: Maintained public trust in NHS digital services
- **Operational Impact**: Uninterrupted service delivery
- **Customer Impact**: Patient confidence in online booking

**Timeline**:
- **Phase 1 (Alpha)**: Hazard log complete, no incidents in testing
- **Phase 2 (Beta)**: Zero incidents in limited live use
- **Phase 3 (Live)**: Zero incidents in full operation
- **Sustainment**: Ongoing monitoring and continuous improvement

**Stakeholder Benefits**:
- **Clinical Safety Officer**: Professional accountability maintained
- **IG Lead**: GDPR compliance demonstrated
- **Minister**: No negative headlines from safety/security failures
- **Patients**: Trust in service maintained

**Leading Indicators**:
- Hazard log closure rate
- Security scan findings remediation time
- Near-miss reports and trends

**Lagging Indicators**:
- Actual incident count
- Regulatory findings
- Patient complaints about safety/privacy

---

### Outcome O-3: Improved GP Practice Efficiency

**Supported Goals**: G-4 (40% Phone Reduction), G-7 (Practice Enablement)

**Outcome Statement**: Measurable reduction in GP practice administrative burden through digital booking adoption.

**Measurement Details**:
- **KPI**: Staff Hours on Telephone Booking
- **Current Value**: ~3 hours/day per practice
- **Target Value**: 1.8 hours/day per practice
- **Measurement Frequency**: Quarterly
- **Data Source**: Practice staff surveys
- **Report Owner**: NHS England Primary Care Team

**Business Value**:
- **Financial Impact**: £24M annual value (staff time freed for patient care)
- **Strategic Impact**: Evidence for continued digital investment
- **Operational Impact**: 40% time saving on booking administration
- **Customer Impact**: Staff able to focus on patient-facing care

**Timeline**:
- **Phase 1 (Months 1-3)**: 10% reduction at early adopter practices
- **Phase 2 (Months 4-6)**: 25% reduction as adoption grows
- **Phase 3 (Months 7-12)**: 40% reduction target achieved
- **Sustainment**: Maintained or improved as online becomes default

**Stakeholder Benefits**:
- **Practice Managers**: Reduced operational pressure
- **Receptionists**: Manageable workload, fewer angry callers
- **NHS England**: Primary care efficiency evidence
- **Treasury**: Value for money demonstration

**Leading Indicators**:
- Daily phone call volumes
- Staff satisfaction scores
- Practice manager feedback

**Lagging Indicators**:
- Validated staff survey results
- Year-on-year comparison
- Staff retention rates

---

### Outcome O-4: Service Standard Compliance

**Supported Goals**: G-3 (GDS Pass), G-5 (Patient Satisfaction)

**Outcome Statement**: Fully compliant government digital service meeting all 14 points of GDS Service Standard.

**Measurement Details**:
- **KPI**: GDS Assessment Result
- **Current Value**: N/A
- **Target Value**: Pass (all phases)
- **Measurement Frequency**: Per assessment
- **Data Source**: GDS assessment panel
- **Report Owner**: Product Owner

**Business Value**:
- **Financial Impact**: Avoided re-assessment costs and delays
- **Strategic Impact**: Credibility as government digital exemplar
- **Operational Impact**: Permission to proceed to each phase
- **Customer Impact**: Assurance of user-centered design

**Timeline**:
- **Alpha Assessment**: Q2 2026
- **Beta Assessment**: Q4 2026
- **Live Assessment**: Q2 2027

**Stakeholder Benefits**:
- **NHS Digital Director**: Evidence of delivery capability
- **GDS**: Maintained Service Standard integrity
- **Patients**: Service designed around their needs
- **Product Owner**: Clear path to Live operation

**Leading Indicators**:
- User research session completion
- Accessibility audit results
- Mock assessment feedback

**Lagging Indicators**:
- Formal assessment result
- Assessment conditions/recommendations
- Re-assessment requirements

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| NHS England Director | SD-1 | Deliver Long Term Plan | G-1 | 30% online uptake | O-1 | Digital shift |
| NHS England Director | SD-1 | Deliver Long Term Plan | G-3 | GDS assessment pass | O-4 | Service Standard |
| Clinical Safety Officer | SD-2 | Protect patients | G-2 | Zero safety incidents | O-2 | Safe service |
| GP Practice Managers | SD-3 | Reduce admin burden | G-1 | 30% online uptake | O-1 | Digital shift |
| GP Practice Managers | SD-3 | Reduce admin burden | G-4 | 40% phone reduction | O-3 | Practice efficiency |
| Patients | SD-4 | Access without frustration | G-1 | 30% online uptake | O-1 | Digital shift |
| Patients | SD-4 | Access without frustration | G-5 | 80% satisfaction | O-1 | Digital shift |
| GP System Suppliers | SD-5 | Maintain market position | G-7 | 500 practices enabled | O-1 | Digital shift |
| GDS Assessment Team | SD-6 | Service Standard compliance | G-3 | GDS assessment pass | O-4 | Service Standard |
| Minister | SD-7 | Demonstrate modernisation | G-1 | 30% online uptake | O-1 | Digital shift |
| Minister | SD-7 | Demonstrate modernisation | G-2 | Zero safety incidents | O-2 | Safe service |
| IG Lead | SD-8 | Protect patient data | G-6 | Zero data breaches | O-2 | Safe service |
| Receptionists | SD-9 | Manageable workload | G-4 | 40% phone reduction | O-3 | Practice efficiency |
| Security Lead | SD-10 | Protect NHS systems | G-6 | Zero data breaches | O-2 | Safe service |

### Conflict Analysis

**Competing Drivers**:

**Conflict 1: Speed vs Safety**
- **SD-1 (NHS England)** wants rapid delivery to meet Long Term Plan commitments
- **SD-2 (Clinical Safety)** needs thorough testing and hazard assessment before release
- **Why incompatible**: Safety assurance takes time; accelerating delivery risks incomplete testing

**Resolution Strategy**:
- Phased rollout starting with limited practices allows safety evidence to accumulate
- Clear stage gates where Clinical Safety Officer has halt authority
- Accept slower initial rollout for sustainable velocity once safety proven
- Ministerial brief explaining why pace is calibrated for safety

---

**Conflict 2: National Mandate vs Practice Adoption**
- **SD-1 (NHS England)** wants comprehensive coverage for meaningful impact
- **SD-3 (Practice Managers)** will only adopt if genuine value proven
- **Why incompatible**: Can't mandate adoption; practices have local autonomy

**Resolution Strategy**:
- Start with enthusiastic early-adopter practices who want to participate
- Build evidence base of actual benefits for recruitment of hesitant practices
- Peer-to-peer sharing of success stories between practice managers
- Avoid mandating until benefits are undeniable

---

**Conflict 3: Innovation vs Stability**
- **SD-5 (GP Suppliers)** want stable specifications that don't change constantly
- **SD-6 (GDS)** wants iteration and improvement based on user feedback
- **Why incompatible**: Iteration means change; change requires supplier development

**Resolution Strategy**:
- Quarterly release cadence with locked specifications between releases
- Early visibility of roadmap for supplier planning
- Distinguish between API changes (infrequent) and UI changes (frequent)
- Joint planning with suppliers on major changes

---

### Synergies

**Synergy 1**: SD-1 (NHS England delivery) + SD-4 (Patient access) + SD-7 (Minister announcements)
- **Alignment**: All three benefit from successful patient adoption
- **Leverage**: Patient success stories serve multiple stakeholder needs simultaneously

**Synergy 2**: SD-2 (Clinical safety) + SD-8 (Data protection) + SD-10 (Cyber security)
- **Alignment**: All three require robust governance and testing
- **Leverage**: Single governance framework serves all three, combined testing effort

**Synergy 3**: SD-3 (Practice burden) + SD-9 (Receptionist workload)
- **Alignment**: Same outcome needed (less phone work)
- **Leverage**: Single metric (phone time) satisfies both stakeholders

---

## Communication & Engagement Plan

### NHS England Director

**Primary Message**: The service is on track to deliver measurable digital transformation in primary care with early evidence of patient adoption and practice efficiency gains.

**Key Talking Points**:
- X patients have successfully booked online this month
- Y practices now enabled, with Z more in pipeline
- Patient satisfaction scores at X%
- On track for GDS Alpha assessment

**Communication Frequency**: Monthly written update, quarterly Steering Committee

**Preferred Channel**: Executive summary email, Steering Committee presentation

**Success Story**: "We can now answer parliamentary questions with specific statistics showing digital adoption growth."

---

### Clinical Safety Officer

**Primary Message**: Clinical safety is paramount - we have robust governance ensuring no release without your sign-off, and adequate time for thorough hazard assessment.

**Key Talking Points**:
- Hazard log status and closure progress
- Testing coverage for identified risks
- Your halt authority is clear and respected
- Safety review timeline built into delivery plan

**Communication Frequency**: Weekly safety review meeting

**Preferred Channel**: Safety review meetings, direct line to Product Owner

**Success Story**: "Clinical governance worked as intended - we identified and resolved a potential hazard before it reached patients."

---

### GP Practice Managers

**Primary Message**: This system is designed to genuinely reduce your workload, not add complexity. Early practices are seeing real reductions in phone call volumes.

**Key Talking Points**:
- X practice has reduced phone bookings by Y%
- System integrates directly with your clinical system
- We'll support your onboarding and train your staff
- You can start small and expand as confidence grows

**Communication Frequency**: Monthly newsletter, practice manager community forums

**Preferred Channel**: GP practice newsletters, practice manager networks, regional events

**Success Story**: "Practice X saved 2 hours per day in reception time, allowing more focus on patient care."

---

### Patients

**Primary Message**: Book your GP appointment online, 24/7, without phone queues. Simple, secure, accessible.

**Key Talking Points**:
- Available any time - no more 8am rush
- Simple process - book in under 3 minutes
- Secure - uses NHS Login you may already have
- Accessible - works with screen readers, large text

**Communication Frequency**: Ongoing awareness campaign

**Preferred Channel**: NHS website, NHS App, practice waiting room screens, social media

**Success Story**: "I booked my appointment on Sunday evening in 2 minutes - so much better than calling on Monday morning."

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| GP Practice Managers | Phone-based booking | Multi-channel (phone + online) | MEDIUM | MEDIUM | Early adopter programme, peer success stories |
| Receptionists | Answer all booking calls | Fewer calls, handle exceptions | MEDIUM | LOW | Training, show time savings |
| Patients | Phone at 8am | 24/7 online option | LOW | LOW | Awareness campaign, simple onboarding |
| GP System Suppliers | Core product | API integration support | MEDIUM | MEDIUM | Funded development, stable specifications |
| NHS Digital Teams | Other projects | New service to operate | MEDIUM | LOW | Clear roles, operational handover |

### Change Readiness

**Champions** (Enthusiastic supporters):
- **Early-adopter practices** - Already frustrated with phone system, keen to try digital
- **Tech-savvy patients** - Want modern convenience, will promote to others
- **NHS Digital leadership** - Committed to digital transformation success

**Fence-sitters** (Neutral, need convincing):
- **Mainstream practices** - Will adopt once they see peers succeeding
- **GP system suppliers** - Commercial concerns, but contractually obligated
- **Less digital-confident patients** - Need assisted digital pathway

**Resisters** (Opposed or skeptical):
- **Practices burned by past IT failures** - Need evidence this is different, peer recommendation
- **Patients who prefer phone** - Maintain phone option, don't force digital-only
- **Staff concerned about job impact** - Emphasise redeployment to patient care, not replacement

---

## Risk Register (Stakeholder-Related)

### Risk R-1: GP Practice Adoption Stalls

**Related Stakeholders**: GP Practice Managers, GP System Suppliers

**Risk Description**: Practices do not enable GP Connect or opt-in to the service at sufficient rate to achieve meaningful coverage.

**Impact on Goals**: G-1 (uptake), G-4 (phone reduction), G-7 (practice enablement)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**:
- Identify and recruit enthusiastic early-adopter practices
- Provide hands-on onboarding support
- Share success stories peer-to-peer
- Address GP system supplier technical barriers

**Contingency Plan**: Focus on geographic clusters for regional impact even if national coverage limited.

---

### Risk R-2: Clinical Safety Incident Occurs

**Related Stakeholders**: Clinical Safety Officer, Patients, Minister

**Risk Description**: A patient experiences harm attributable to the booking system (wrong appointment, lost booking, identity confusion).

**Impact on Goals**: G-2 (zero incidents), G-7 (Minister - avoid headlines)

**Probability**: LOW

**Impact**: CRITICAL

**Mitigation Strategy**:
- Thorough hazard identification and testing
- Clinical Safety Officer halt authority
- Incident reporting and response procedures
- Phased rollout to limit exposure

**Contingency Plan**: Immediate service pause, incident investigation, fix before resumption, Ministerial briefing.

---

### Risk R-3: GDS Assessment Fails

**Related Stakeholders**: GDS Assessment Team, Product Owner, NHS England Director

**Risk Description**: Service fails GDS assessment requiring re-assessment and delaying progression.

**Impact on Goals**: G-3 (GDS pass), G-1 (uptake delayed)

**Probability**: MEDIUM

**Impact**: MEDIUM

**Mitigation Strategy**:
- Early engagement with GDS assessment team
- Mock assessments before formal assessment
- Address accessibility and user research gaps proactively
- Maintain comprehensive evidence portfolio

**Contingency Plan**: Address assessment conditions, implement recommendations, request re-assessment.

---

### Risk R-4: Data Breach Occurs

**Related Stakeholders**: IG Lead, Security Lead, ICO, Patients

**Risk Description**: Patient data is accessed by unauthorised parties requiring ICO notification.

**Impact on Goals**: G-6 (zero breaches), G-2 (safe service)

**Probability**: LOW

**Impact**: CRITICAL

**Mitigation Strategy**:
- Security by design from start
- Penetration testing before each release
- Encryption at rest and in transit
- Incident response plan tested

**Contingency Plan**: Immediate containment, ICO notification within 72 hours, patient notification, forensic investigation.

---

### Risk R-5: GP System Supplier Non-Cooperation

**Related Stakeholders**: GP System Suppliers, GP Connect Team

**Risk Description**: One or more major GP system suppliers delay or inadequately implement GP Connect integration.

**Impact on Goals**: G-7 (practice enablement), G-1 (uptake)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**:
- Contractual obligations for GP Connect support
- NHS funding for supplier development
- Regular supplier engagement meetings
- Early visibility of requirements

**Contingency Plan**: Escalation to NHS England commercial, focus on suppliers with good implementations.

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Budget approval | Finance | NHS Digital Director | Product Owner | All |
| Requirements prioritization | Product Owner | NHS England Director | Patients, Practices, GDS | Suppliers |
| Architecture decisions | Enterprise Architect | NHS Digital Director | Security, GP Connect | Suppliers |
| Clinical safety sign-off | Clinical Safety Officer | Clinical Safety Officer | GPs, Product Owner | All |
| Security assurance | Security Lead | IG Lead | Enterprise Architect | All |
| Go/No-go for Beta | Product Owner | NHS England Director | CSO, Security, GDS | Minister |
| Go/No-go for Live | NHS England Director | NHS Digital Director | All | Minister |
| Practice onboarding | GP Connect Team | NHS England Director | Practice Managers | Suppliers |
| GP system supplier issues | GP Connect Team | NHS Digital Director | Suppliers | NHS England |

### Escalation Path

1. **Level 1**: Product Owner (day-to-day delivery decisions)
2. **Level 2**: NHS Digital Director (resource, timeline, cross-team issues)
3. **Level 3**: NHS England Director / Steering Committee (strategic direction, major conflicts, Go/No-go)
4. **Level 4**: Minister briefing (significant risks, patient safety, media issues)

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| NHS England Director | PENDING | | PENDING |
| Clinical Safety Officer | PENDING | | PENDING |
| GP Practice Manager Rep | PENDING | | PENDING |
| Patient Representative | PENDING | | PENDING |
| Enterprise Architect | PENDING | | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Programme Sponsor | NHS Digital Director | | |
| Executive Sponsor | NHS England Director | | |
| Clinical Governance | Clinical Safety Officer | | |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

*To be completed during Discovery phase user research*

### Appendix B: Survey Results

*To be completed following practice manager and patient surveys*

### Appendix C: References

- ARC-000-PRIN-v1.0.md - Architecture Principles
- ARC-001-REQ-v1.0.md - Requirements Specification
- NHS Long Term Plan (2019)
- GDS Service Standard
- DCB0129/DCB0160 Clinical Safety Standards

---

**Generated by**: ArcKit `/arckit.stakeholders` command
**Generated on**: 2026-01-28
**ArcKit Version**: 1.0.0
**Project**: NHS Doctors Online Appointment System (Project 001)
**AI Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
