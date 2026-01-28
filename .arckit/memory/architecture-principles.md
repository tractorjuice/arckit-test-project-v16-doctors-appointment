# NHS Doctors Appointment System - Enterprise Architecture Principles

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-000-PRIN-v1.0 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | Doctors Online Appointment System (Global) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-01-28 |
| **Last Modified** | 2026-01-28 |
| **Review Cycle** | Annual |
| **Next Review Date** | 2027-01-28 |
| **Owner** | Enterprise Architecture Team |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | All Project Teams, NHS Digital, GDS Assessment Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-28 | ArcKit AI | Initial creation from `/arckit.principles` command | PENDING | PENDING |

---

## Executive Summary

This document establishes the immutable principles governing all technology architecture decisions for the NHS Doctors Online Appointment System. These principles ensure consistency, security, scalability, and alignment with NHS Digital standards, GDS Service Standard, and UK Government requirements.

**Scope**: All technology components, integrations, and data handling for the appointment booking system
**Authority**: Enterprise Architecture Review Board, NHS Digital Architecture Governance
**Compliance**: Mandatory unless exception approved by CTO/Clinical Safety Officer

**Philosophy**: These principles are **technology-agnostic** - they describe WHAT qualities the architecture must have, not HOW to implement them with specific products. Technology selection happens during research and design phases guided by these principles.

**Healthcare Context**: As an NHS service handling patient health data, these principles incorporate mandatory healthcare-specific requirements including clinical safety (DCB0129/DCB0160), NHS Data Security and Protection Toolkit (DSPT), and UK GDPR special category data handling.

---

## I. Strategic Principles

### 1. User-Centered Design (GDS Principle 1)

**Principle Statement**:
All systems MUST be designed around the needs of patients, clinicians, and practice staff, validated through user research and usability testing.

**Rationale**:
The GDS Service Standard mandates user-centered design. Healthcare services must be accessible to all patients including those with disabilities, limited digital literacy, or no internet access.

**Implications**:
- Conduct user research with real patients, clinicians, and practice staff before design
- Design for the full range of users (elderly, disabled, non-English speakers, low digital literacy)
- Provide assisted digital support pathways for users who cannot self-serve
- Test with users throughout development, not just at the end
- Measure success by user outcomes, not just system functionality

**Validation Gates**:
- [ ] User research conducted with representative patient cohort
- [ ] Accessibility testing with assistive technology users
- [ ] Usability testing at Alpha, Beta, and Live phases
- [ ] Assisted digital pathway designed and tested
- [ ] User satisfaction metrics defined and tracked

---

### 2. Scalability and Elasticity

**Principle Statement**:
All systems MUST be designed to scale horizontally to meet demand, handling appointment booking surges (Monday mornings, flu season, pandemic response) without degradation.

**Rationale**:
GP appointment demand is highly variable. Systems must handle 10x normal load during health crises without manual intervention or architectural changes.

**Implications**:
- Design for stateless components that can be replicated
- Avoid hard-coded limits or fixed capacity assumptions
- Plan for distributed deployment across multiple compute nodes
- Use load balancing to distribute traffic across instances
- Implement auto-scaling based on demand metrics
- Plan for surge capacity during health emergencies

**NHS-Specific Considerations**:
- Monday 8am booking rush (10x normal load within minutes)
- Seasonal flu vaccination campaigns
- Pandemic response requiring rapid scale-up
- National service outages requiring graceful degradation

**Validation Gates**:
- [ ] System can scale horizontally (add more instances)
- [ ] No single points of failure that limit scaling
- [ ] Load testing demonstrates capacity for 10x normal demand
- [ ] Scaling metrics and triggers defined
- [ ] Cost model accounts for variable capacity
- [ ] Surge capacity tested annually

---

### 3. Resilience and Fault Tolerance

**Principle Statement**:
All systems MUST gracefully degrade when dependencies fail (NHS Spine, GP Connect, SMS gateways) and recover automatically without data loss or manual intervention.

**Rationale**:
Healthcare services are critical infrastructure. Failures must not prevent patients from accessing care or cause loss of appointment data.

**Implications**:
- Implement circuit breakers for external dependencies (NHS Spine, GP Connect)
- Use timeouts on all network calls (NHS services can be slow)
- Retry with exponential backoff for transient failures
- Graceful degradation when non-critical services fail (e.g., SMS notifications)
- Automated health checks and recovery
- Avoid cascading failures through bulkhead isolation
- Maintain offline capability for critical booking data

**NHS-Specific Resilience**:
- NHS Spine may have scheduled maintenance windows
- GP Connect availability varies by practice
- MESH file transfer may be delayed
- Booking data must never be lost even during outages

**Validation Gates**:
- [ ] Failure modes identified for all NHS integrations
- [ ] Chaos engineering or fault injection testing performed
- [ ] Recovery Time Objective (RTO): <1 hour for booking services
- [ ] Recovery Point Objective (RPO): Zero data loss for appointments
- [ ] Automated failover tested monthly
- [ ] Degraded mode behavior documented and tested

---

### 4. NHS Interoperability (MANDATORY)

**Principle Statement**:
All systems MUST integrate with NHS national services using NHS Digital approved standards and protocols. Proprietary integration approaches are prohibited.

**Rationale**:
NHS interoperability ensures patient data flows correctly between systems, supports care continuity, and enables national health programmes.

**NHS Integration Requirements**:
- **NHS Spine**: Patient Demographics Service (PDS) for patient lookup via FHIR R4
- **NHS Login**: Patient authentication and identity verification (mandatory for patient-facing services)
- **GP Connect**: Access to GP clinical systems for appointment availability
- **MESH**: Secure file transfer for NHS communications
- **NHS Number**: Primary patient identifier (no local patient IDs for cross-system use)

**Interoperability Standards**:
- FHIR R4 for clinical data exchange
- HL7v2 where legacy integration required (with migration plan to FHIR)
- NHS Data Dictionary for terminology
- SNOMED CT for clinical coding
- dm+d for medications

**Validation Gates**:
- [ ] NHS Spine integration using approved connection methods
- [ ] NHS Login implemented for patient authentication
- [ ] GP Connect integration certified
- [ ] FHIR R4 compliance validated
- [ ] NHS Number used as primary patient identifier
- [ ] MESH configured for secure file transfer

---

### 5. Security by Design (NON-NEGOTIABLE)

**Principle Statement**:
All architectures MUST implement defense-in-depth security with zero-trust principles. Security is NOT a feature to be added later - it is a foundational requirement for handling NHS patient data.

**Rationale**:
Patient health data is special category data under UK GDPR. NHS DSPT compliance is mandatory. The threat landscape requires assuming breach and continuously verifying all access.

**Zero Trust Pillars**:
1. **Identity-Based Access**: No network-based trust; every request authenticated via NHS Identity or equivalent
2. **Least Privilege**: Grant minimum necessary permissions, role-based access for clinical vs administrative users
3. **Encryption Everywhere**: Data encrypted in transit (TLS 1.2+) and at rest (AES-256 or equivalent)
4. **Continuous Verification**: Monitor, log, and analyze all access to patient data

**Mandatory Controls**:
- [ ] Multi-factor authentication for all staff access
- [ ] NHS Login for patient authentication
- [ ] Service-to-service authentication (mutual TLS, signed tokens)
- [ ] Secrets management via secure vault (never in code or config)
- [ ] Network segmentation with minimal trust zones
- [ ] Encryption at rest for all patient data
- [ ] Encrypted transport for all network communication (TLS 1.2+)
- [ ] Structured audit logging of all patient data access
- [ ] Annual penetration testing by CHECK-approved provider
- [ ] Vulnerability scanning with 30-day remediation SLA

**Compliance Frameworks**:
- NHS Data Security and Protection Toolkit (DSPT) - MANDATORY
- NCSC Cyber Assessment Framework (CAF)
- ISO 27001 (recommended)
- Cyber Essentials Plus (minimum)

**Exceptions**:
- NONE. Security principles are non-negotiable for NHS services.
- Specific control implementations may vary with compensating controls approved by Clinical Safety Officer.

**Validation Gates**:
- [ ] Threat model completed and reviewed
- [ ] DSPT self-assessment completed
- [ ] Penetration testing passed (CHECK-approved provider)
- [ ] Security controls mapped to DSPT requirements
- [ ] Incident response runbook created and tested
- [ ] Data breach notification process documented (<72 hours ICO notification)

---

### 6. Observability and Operational Excellence

**Principle Statement**:
All systems MUST emit structured telemetry (logs, metrics, traces) enabling real-time monitoring, clinical incident investigation, and capacity planning.

**Rationale**:
Healthcare services require comprehensive audit trails for clinical safety investigations and regulatory compliance. We cannot operate what we cannot observe.

**Telemetry Requirements**:
- **Logging**: Structured logs with correlation IDs, patient identifiers (pseudonymised for analysis)
- **Metrics**: Request volume, latency percentiles (p50, p95, p99), error rates, booking success rates
- **Tracing**: Distributed trace context for request flows across NHS integrations
- **Alerting**: Service Level Objective (SLO)-based alerting with actionable runbooks

**Healthcare-Specific Instrumentation**:
- Appointment booking success/failure rates by practice
- NHS Spine/GP Connect availability and latency
- Patient journey completion rates
- Clinical safety incidents requiring investigation
- Data access audit trails (who accessed what patient data when)

**Log Retention** (NHS/DSPT Requirements):
- **Audit logs**: 8 years minimum (NHS Records Management Code)
- **Security logs**: 2 years minimum
- **Application logs**: 90 days for troubleshooting
- **Metrics**: 2 years with aggregation for trend analysis

**Validation Gates**:
- [ ] Logging, metrics, tracing instrumented
- [ ] Audit trail captures all patient data access
- [ ] Dashboards for booking success rates and system health
- [ ] SLOs defined: 99.9% availability, <2s booking response time
- [ ] Runbooks created for common failure scenarios
- [ ] Log retention meets NHS Records Management Code

---

## II. Data Principles

### 7. Patient Data Protection (UK GDPR Special Category)

**Principle Statement**:
Patient health data MUST be processed lawfully with explicit legal basis, stored securely within UK jurisdiction, and retained only for the minimum necessary period.

**Rationale**:
Health data is special category data under UK GDPR Article 9. Processing requires explicit legal basis and enhanced protection. ICO enforcement and patient trust require exemplary data handling.

**Legal Basis for Processing**:
- Explicit consent for appointment booking
- Healthcare provision (GDPR Art 9(2)(h)) for clinical data
- Public health (GDPR Art 9(2)(i)) for aggregate reporting
- Legal obligation for statutory reporting

**Data Minimisation**:
- Collect only data necessary for appointment booking
- Do not retain clinical notes longer than necessary
- Pseudonymise data for analytics and reporting
- Delete data when retention period expires

**Data Residency**:
- Patient data MUST remain within UK jurisdiction
- No transfer to third countries without adequacy decision or appropriate safeguards
- Cloud hosting must guarantee UK data residency

**Validation Gates**:
- [ ] Legal basis documented for each data processing activity
- [ ] Privacy notices published and accessible
- [ ] Data minimisation applied to all collections
- [ ] UK data residency confirmed for all patient data
- [ ] DPIA completed for high-risk processing
- [ ] Subject access request process documented (<30 days response)

---

### 8. Data Quality and Lineage

**Principle Statement**:
Patient data MUST maintain accuracy, completeness, and consistency with NHS Spine as the authoritative source for demographics.

**Rationale**:
Incorrect patient data in healthcare can lead to clinical safety incidents. NHS Spine is the authoritative source for patient demographics; local copies must synchronise.

**Quality Standards**:
- **Accuracy**: NHS Number validated against PDS before booking
- **Completeness**: Mandatory fields enforced (NHS Number, DOB, contact details)
- **Consistency**: Demographics synchronised with PDS, not manually maintained
- **Timeliness**: PDS lookup performed for each booking session

**NHS Spine as Source of Truth**:
- Patient demographics (name, address, DOB, GP registration) from PDS
- Local caches refreshed at each patient interaction
- No manual override of PDS data without clinical justification

**Validation Gates**:
- [ ] NHS Number validated against PDS for all patients
- [ ] Demographics synchronised from PDS, not manually entered
- [ ] Data quality rules automated (format validation, mandatory fields)
- [ ] Data lineage documented for all patient data flows
- [ ] Schema changes require clinical safety review

---

### 9. Consent Management

**Principle Statement**:
Patient consent MUST be captured, stored, and enforced for all optional data processing. Patients MUST be able to view and withdraw consent at any time.

**Rationale**:
UK GDPR requires explicit consent for processing beyond direct healthcare provision. Patients have the right to control how their data is used.

**Consent Categories**:
- **Appointment booking**: Required for service delivery
- **SMS/Email reminders**: Explicit opt-in consent required
- **Research/Analytics**: Separate explicit consent
- **Third-party sharing**: Explicit consent with named recipients

**Consent Requirements**:
- Granular consent (separate consent per processing purpose)
- Freely given (no bundling, no detriment for refusal)
- Recorded with timestamp and version of consent text
- Withdrawal mechanism accessible and effective
- Consent refresh for material changes

**Validation Gates**:
- [ ] Consent captured for all optional processing
- [ ] Consent records include timestamp, version, and mechanism
- [ ] Withdrawal mechanism implemented and tested
- [ ] Consent enforced at point of processing
- [ ] Annual consent audit conducted

---

## III. Integration Principles

### 10. Loose Coupling with NHS Systems

**Principle Statement**:
Systems MUST be loosely coupled through published NHS Digital APIs, avoiding direct database access or proprietary integrations that create lock-in.

**Rationale**:
NHS systems evolve independently. Loose coupling through standard APIs enables resilience, replaceability, and compliance with NHS Digital integration patterns.

**Implications**:
- Use NHS Digital approved APIs (FHIR, GP Connect, NHS Login)
- No direct database access to GP clinical systems
- Each system manages its own data lifecycle
- Avoid distributed transactions across NHS boundaries
- Cache NHS Spine data locally with defined TTL

**NHS Integration Anti-Patterns (PROHIBITED)**:
- Direct database queries to external systems
- Proprietary APIs that bypass NHS Digital approval
- Tight coupling to specific GP system vendor
- Storing NHS data without authorisation

**Validation Gates**:
- [ ] NHS Digital API patterns used for all integrations
- [ ] No direct database coupling to external systems
- [ ] Each integration has defined failure mode
- [ ] Vendor lock-in assessment completed
- [ ] Integration changes don't require coordinated deployment

---

### 11. Asynchronous Communication for Non-Critical Flows

**Principle Statement**:
Systems SHOULD use asynchronous communication for appointment reminders, notifications, and batch processes to improve resilience.

**Rationale**:
Asynchronous patterns reduce temporal coupling with NHS systems and external gateways (SMS, email), improving fault tolerance.

**Asynchronous Flows**:
- Appointment reminder notifications (SMS, email)
- Appointment confirmation messages
- MESH file transfers to/from GP systems
- Reporting and analytics aggregation
- Audit log processing

**Synchronous Flows** (where immediate response required):
- Patient authentication (NHS Login)
- Appointment availability lookup (real-time)
- Booking confirmation (patient must see immediate result)
- Payment processing (if applicable)

**Validation Gates**:
- [ ] Notifications use asynchronous patterns
- [ ] Message durability and delivery guarantees defined
- [ ] Dead letter queues configured for failed messages
- [ ] Retry policies documented for each async flow
- [ ] MESH integration tested for reliability

---

## IV. Healthcare-Specific Principles

### 12. Clinical Safety (DCB0129/DCB0160)

**Principle Statement**:
All systems MUST comply with DCB0129 (manufacturer) and DCB0160 (deployer) clinical safety standards, with identified Clinical Safety Officer and hazard log.

**Rationale**:
NHS England mandates clinical safety standards for all health IT systems. Clinical safety failures can result in patient harm.

**Clinical Safety Requirements**:
- Clinical Safety Management System documented
- Clinical Safety Officer (CSO) appointed with authority
- Clinical Risk Management File maintained
- Hazard log with risk assessment for all identified hazards
- Safety case documented and approved

**Hazard Categories for Appointment Systems**:
- Patient books appointment with wrong clinician type
- Appointment booking lost or duplicated
- Patient receives incorrect appointment details
- Urgent appointment delayed due to system failure
- Patient identity confusion (wrong patient record)

**Clinical Safety Process**:
1. Hazard identification during design
2. Risk assessment (severity x likelihood)
3. Mitigation controls implemented
4. Residual risk accepted by CSO
5. Post-deployment safety monitoring

**Validation Gates**:
- [ ] Clinical Safety Officer appointed
- [ ] Hazard log created and maintained
- [ ] Clinical Risk Management File complete
- [ ] Safety case reviewed and approved
- [ ] Post-deployment safety monitoring in place
- [ ] Clinical safety incidents reported and investigated

---

### 13. Accessibility (WCAG 2.2 AA - MANDATORY)

**Principle Statement**:
All patient-facing interfaces MUST meet WCAG 2.2 Level AA accessibility standards. Public sector services have legal obligation under Equality Act 2010.

**Rationale**:
Public sector websites must be accessible under The Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018. Many patients have disabilities, visual impairments, or motor difficulties.

**Accessibility Requirements**:
- Screen reader compatibility (semantic HTML, ARIA labels)
- Keyboard navigation for all functionality
- Colour contrast ratios meeting AA standards
- Resizable text without loss of functionality
- Form error identification and suggestions
- Clear, simple language (reading age appropriate)

**NHS-Specific Accessibility**:
- Large text option for elderly patients
- High contrast mode for visual impairments
- Voice input support where possible
- British Sign Language (BSL) video content for key journeys
- Easy Read versions for patients with learning disabilities

**Validation Gates**:
- [ ] WCAG 2.2 AA compliance tested (automated + manual)
- [ ] Screen reader testing completed (NVDA, JAWS, VoiceOver)
- [ ] Keyboard-only navigation tested
- [ ] Accessibility statement published
- [ ] User testing with disabled users completed
- [ ] Annual accessibility audit scheduled

---

### 14. NHS Service Standard Compliance (GDS)

**Principle Statement**:
The service MUST meet all 14 points of the GDS Service Standard, passing assessment at Alpha, Beta, and Live phases.

**Rationale**:
NHS services must pass GDS Service Standard assessments before going live. The Service Standard ensures services are user-centered, secure, and reliable.

**Service Standard Points**:
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

**Validation Gates**:
- [ ] Alpha assessment passed
- [ ] Beta assessment passed
- [ ] Live assessment passed
- [ ] Performance dashboard published
- [ ] Source code in open repository
- [ ] GOV.UK Design System components used

---

## V. Quality Attributes

### 15. Performance for Healthcare Demand

**Principle Statement**:
All systems MUST meet defined performance targets under peak NHS demand with efficient use of resources.

**Performance Targets**:
- **Appointment search**: <2 seconds p95 latency
- **Booking confirmation**: <3 seconds p95 latency
- **Page load**: <3 seconds on 3G connection
- **Throughput**: 1000 bookings per minute at peak
- **Concurrent users**: 10,000 simultaneous users

**NHS Peak Demand Patterns**:
- Monday 8:00-8:30am: 10x normal booking volume
- September: Back-to-school health appointments
- October-November: Flu vaccination campaigns
- January: New Year health resolutions
- Pandemic response: Unpredictable surge

**Validation Gates**:
- [ ] Performance requirements defined with measurable targets
- [ ] Load testing performed at 10x normal capacity
- [ ] Monday morning surge simulated and passed
- [ ] Performance monitoring continuous in production
- [ ] Capacity planning model reviewed quarterly

---

### 16. Availability for Critical Healthcare Service

**Principle Statement**:
Appointment booking MUST be available 99.9% of the time with automated recovery and zero appointment data loss.

**Availability Targets**:
- **Uptime SLA**: 99.9% (43.8 minutes downtime per month maximum)
- **Recovery Time Objective (RTO)**: <1 hour
- **Recovery Point Objective (RPO)**: Zero data loss for appointments
- **Planned maintenance**: Outside core hours (10pm-6am)

**NHS Availability Considerations**:
- 24/7 availability for online booking
- Patients expect appointments to persist across sessions
- Integration with GP systems during practice hours
- Graceful degradation if NHS Spine unavailable

**Validation Gates**:
- [ ] 99.9% availability SLA defined and monitored
- [ ] RTO <1 hour demonstrated through DR testing
- [ ] RPO zero data loss for appointments
- [ ] Failover tested quarterly
- [ ] Backup and restore tested monthly
- [ ] Incident response tested annually

---

## VI. Development Practices

### 17. Infrastructure as Code

**Principle Statement**:
All infrastructure MUST be defined as code, version-controlled, and deployed through automated pipelines with full audit trail.

**Rationale**:
NHS services require auditable, repeatable infrastructure deployment. Manual changes create compliance gaps and operational risk.

**Implications**:
- All infrastructure defined in declarative code
- Infrastructure changes require code review
- Environments reproducible from code
- No manual changes to production infrastructure
- Infrastructure versioned alongside application code
- Change audit trail for NHS Digital governance

**Validation Gates**:
- [ ] Infrastructure defined as code
- [ ] Infrastructure code version-controlled
- [ ] Automated deployment pipeline for infrastructure
- [ ] No manual infrastructure changes in production
- [ ] Audit trail for all infrastructure changes

---

### 18. Automated Testing with Clinical Safety Coverage

**Principle Statement**:
All code changes MUST be validated through automated testing including clinical safety scenarios before deployment.

**Test Pyramid**:
- **Unit Tests**: 80%+ code coverage
- **Integration Tests**: NHS API integration scenarios
- **End-to-End Tests**: Critical patient booking journeys
- **Clinical Safety Tests**: Hazard mitigation verification

**Required Test Types**:
- Functional tests (booking flows work correctly)
- Performance tests (meets latency targets)
- Security tests (OWASP Top 10, DSPT controls)
- Accessibility tests (automated WCAG checks)
- Clinical safety tests (hazard scenarios prevented)

**Validation Gates**:
- [ ] Automated tests pass before merge
- [ ] 80%+ unit test coverage
- [ ] Critical patient journeys have E2E tests
- [ ] Clinical safety scenarios tested
- [ ] Accessibility automated checks pass
- [ ] Security scan with no critical vulnerabilities

---

### 19. Continuous Deployment with NHS Change Control

**Principle Statement**:
All deployments MUST go through automated pipelines with appropriate change control for NHS clinical systems.

**Pipeline Stages**:
1. **Source Control**: All changes committed to version control
2. **Build**: Automated compilation and packaging
3. **Test**: Automated test execution (functional, security, accessibility)
4. **Security Scan**: Dependency and code vulnerability scanning
5. **Staging**: Deployment to staging environment
6. **Change Approval**: CAB approval for production changes
7. **Production**: Automated deployment with rollback capability

**NHS Change Control**:
- Standard changes: Automated deployment with post-change verification
- Normal changes: CAB approval required
- Emergency changes: Expedited approval with retrospective review
- Clinical safety changes: CSO approval required

**Validation Gates**:
- [ ] Automated CI/CD pipeline exists
- [ ] Pipeline includes security and accessibility scanning
- [ ] Change control process documented and followed
- [ ] Rollback capability tested
- [ ] Deployment audit trail maintained

---

## VII. Exception Process

### Requesting Architecture Exceptions

Principles are mandatory unless a documented exception is approved by the Enterprise Architecture Review Board and, where applicable, the Clinical Safety Officer.

**Valid Exception Reasons**:
- NHS Digital mandated integration approach differs
- Legacy GP system integration constraints
- Transitional state during migration from existing service
- Clinical safety consideration requiring deviation
- Pilot/proof-of-concept with defined end date

**Exception Request Requirements**:
- [ ] Justification with business/technical/clinical rationale
- [ ] Alternative approach and compensating controls
- [ ] Risk assessment including clinical safety impact
- [ ] CSO review if patient safety affected
- [ ] Expiration date (exceptions are time-bound, max 12 months)
- [ ] Remediation plan to achieve compliance

**Approval Process**:
1. Submit exception request to Enterprise Architecture team
2. Clinical Safety Officer review (if patient safety affected)
3. Review by architecture review board
4. CTO approval for exceptions to critical principles
5. Document exception in project architecture documentation
6. Quarterly review of all active exceptions

---

## VIII. Governance and Compliance

### Architecture Review Gates

All projects must pass architecture reviews at GDS Service Standard milestones:

**Discovery**:
- [ ] Architecture principles understood by team
- [ ] High-level approach aligns with principles
- [ ] NHS integration requirements identified
- [ ] No obvious principle violations

**Alpha Assessment**:
- [ ] Detailed architecture documented
- [ ] NHS Spine/GP Connect integration designed
- [ ] Clinical safety hazards identified
- [ ] Accessibility approach validated
- [ ] Exceptions requested and approved

**Beta Assessment**:
- [ ] Implementation matches approved architecture
- [ ] All validation gates passed
- [ ] Clinical Risk Management File complete
- [ ] DSPT self-assessment completed
- [ ] Accessibility testing passed

**Live Assessment**:
- [ ] Production deployment architecture validated
- [ ] Operational readiness verified
- [ ] Clinical safety sign-off obtained
- [ ] Security penetration testing passed
- [ ] Performance under load validated

### Enforcement

- Architecture reviews are **mandatory** for NHS Digital service assessments
- Principle violations must be remediated before production deployment
- Clinical safety violations are escalated to Clinical Safety Officer immediately
- Approved exceptions are time-bound (max 12 months) and reviewed quarterly
- Post-live compliance audits conducted annually

---

## IX. Appendix

### Principle Summary Checklist

| # | Principle | Category | Criticality | NHS Specific |
|---|-----------|----------|-------------|--------------|
| 1 | User-Centered Design | Strategic | HIGH | GDS Service Standard |
| 2 | Scalability and Elasticity | Strategic | HIGH | Monday morning surge |
| 3 | Resilience and Fault Tolerance | Strategic | CRITICAL | NHS Spine resilience |
| 4 | NHS Interoperability | Strategic | CRITICAL | FHIR, GP Connect, MESH |
| 5 | Security by Design | Strategic | CRITICAL | DSPT, special category data |
| 6 | Observability | Strategic | HIGH | Audit trails, 8-year retention |
| 7 | Patient Data Protection | Data | CRITICAL | UK GDPR, special category |
| 8 | Data Quality and Lineage | Data | HIGH | PDS as source of truth |
| 9 | Consent Management | Data | HIGH | Granular patient consent |
| 10 | Loose Coupling | Integration | HIGH | NHS Digital APIs |
| 11 | Asynchronous Communication | Integration | MEDIUM | Notifications, MESH |
| 12 | Clinical Safety | Healthcare | CRITICAL | DCB0129/DCB0160 |
| 13 | Accessibility | Healthcare | CRITICAL | WCAG 2.2 AA mandatory |
| 14 | NHS Service Standard | Healthcare | CRITICAL | GDS 14 points |
| 15 | Performance | Quality | HIGH | 10x surge capacity |
| 16 | Availability | Quality | CRITICAL | 99.9%, zero data loss |
| 17 | Infrastructure as Code | DevOps | HIGH | Audit trail |
| 18 | Automated Testing | DevOps | HIGH | Clinical safety tests |
| 19 | Continuous Deployment | DevOps | HIGH | NHS change control |

### Compliance Framework Mapping

| Framework | Principles Addressed |
|-----------|---------------------|
| NHS DSPT | 5, 6, 7, 8, 9, 17 |
| GDS Service Standard | 1, 13, 14 |
| DCB0129/DCB0160 | 12, 18 |
| UK GDPR | 7, 8, 9 |
| WCAG 2.2 AA | 13 |
| NCSC CAF | 5, 6, 17 |

### Related Documents

- `DEPENDENCY-MATRIX.md` - Command dependency order
- `WORKFLOW-DIAGRAMS.md` - Architecture workflow visualisation
- NHS Digital Integration Standards
- GDS Service Standard documentation
- DCB0129/DCB0160 Clinical Safety Standards

---

**Generated by**: ArcKit `/arckit.principles` command
**Generated on**: 2026-01-28
**ArcKit Version**: 1.0.0
**Project**: Doctors Online Appointment System (Global)
**AI Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
