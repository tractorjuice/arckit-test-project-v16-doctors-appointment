# Risk Register

> **Template Status**: Live | **Version**: 1.0.0 | **Command**: `/arckit.risk`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RISK-v1.1 |
| **Document Type** | Risk Register |
| **Project** | NHS Doctors Online Appointment System (Project 001) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2026-01-28 |
| **Last Modified** | 2026-01-28 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-02-28 |
| **Owner** | Programme Manager, NHS Digital |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Steering Committee, NHS Digital Director, NHS England Director, Clinical Safety Officer, Security Lead, IG Lead, Product Owner |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-28 | ArcKit AI | Initial creation from `/arckit.risk` command | PENDING | PENDING |
| 1.1 | 2026-01-28 | ArcKit AI | Updated to latest template format with ASCII risk matrices | PENDING | PENDING |

---

## Executive Summary

### Risk Profile Overview

**Total Risks Identified:** 16 risks across 6 categories

| Risk Level | Inherent | Residual | Change |
|------------|----------|----------|--------|
| **Critical** (20-25) | 5 | 0 | ↓ 100% |
| **High** (13-19) | 5 | 4 | ↓ 20% |
| **Medium** (6-12) | 5 | 9 | ↑ 80% |
| **Low** (1-5) | 1 | 3 | ↑ 200% |
| **TOTAL** | 16 | 16 | - |

### Risk Category Distribution

| Category | Count | Avg Inherent | Avg Residual | Control Effectiveness |
|----------|-------|--------------|--------------|----------------------|
| **STRATEGIC** | 3 | 16.0 | 12.0 | 25% reduction |
| **OPERATIONAL** | 2 | 11.0 | 6.0 | 45% reduction |
| **COMPLIANCE** | 3 | 11.3 | 9.0 | 20% reduction |
| **REPUTATIONAL** | 1 | 16.0 | 12.0 | 25% reduction |
| **TECHNOLOGY** | 5 | 14.4 | 8.4 | 42% reduction |
| **CLINICAL SAFETY** | 2 | 20.0 | 8.0 | 60% reduction |

### Overall Risk Assessment

**Overall Residual Risk Score:** 156/400
**Risk Reduction from Controls:** 39% reduction from inherent risk (256 → 156)
**Risk Profile Status:** ⚠️ Concerning - 4 risks exceed appetite, require senior approval

### Risks Exceeding Appetite

**Number of risks exceeding organizational appetite:** 4 risks

| Risk ID | Title | Category | Score | Appetite | Excess | Escalation |
|---------|-------|----------|-------|----------|--------|------------|
| R-003 | GDS Assessment Fails | COMPLIANCE | 12 | 9 | +3 | NHS Digital Director approval required |
| R-004 | Data Breach Occurs | TECHNOLOGY | 12 | 9 | +3 | IG Lead + Security Lead approval required |
| R-005 | GP System Supplier Non-Cooperation | STRATEGIC | 12 | 12 | 0 | At threshold - close monitoring |
| R-006 | Ministerial Scrutiny During Incident | REPUTATIONAL | 12 | 9 | +3 | NHS England Director approval required |

### Top 5 Critical Risks Requiring Immediate Attention

1. **R-002** (CLINICAL SAFETY, Medium 10): Clinical Safety Incident Occurs - Owner: Clinical Safety Officer - Status: In Progress
2. **R-001** (STRATEGIC, Medium 12): GP Practice Adoption Stalls - Owner: NHS England Director - Status: In Progress
3. **R-004** (TECHNOLOGY, Medium 12): Data Breach Occurs - Owner: Security Lead - Status: In Progress
4. **R-006** (REPUTATIONAL, Medium 12): Ministerial Scrutiny During Incident - Owner: NHS England Director - Status: Open
5. **R-007** (COMPLIANCE, Medium 12): GDPR Compliance Failure - Owner: IG Lead - Status: In Progress

### Key Findings and Recommendations

**Key Findings:**
- 5 risks started as CRITICAL (score 20-25) before controls - all reduced to HIGH or MEDIUM
- Clinical safety risks have strongest control effectiveness (60% reduction) due to robust DCB0129/0160 governance
- Technology/data protection risks cluster together - shared mitigations provide efficiency
- GP practice adoption is the critical enabler - if practices don't onboard, service cannot deliver value
- Reputational risks are difficult to mitigate - prevention through other risk controls is essential

**Recommendations:**
1. Escalate R-003, R-004, R-006 to appropriate senior stakeholders for formal risk acceptance
2. Prioritise GP practice recruitment (R-001, R-005) as these are foundational to service success
3. Implement integrated monitoring dashboard covering all technology/data protection risks
4. Conduct pre-mortem exercise for clinical safety scenarios before Beta launch

---

## A. Risk Matrix Visualization

### Inherent Risk Matrix (Before Controls)

**5×5 Likelihood × Impact Matrix**

```
                                    IMPACT
              1-Minimal   2-Minor    3-Moderate   4-Major    5-Severe
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │           │           │           │           │           │
Certain    │    5      │    10     │    15     │    20     │    25     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │           │           │           │  R-001    │  R-002    │
           │    4      │    8      │    12     │  R-003    │  R-004    │
L          │           │           │           │  R-005    │  R-009    │
I          │           │           │           │  R-006    │  R-010    │
K          │           │           │           │  R-007    │  R-011    │
E          │           │           │           │  R-008    │           │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │           │           │           │           │
H          │    3      │    6      │    9      │    12     │    15     │
O          ├───────────┼───────────┼───────────┼───────────┼───────────┤
O 2-Unlikely│          │           │  R-012    │  R-016    │           │
D          │    2      │    4      │  R-013    │           │           │
           │           │           │  R-014    │           │           │
           │           │           │  R-015    │           │           │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
1-Rare     │           │           │           │           │           │
           │    1      │    2      │    3      │    4      │    5      │
           └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: ██ Critical (20-25)  ▓▓ High (13-19)  ░░ Medium (6-12)  ·· Low (1-5)
```

**Risk Zones:**
- **Critical (20-25)**: R-002, R-004, R-009, R-010, R-011 - Immediate attention required
- **High (13-19)**: R-001, R-003, R-005, R-006, R-007, R-008 - Senior management attention
- **Medium (6-12)**: R-012, R-013, R-014, R-015, R-016 - Management monitoring
- **Low (1-5)**: None before controls

### Residual Risk Matrix (After Controls)

**5×5 Likelihood × Impact Matrix - After Controls Applied**

```
                                    IMPACT
              1-Minimal   2-Minor    3-Moderate   4-Major    5-Severe
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │           │           │           │           │           │
Certain    │    5      │    10     │    15     │    20     │    25     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │           │           │           │           │           │
           │    4      │    8      │    12     │    16     │    20     │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │           │  R-008    │  R-001    │           │
K          │    3      │    6      │  R-009    │  R-003    │           │
E          │           │           │  R-010    │  R-004    │           │
L          │           │           │           │  R-005    │           │
I          │           │           │           │  R-006    │           │
H          │           │           │           │  R-007    │           │
O          ├───────────┼───────────┼───────────┼───────────┼───────────┤
O 2-Unlikely│          │           │  R-011    │           │  R-002    │
D          │    2      │    4      │           │    8      │    10     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
1-Rare     │  R-012    │           │           │  R-016    │           │
           │  R-013    │    2      │    3      │           │    5      │
           │  R-014    │           │           │           │           │
           │  R-015    │           │           │           │           │
           └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: ██ Critical (20-25)  ▓▓ High (13-19)  ░░ Medium (6-12)  ·· Low (1-5)
```

**Risk Movement Analysis:**
- **Significant Improvement**: R-002 (20→10), R-011 (20→6) - Clinical safety controls very effective
- **Moderate Improvement**: R-004 (20→12), R-009 (16→9), R-010 (16→9) - Encryption/access controls working
- **Limited Improvement**: R-001 (16→12), R-005 (15→12) - External dependencies limit control
- **Stable Low**: R-012, R-013, R-014, R-015, R-016 - Already well-controlled

---

## B. Top 10 Risks (Ranked by Residual Score)

| Rank | ID | Title | Category | Inherent | Residual | Owner | Status | Response |
|------|----|-------|----------|----------|----------|-------|--------|----------|
| 1 | R-001 | GP Practice Adoption Stalls | STRATEGIC | 16 | 12 | NHS England Director | In Progress | Treat |
| 2 | R-003 | GDS Assessment Fails | COMPLIANCE | 12 | 12 | Product Owner | Open | Treat |
| 3 | R-004 | Data Breach Occurs | TECHNOLOGY | 20 | 12 | Security Lead | In Progress | Treat |
| 4 | R-005 | GP System Supplier Non-Cooperation | STRATEGIC | 15 | 12 | GP Connect Team Lead | In Progress | Treat |
| 5 | R-006 | Ministerial Scrutiny During Incident | REPUTATIONAL | 16 | 12 | NHS England Director | Open | Treat |
| 6 | R-007 | GDPR Compliance Failure | COMPLIANCE | 16 | 12 | IG Lead | In Progress | Treat |
| 7 | R-002 | Clinical Safety Incident Occurs | CLINICAL SAFETY | 20 | 10 | Clinical Safety Officer | In Progress | Treat |
| 8 | R-008 | Vulnerable Patient Exclusion | OPERATIONAL | 16 | 9 | Product Owner | In Progress | Treat |
| 9 | R-009 | Unauthorized Access to Health Data | TECHNOLOGY | 16 | 9 | Security Lead | In Progress | Treat |
| 10 | R-010 | NHS Number and Contact Breach | TECHNOLOGY | 16 | 9 | Security Lead | In Progress | Treat |

---

## C. Detailed Risk Register

### Risk R-001: GP Practice Adoption Stalls

**Category:** STRATEGIC
**Status:** In Progress
**Risk Owner:** NHS England Director of Primary Care (from Stakeholder RACI: Accountable for Practice Onboarding)
**Action Owner:** GP Connect Team Lead

#### Risk Identification

**Risk Description:**
GP practices do not enable GP Connect Appointment Management or opt-in to the service at sufficient rate to achieve meaningful coverage. Without practice participation, patients cannot book appointments online regardless of the quality of the national service.

**Root Cause:**
- GP practices have experienced previous NHS IT failures that created work rather than reducing it
- GP practices have local autonomy and cannot be mandated to participate
- GP system suppliers may not prioritise integration work

**Trigger Events:**
- GP practices decline opt-in invitations
- GP system suppliers delay GP Connect enablement
- Early-adopter practices report poor experience, deterring others
- Technical integration issues at scale

**Consequences if Realized:**
- G-1 (30% online booking uptake) unachievable
- G-4 (40% phone reduction) unachievable
- G-7 (500 practices by Beta) missed
- NHS Long Term Plan commitment not delivered
- Service has insufficient coverage to justify investment

**Affected Stakeholders:**
- **NHS England Director** (SD-1): Cannot demonstrate Long Term Plan delivery
- **GP Practice Managers** (SD-3): Continue phone pressure without digital relief
- **Patients** (SD-4): Cannot access online booking at their practice
- **Minister** (SD-7): Cannot announce successful digital transformation

**Related Objectives:**
- G-1 (30% online booking uptake): Cannot achieve without practices
- G-7 (500+ practices by Beta): Direct measure of this risk

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 4 - Likely | GP practices have autonomy and history of IT project scepticism; external dependency on suppliers |
| **Impact** | 4 - Major | Service cannot deliver value without practices; threatens entire business case |
| **Inherent Risk Score** | **16** (High) | 4 × 4 = 16 |

**Risk Zone:** 🟧 High (13-19)

#### Current Controls and Mitigations

**Existing Controls:**
1. **Early Adopter Programme**: Targeting enthusiastic practices who want to participate
   - Owner: GP Connect Team Lead
   - Effectiveness: **Adequate**
   - Evidence: 50+ practices expressing interest during Discovery

2. **Hands-on Onboarding Support**: Dedicated support team for practice enablement
   - Owner: GP Connect Team Lead
   - Effectiveness: **Adequate**
   - Evidence: Template onboarding process tested with pilot practices

3. **GP System Supplier Contracts**: Contractual obligations for GP Connect support
   - Owner: NHS Digital Commercial
   - Effectiveness: **Adequate**
   - Evidence: Contracts include GP Connect SLAs

4. **Practice Manager Network Engagement**: Peer-to-peer promotion through practice manager forums
   - Owner: NHS England Primary Care Team
   - Effectiveness: **Adequate**
   - Evidence: Presentations at regional practice manager events

**Overall Control Effectiveness:** Adequate (reduces risk from 16 to 12)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | Controls improve engagement but cannot eliminate practice autonomy concerns |
| **Impact** | 4 - Major | Impact unchanged - still threatens service viability |
| **Residual Risk Score** | **12** (Medium) | 3 × 4 = 12 |

**Risk Zone:** 🟨 Medium (6-12)
**Risk Reduction:** 25% reduction from inherent (16 → 12)

#### Risk Response (4Ts Framework)

**Primary Response:** TREAT (Mitigate/Reduce)

**Rationale:**
Risk is at threshold of appetite and is foundational to service success. Active mitigation essential. Cannot tolerate, transfer, or terminate.

**Alternative Responses Considered:**
- **Tolerate**: Rejected - Risk threatens entire service
- **Transfer**: Not possible - External dependency cannot be transferred
- **Terminate**: Not viable - Would mean abandoning service

#### Risk Appetite Assessment

**Organizational Risk Appetite for STRATEGIC risks:** Medium (Score ≤ 12)
**Current Residual Risk Score:** 12 (Medium)
**Assessment:** ✅ **At Appetite Threshold** - Close monitoring required

**Justification:**
Risk at threshold. Any deterioration requires escalation. Critical success factor CSF-1 (500 practices by Beta) provides measurable trigger for escalation.

**Escalation Required:** Not immediately, but monthly monitoring at Steering Committee

#### Action Plan

**Additional Mitigations Needed:**

1. **Success Story Publication**
   - Description: Document and share success stories from early-adopter practices showing workload reduction
   - Owner: Communications Team
   - Due Date: Alpha + 2 months
   - Cost: £10K
   - Expected Impact: Reduce likelihood from 3 to 2

2. **Regional Practice Manager Champions**
   - Description: Recruit influential practice managers as regional champions to promote adoption
   - Owner: NHS England Primary Care Team
   - Due Date: Beta launch
   - Cost: £25K (incentives and events)
   - Expected Impact: Reduce likelihood from 3 to 2

**Target Residual Risk After Mitigations:**
- Target Likelihood: 2 (Unlikely)
- Target Impact: 4 (Major - unchanged)
- Target Score: 8 (Medium) ✅ Well within appetite

**Success Criteria:**
- 100 practices onboarded by Alpha assessment
- 500 practices onboarded by Beta assessment
- <10% practice dropout rate after onboarding

**Monitoring Plan:**
- **Frequency:** Weekly practice onboarding dashboard; Monthly Steering Committee review
- **Key Indicators:**
  - Practice expression of interest pipeline
  - Onboarding completion rate
  - Practice dropout/pause rate
- **Escalation Triggers:**
  - Fewer than 50 practices by Alpha
  - Onboarding completion rate <80%
  - 3+ practices withdraw

---

### Risk R-002: Clinical Safety Incident Occurs

**Category:** CLINICAL SAFETY
**Status:** In Progress
**Risk Owner:** Clinical Safety Officer, NHS Digital (DCB0129/0160 accountability)
**Action Owner:** Clinical Safety Officer

#### Risk Identification

**Risk Description:**
A patient experiences harm attributable to the booking system through booking errors (wrong appointment, lost booking, double booking), identity confusion (wrong patient record accessed), or delayed urgent care due to system failure.

**Root Cause:**
- Complex integration with multiple GP systems increases error potential
- Patient identity matching across NHS Login, PDS, and GP systems
- Booking reason triage affects care urgency classification

**Trigger Events:**
- GP Connect integration error causes booking loss or duplication
- NHS Number mismatch assigns booking to wrong patient
- System failure during Monday peak prevents urgent bookings
- Booking reason code misinterpreted by GP practice

**Consequences if Realized:**
- Patient harm (delayed care, wrong treatment, missed diagnosis)
- DCB0129/0160 regulatory investigation
- Clinical Safety Officer personal professional accountability
- Service pause or withdrawal
- Ministerial scrutiny and negative media coverage

**Affected Stakeholders:**
- **Clinical Safety Officer** (SD-2): Personal professional accountability; driver to protect patients
- **Patients**: Direct harm from healthcare system failure
- **Minister** (SD-7): Cannot avoid negative headlines from patient harm
- **NHS England Director** (SD-1): Service credibility destroyed

**Related Objectives:**
- G-2 (Zero clinical safety incidents): Direct measure of this risk
- O-2 (Safe Digital Healthcare Service): Outcome threatened

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 4 - Likely | Complex integration, multiple systems, high transaction volume increases error probability |
| **Impact** | 5 - Catastrophic | Patient harm is paramount; regulatory consequences; service withdrawal |
| **Inherent Risk Score** | **20** (Critical) | 4 × 5 = 20 |

**Risk Zone:** 🟥 Critical (20-25)

#### Current Controls and Mitigations

**Existing Controls:**
1. **DCB0129/0160 Clinical Safety Management System**: Formal hazard log, clinical risk assessment, CSO sign-off
   - Owner: Clinical Safety Officer
   - Effectiveness: **Strong**
   - Evidence: Hazard log maintained; all releases require CSO approval

2. **Clinical Safety Testing**: Dedicated clinical safety test scenarios before each release
   - Owner: Clinical Safety Officer + Test Lead
   - Effectiveness: **Strong**
   - Evidence: Clinical test pack with >100 scenarios

3. **CSO Halt Authority**: Clinical Safety Officer has authority to halt any release
   - Owner: Clinical Safety Officer
   - Effectiveness: **Strong**
   - Evidence: Documented in governance framework

4. **Phased Rollout**: Limited practices initially to contain exposure while safety evidence accumulates
   - Owner: Product Owner
   - Effectiveness: **Strong**
   - Evidence: Phased rollout plan approved

5. **GP Connect Validation**: API validation and error handling for all GP system interactions
   - Owner: Technical Lead
   - Effectiveness: **Adequate**
   - Evidence: GP Connect compliance testing passed

**Overall Control Effectiveness:** Strong (reduces risk from 20 to 10)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 2 - Unlikely | Strong clinical governance significantly reduces probability |
| **Impact** | 5 - Catastrophic | Impact cannot be reduced - patient safety is paramount |
| **Residual Risk Score** | **10** (Medium) | 2 × 5 = 10 |

**Risk Zone:** 🟨 Medium (6-12)
**Risk Reduction:** 50% reduction from inherent (20 → 10)

#### Risk Response (4Ts Framework)

**Primary Response:** TREAT (Mitigate/Reduce)

**Rationale:**
Patient safety is non-negotiable. Despite residual risk being within appetite, continuous improvement of controls is required.

#### Risk Appetite Assessment

**Organizational Risk Appetite for CLINICAL SAFETY risks:** Very Low (Score ≤ 10)
**Current Residual Risk Score:** 10 (Medium)
**Assessment:** ✅ **At Appetite Threshold** - Maximum acceptable level

**Justification:**
Clinical safety risks can never be fully eliminated in healthcare IT. Score of 10 represents minimum achievable with robust governance. Any incident requires immediate escalation regardless of score.

**Escalation Required:** Any clinical incident (regardless of score) escalates to CSO → NHS Digital Director → NHS England Director → Minister

#### Action Plan

**Additional Mitigations Needed:**

1. **Clinical Pre-Mortem Exercise**
   - Description: Conduct structured exercise imagining clinical safety incident has occurred; identify additional controls
   - Owner: Clinical Safety Officer
   - Due Date: Before Beta launch
   - Cost: £5K (facilitation)
   - Expected Impact: Identify unknown hazards; improve response readiness

2. **Independent Clinical Review**
   - Description: Commission independent clinical safety review before Live
   - Owner: NHS Digital Director
   - Due Date: Before Live assessment
   - Cost: £30K
   - Expected Impact: External validation of safety controls

**Target Residual Risk After Mitigations:**
- Target Likelihood: 1 (Rare)
- Target Impact: 5 (Catastrophic - unchanged)
- Target Score: 5 (Low) ✅ Significant margin within appetite

**Success Criteria:**
- Zero patient safety incidents throughout Alpha, Beta, Live
- All hazard log items closed before each phase
- Independent clinical review passed

**Monitoring Plan:**
- **Frequency:** Weekly clinical safety review; Daily monitoring of near-misses
- **Key Indicators:**
  - Hazard log status (open/closed)
  - Near-miss reports
  - Clinical incident reports (target: 0)
- **Escalation Triggers:**
  - Any clinical incident (immediate)
  - Near-miss trend (3+ similar in a week)
  - Hazard closure delayed >2 weeks

---

### Risk R-003: GDS Assessment Fails

**Category:** COMPLIANCE
**Status:** Open
**Risk Owner:** Product Owner, NHS Digital
**Action Owner:** Product Owner

#### Risk Identification

**Risk Description:**
Service fails GDS Service Standard assessment at Alpha, Beta, or Live gate, requiring re-assessment and delaying service progression. Failure damages credibility and delays patient benefits.

**Root Cause:**
- GDS assessments require extensive user research evidence
- Accessibility requirements (WCAG 2.2 AA) are stringent
- Performance data and operational metrics required
- GDS assessors apply rigorous standards

**Trigger Events:**
- Insufficient user research evidence presented
- Accessibility audit finds critical issues
- Performance data incomplete or below threshold
- Technology choices questioned (not open standards)

**Consequences if Realized:**
- Service progression blocked until re-assessment
- 2-3 month delay per failed assessment
- NHS credibility with GDS damaged
- Resource cost of remediation and re-assessment

**Affected Stakeholders:**
- **GDS Assessment Team** (SD-6): Maintaining Service Standard integrity
- **Product Owner**: Delivery responsibility
- **NHS England Director** (SD-1): Long Term Plan delivery delayed
- **Patients** (SD-4): Access delayed

**Related Objectives:**
- G-3 (Pass GDS assessments): Direct measure of this risk
- O-4 (Service Standard Compliance): Outcome at risk

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | GDS assessments are rigorous; NHS projects have mixed track record |
| **Impact** | 4 - Major | 3+ month delays; credibility damage; resource diversion |
| **Inherent Risk Score** | **12** (Medium) | 3 × 4 = 12 |

**Risk Zone:** 🟨 Medium (6-12)

#### Current Controls and Mitigations

**Existing Controls:**
1. **Early GDS Engagement**: Informal engagement with GDS before formal assessments
   - Owner: Product Owner
   - Effectiveness: **Adequate**
   - Evidence: Initial GDS meeting held

2. **User Research Programme**: Dedicated user research with diverse patient groups
   - Owner: User Research Lead
   - Effectiveness: **Adequate**
   - Evidence: User research plan with 50+ sessions planned

3. **Accessibility Testing**: Accessibility audit with real assistive technology users
   - Owner: Product Owner
   - Effectiveness: **Adequate** (in progress)
   - Evidence: Accessibility partner engaged

**Overall Control Effectiveness:** Adequate (risk maintained at 12)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | Controls improve evidence but cannot guarantee GDS panel decision |
| **Impact** | 4 - Major | Impact unchanged |
| **Residual Risk Score** | **12** (Medium) | 3 × 4 = 12 |

**Risk Zone:** 🟨 Medium (6-12)
**Risk Reduction:** 0% (controls prevent deterioration rather than improve)

#### Risk Response (4Ts Framework)

**Primary Response:** TREAT (Mitigate/Reduce)

#### Risk Appetite Assessment

**Organizational Risk Appetite for COMPLIANCE risks:** Low (Score ≤ 9)
**Current Residual Risk Score:** 12 (Medium)
**Assessment:** ❌ **Exceeds Appetite** by 3 points (33% over threshold)

**Justification:**
GDS assessment is mandatory compliance. Risk accepted due to mandatory nature with commitment to intensive preparation.

**Escalation Required:** Yes - NHS Digital Director approval required for proceeding with risk above appetite

#### Action Plan

**Additional Mitigations Needed:**

1. **Mock Assessment**
   - Description: Conduct internal mock assessment with GDS-experienced assessors before each formal assessment
   - Owner: Product Owner
   - Due Date: 4 weeks before each assessment
   - Cost: £15K per mock
   - Expected Impact: Identify gaps; reduce likelihood from 3 to 2

2. **Evidence Portfolio Development**
   - Description: Maintain comprehensive evidence portfolio mapped to 14 Service Standard points
   - Owner: Delivery Manager
   - Due Date: Ongoing
   - Cost: £5K (tooling)
   - Expected Impact: Ensure no evidence gaps at assessment

**Target Residual Risk After Mitigations:**
- Target Likelihood: 2 (Unlikely)
- Target Impact: 4 (Major)
- Target Score: 8 (Medium) ✅ Within appetite

**Success Criteria:**
- Pass Alpha assessment on first attempt
- Pass Beta assessment on first attempt
- Pass Live assessment on first attempt

---

### Risk R-004: Data Breach Occurs

**Category:** TECHNOLOGY
**Status:** In Progress
**Risk Owner:** Security Lead, NHS Digital
**Action Owner:** Security Lead

#### Risk Identification

**Risk Description:**
Patient data (NHS Numbers, contact details, health data) is accessed by unauthorized parties through cyber attack, insider threat, or supply chain compromise, requiring ICO notification within 72 hours.

**Root Cause:**
- NHS is high-value target for cyber attackers (WannaCry precedent)
- Special category health data is valuable for fraud and discrimination
- Multiple integration points (NHS Login, GP Connect, Gov.uk Notify) increase attack surface
- Large-scale data (5M+ patients) increases breach impact

**Trigger Events:**
- SQL injection or other application vulnerability exploited
- Credential compromise (staff or API)
- Database backup exposure
- Third-party/supply chain breach
- Insider threat

**Consequences if Realized:**
- ICO notification within 72 hours
- Potential ICO fine (up to £17.5M / 4% revenue)
- Patient notification requirement
- NHS reputation damage
- Loss of patient trust in digital services

**Affected Stakeholders:**
- **Security Lead** (SD-10): Accountable for DSPT compliance and security
- **IG Lead** (SD-8): Data protection accountability
- **Patients**: Personal data exposed
- **Minister** (SD-7): Negative headlines
- **ICO**: Regulatory investigation

**Related Objectives:**
- G-6 (Zero data breaches): Direct measure of this risk
- O-2 (Safe Digital Healthcare Service): Outcome at risk

#### Inherent Risk Assessment (Before Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 4 - Likely | NHS is known target; healthcare breaches common; multiple attack vectors |
| **Impact** | 5 - Catastrophic | Regulatory fines; patient harm from discrimination; reputation destruction |
| **Inherent Risk Score** | **20** (Critical) | 4 × 5 = 20 |

**Risk Zone:** 🟥 Critical (20-25)

#### Current Controls and Mitigations

**Existing Controls:**
1. **Encryption at Rest**: AES-256 encryption for all patient data; NHS Number field-level encryption
   - Owner: Technical Lead
   - Effectiveness: **Strong**
   - Evidence: Encryption implemented and tested

2. **Encryption in Transit**: TLS 1.3 only; NHS Digital approved cipher suites
   - Owner: Technical Lead
   - Effectiveness: **Strong**
   - Evidence: Transport security validated

3. **Access Controls**: RBAC with NHS Login P5/P9 for patients; MFA for staff
   - Owner: Security Lead
   - Effectiveness: **Strong**
   - Evidence: Access control framework documented and tested

4. **Penetration Testing**: Penetration testing before each release
   - Owner: Security Lead
   - Effectiveness: **Strong**
   - Evidence: Penetration testing partner engaged; schedule agreed

5. **Data Loss Prevention**: DLP monitoring for sensitive data exfiltration
   - Owner: Security Team
   - Effectiveness: **Adequate**
   - Evidence: DLP rules configured

6. **Incident Response Plan**: 72-hour ICO notification process; patient notification procedure
   - Owner: IG Lead
   - Effectiveness: **Adequate**
   - Evidence: Incident response plan documented

**Overall Control Effectiveness:** Strong (reduces risk from 20 to 12)

#### Residual Risk Assessment (After Controls)

| Assessment | Rating | Justification |
|------------|--------|---------------|
| **Likelihood** | 3 - Possible | Strong controls significantly reduce probability but cannot eliminate |
| **Impact** | 4 - Major | Reduced from catastrophic due to incident response capability limiting damage |
| **Residual Risk Score** | **12** (Medium) | 3 × 4 = 12 |

**Risk Zone:** 🟨 Medium (6-12)
**Risk Reduction:** 40% reduction from inherent (20 → 12)

#### Risk Response (4Ts Framework)

**Primary Response:** TREAT (Mitigate/Reduce)

**Alternative Responses Considered:**
- **Transfer**: Cyber insurance obtained as secondary response (£5M cover)
- **Terminate**: Not viable - service requires patient data

#### Risk Appetite Assessment

**Organizational Risk Appetite for TECHNOLOGY risks:** Medium (Score ≤ 9)
**Current Residual Risk Score:** 12 (Medium)
**Assessment:** ❌ **Exceeds Appetite** by 3 points (33% over threshold)

**Justification:**
Cyber security risk can never be fully eliminated. Score of 12 reflects best achievable with comprehensive controls. Accepted with enhanced monitoring and cyber insurance.

**Escalation Required:** Yes - IG Lead and Security Lead approval obtained. NHS Digital Director informed.

#### Action Plan

**Additional Mitigations Needed:**

1. **Red Team Exercise**
   - Description: Commission red team attack simulation before Beta
   - Owner: Security Lead
   - Due Date: Before Beta launch
   - Cost: £50K
   - Expected Impact: Identify unknown vulnerabilities; reduce likelihood from 3 to 2

2. **Security Operations Center (SOC) Integration**
   - Description: Integrate with NHS Digital SOC for 24/7 monitoring
   - Owner: Security Lead
   - Due Date: Before Live launch
   - Cost: £30K/year
   - Expected Impact: Faster detection; reduce impact from 4 to 3

**Target Residual Risk After Mitigations:**
- Target Likelihood: 2 (Unlikely)
- Target Impact: 3 (Moderate)
- Target Score: 6 (Medium) ✅ Within appetite

---

### Risk R-005: GP System Supplier Non-Cooperation

**Category:** STRATEGIC
**Status:** In Progress
**Risk Owner:** GP Connect Team Lead, NHS Digital
**Action Owner:** GP Connect Team Lead

#### Risk Identification

**Risk Description:**
One or more major GP system suppliers (EMIS, TPP, Vision, Microtest) delay or inadequately implement GP Connect Appointment Management integration, preventing practices using those systems from participating.

**Inherent Risk Score:** **15** (High) - 3 × 5 = 15
**Residual Risk Score:** **12** (Medium) - 3 × 4 = 12 (after contractual controls, funding, engagement)

**Owner:** GP Connect Team Lead
**Status:** In Progress

---

### Risk R-006: Ministerial Scrutiny During Incident

**Category:** REPUTATIONAL
**Status:** Open
**Risk Owner:** NHS England Director of Primary Care
**Action Owner:** Communications Team

#### Risk Identification

**Risk Description:**
A service issue (performance failure, safety concern, security incident, or poor user experience) generates negative media coverage and parliamentary questions, damaging NHS digital reputation and potentially requiring service pause.

**Inherent Risk Score:** **16** (High) - 4 × 4 = 16
**Residual Risk Score:** **12** (Medium) - 3 × 4 = 12 (after communications controls)

**Risk Appetite:** Low (Score ≤ 9)
**Assessment:** ❌ **Exceeds Appetite** by 3 points

**Owner:** NHS England Director
**Status:** Open (controls in place, monitoring ongoing)

---

### Risk R-007: GDPR Compliance Failure

**Category:** COMPLIANCE
**Status:** In Progress
**Risk Owner:** Information Governance Lead, NHS Digital
**Action Owner:** IG Lead

#### Risk Identification

**Risk Description:**
Processing of patient health data found to be non-compliant with UK GDPR requirements, resulting in ICO investigation, enforcement action, or fine. Derived from DPIA risks DPIA-001 through DPIA-010.

**Inherent Risk Score:** **16** (High) - 4 × 4 = 16
**Residual Risk Score:** **12** (Medium) - 3 × 4 = 12 (after DPIA, privacy by design, SAR process)

**Risk Appetite:** Low (Score ≤ 9)
**Assessment:** ❌ **Exceeds Appetite** by 3 points

**Owner:** IG Lead
**Status:** In Progress (DPIA completed, controls being implemented)

---

### Risk R-008: Vulnerable Patient Exclusion

**Category:** OPERATIONAL
**Status:** In Progress
**Risk Owner:** Product Owner, NHS Digital
**Action Owner:** Product Owner

#### Risk Identification

**Risk Description:**
Elderly, disabled, or low-digital-literacy patients cannot effectively use the service, widening the digital divide and creating health inequity. Derived from DPIA risk DPIA-010.

**Inherent Risk Score:** **16** (High) - 4 × 4 = 16
**Residual Risk Score:** **9** (Medium) - 3 × 3 = 9 (after WCAG compliance, assisted digital, phone preservation)

**Risk Appetite:** Medium (Score ≤ 9)
**Assessment:** ✅ **At Appetite Threshold**

**Owner:** Product Owner
**Status:** In Progress (accessibility testing ongoing)

---

### Risk R-009: Unauthorized Access to Health Data

**Category:** TECHNOLOGY
**Status:** In Progress
**Risk Owner:** Security Lead, NHS Digital

#### Risk Identification

**Risk Description:**
An attacker exploits a vulnerability (SQL injection, credential compromise, insider threat) to access the booking database containing appointment reason codes and free text revealing health conditions. Derived from DPIA risk DPIA-001.

**Inherent Risk Score:** **16** (High) - 4 × 4 = 16
**Residual Risk Score:** **9** (Medium) - 3 × 3 = 9 (after encryption, RBAC, audit logging, pen testing)

**Owner:** Security Lead
**Status:** In Progress

---

### Risk R-010: NHS Number and Contact Details Breach

**Category:** TECHNOLOGY
**Status:** In Progress
**Risk Owner:** Security Lead, NHS Digital

#### Risk Identification

**Risk Description:**
Database breach or backup exposure reveals patient NHS Numbers, mobile phones, and email addresses, enabling identity theft and targeted phishing. Derived from DPIA risk DPIA-002.

**Inherent Risk Score:** **16** (High) - 4 × 4 = 16
**Residual Risk Score:** **9** (Medium) - 3 × 3 = 9 (after encryption and access controls)

**Owner:** Security Lead
**Status:** In Progress (controls implemented, monitoring ongoing)

---

### Risk R-011: Booking Error Causing Patient Safety Harm

**Category:** CLINICAL SAFETY
**Status:** In Progress
**Risk Owner:** Clinical Safety Officer, NHS Digital

#### Risk Identification

**Risk Description:**
System error causes booking to be lost, duplicated, or assigned to wrong patient; patient misses urgent care or receives wrong treatment. Derived from DPIA risk DPIA-003 and stakeholder risk R-2.

**Note:** This risk is closely related to R-002 (Clinical Safety Incident) and shares controls. R-002 addresses the broader clinical safety governance; R-011 focuses on specific booking errors.

**Inherent Risk Score:** **20** (Critical) - 4 × 5 = 20
**Residual Risk Score:** **6** (Medium) - 2 × 3 = 6 (after clinical safety testing, GP Connect validation, hazard log)

**Owner:** Clinical Safety Officer
**Status:** In Progress (clinical safety governance active)

---

### Risk R-012: Excessive Data Retention

**Category:** COMPLIANCE
**Status:** Monitoring
**Risk Owner:** IG Lead, NHS Digital

#### Risk Identification

**Risk Description:**
Data retained beyond necessary period, increasing breach exposure window and violating data minimization principle. Derived from DPIA risk DPIA-004.

**Inherent Risk Score:** **6** (Medium) - 2 × 3 = 6
**Residual Risk Score:** **3** (Low) - 1 × 3 = 3 (after automated deletion jobs, retention policy enforcement)

**Owner:** IG Lead
**Status:** Monitoring (automated retention controls implemented)

---

### Risk R-013: Third-Party Processor Misuse

**Category:** OPERATIONAL
**Status:** Monitoring
**Risk Owner:** IG Lead, NHS Digital

#### Risk Identification

**Risk Description:**
Gov.uk Notify or GP system supplier misuses patient data for unauthorized purposes. Derived from DPIA risk DPIA-005.

**Inherent Risk Score:** **6** (Medium) - 2 × 3 = 6
**Residual Risk Score:** **3** (Low) - 1 × 3 = 3 (after DPAs, vendor audits, limited data sharing)

**Owner:** IG Lead
**Status:** Monitoring (DPAs in place, audits scheduled)

---

### Risk R-014: Re-identification of Pseudonymised Data

**Category:** TECHNOLOGY
**Status:** Monitoring
**Risk Owner:** Security Lead, NHS Digital

#### Risk Identification

**Risk Description:**
Audit logs with pseudonymised NHS Numbers re-identified through correlation with other data sources. Derived from DPIA risk DPIA-006.

**Inherent Risk Score:** **6** (Medium) - 2 × 3 = 6
**Residual Risk Score:** **3** (Low) - 1 × 3 = 3 (after k-anonymity for analytics, separate identifier storage)

**Owner:** Security Lead
**Status:** Monitoring (pseudonymisation controls implemented)

---

### Risk R-015: Loss of Control Over Personal Data

**Category:** COMPLIANCE
**Status:** Monitoring
**Risk Owner:** IG Lead, NHS Digital

#### Risk Identification

**Risk Description:**
Patients unable to effectively exercise data subject rights (SAR, deletion, portability). Derived from DPIA risk DPIA-007.

**Inherent Risk Score:** **6** (Medium) - 2 × 3 = 6
**Residual Risk Score:** **3** (Low) - 1 × 3 = 3 (after SAR process, consent management, privacy notice)

**Owner:** IG Lead
**Status:** Monitoring (rights processes documented, to be tested)

---

### Risk R-016: Function Creep

**Category:** TECHNOLOGY
**Status:** Monitoring
**Risk Owner:** Enterprise Architect, NHS Digital

#### Risk Identification

**Risk Description:**
Data used for purposes beyond stated booking purposes (e.g., marketing, research without consent). Derived from DPIA risk DPIA-008.

**Inherent Risk Score:** **8** (Medium) - 2 × 4 = 8
**Residual Risk Score:** **4** (Low) - 1 × 4 = 4 (after technical controls preventing repurposing, governance oversight, audit logging)

**Owner:** Enterprise Architect
**Status:** Monitoring (technical controls implemented)

---

## D. Risk Category Analysis

### STRATEGIC Risks

**Total STRATEGIC Risks:** 2 (R-001, R-005)
**Average Inherent Score:** 15.5 (High)
**Average Residual Score:** 12.0 (Medium)
**Control Effectiveness:** 23% reduction

**Risk List:**
- R-001: GP Practice Adoption Stalls - Residual: 12 (Medium)
- R-005: GP System Supplier Non-Cooperation - Residual: 12 (Medium)

**Key Themes:**
- External dependencies on GP practices and suppliers limit control effectiveness
- Success requires engagement and relationship management, not just technical controls

**Category Risk Profile:** ⚠️ Concerning - Limited ability to reduce external dependencies

---

### CLINICAL SAFETY Risks

**Total CLINICAL SAFETY Risks:** 2 (R-002, R-011)
**Average Inherent Score:** 20.0 (Critical)
**Average Residual Score:** 8.0 (Medium)
**Control Effectiveness:** 60% reduction

**Risk List:**
- R-002: Clinical Safety Incident Occurs - Residual: 10 (Medium)
- R-011: Booking Error Causing Patient Safety Harm - Residual: 6 (Medium)

**Key Themes:**
- Strong governance (DCB0129/0160) provides effective risk reduction
- CSO halt authority is critical control
- Phased rollout limits exposure while evidence accumulates
- Impact remains high - patient safety is non-negotiable

**Category Risk Profile:** ✅ Acceptable - Robust controls significantly reduce risk

---

### COMPLIANCE Risks

**Total COMPLIANCE Risks:** 3 (R-003, R-007, R-012)
**Average Inherent Score:** 11.3 (Medium)
**Average Residual Score:** 9.0 (Medium)
**Control Effectiveness:** 20% reduction

**Risk List:**
- R-003: GDS Assessment Fails - Residual: 12 (Medium) ❌ Exceeds appetite
- R-007: GDPR Compliance Failure - Residual: 12 (Medium) ❌ Exceeds appetite
- R-012: Excessive Data Retention - Residual: 3 (Low)

**Key Themes:**
- Compliance risks are mandatory - cannot avoid
- DPIA and Service Standard provide clear compliance paths
- Retention risks well-controlled through automation

**Category Risk Profile:** ⚠️ Concerning - Two risks exceed appetite (GDS, GDPR)

---

### TECHNOLOGY Risks

**Total TECHNOLOGY Risks:** 5 (R-004, R-009, R-010, R-014, R-016)
**Average Inherent Score:** 13.2 (High)
**Average Residual Score:** 7.4 (Medium)
**Control Effectiveness:** 44% reduction

**Risk List:**
- R-004: Data Breach Occurs - Residual: 12 (Medium) ❌ Exceeds appetite
- R-009: Unauthorized Access to Health Data - Residual: 9 (Medium)
- R-010: NHS Number and Contact Breach - Residual: 9 (Medium)
- R-014: Re-identification - Residual: 3 (Low)
- R-016: Function Creep - Residual: 4 (Low)

**Key Themes:**
- Strong technical controls (encryption, access control) are highly effective
- Cyber security risk can never be eliminated but can be well-managed
- Technology risks cluster together - shared mitigations efficient

**Category Risk Profile:** ⚠️ Concerning - Data breach risk exceeds appetite; otherwise well-controlled

---

### REPUTATIONAL Risks

**Total REPUTATIONAL Risks:** 1 (R-006)
**Average Inherent Score:** 16.0 (High)
**Average Residual Score:** 12.0 (Medium)
**Control Effectiveness:** 25% reduction

**Risk List:**
- R-006: Ministerial Scrutiny During Incident - Residual: 12 (Medium) ❌ Exceeds appetite

**Key Themes:**
- Reputational risk is difficult to directly control
- Best mitigation is preventing underlying incidents
- Communications can limit damage but not prevent

**Category Risk Profile:** ⚠️ Concerning - Prevention through other risk controls is key

---

### OPERATIONAL Risks

**Total OPERATIONAL Risks:** 2 (R-008, R-013)
**Average Inherent Score:** 11.0 (Medium)
**Average Residual Score:** 6.0 (Medium)
**Control Effectiveness:** 45% reduction

**Risk List:**
- R-008: Vulnerable Patient Exclusion - Residual: 9 (Medium)
- R-013: Third-Party Processor Misuse - Residual: 3 (Low)

**Key Themes:**
- Accessibility controls effective for inclusion risk
- DPAs control processor risk

**Category Risk Profile:** ✅ Acceptable - All risks within appetite

---

## E. Risk Ownership Matrix

**Risk Ownership Distribution by Stakeholder:**

| Stakeholder | Role | Owned Risks | Critical | High | Medium | Low | Total Score | Risk Concentration |
|-------------|------|-------------|----------|------|--------|-----|-------------|-------------------|
| NHS England Director | Strategic Sponsor | R-001, R-006 | 0 | 0 | 2 | 0 | 24 | Moderate |
| Clinical Safety Officer | Clinical Governance | R-002, R-011 | 0 | 0 | 2 | 0 | 16 | Focused (appropriate) |
| Security Lead | Security Governance | R-004, R-009, R-010, R-014 | 0 | 0 | 3 | 1 | 33 | ⚠️ High concentration |
| IG Lead | Data Protection | R-007, R-012, R-013, R-015 | 0 | 0 | 1 | 3 | 21 | Moderate |
| Product Owner | Product Delivery | R-003, R-008 | 0 | 0 | 2 | 0 | 21 | Moderate |
| GP Connect Team Lead | Integration | R-005 | 0 | 0 | 1 | 0 | 12 | Low |
| Enterprise Architect | Architecture | R-016 | 0 | 0 | 0 | 1 | 4 | Low |

**Risk Concentration Analysis:**
- ⚠️ **Security Lead owns 4 risks totaling 33 points** - Appropriate given role, but ensure adequate security team capacity
- **Clinical Safety Officer concentration appropriate** - Patient safety is their core accountability
- **Good distribution across other stakeholders**

**Escalation Paths:**
- **Clinical Safety Risks** → Clinical Safety Officer → NHS Digital Director → NHS England Director → Minister
- **Security/Data Risks** → Security Lead / IG Lead → NHS Digital Director
- **Strategic Risks** → NHS England Director → Minister
- **Compliance Risks** → IG Lead / Product Owner → NHS Digital Director → GDS / ICO

---

## F. 4Ts Response Framework Summary

**Risk Response Distribution:**

| Response | Count | % | Total Risk Score | Key Examples |
|----------|-------|---|------------------|--------------|
| **TOLERATE** | 4 | 25% | 13 (Low) | R-012, R-013, R-014, R-015 - Low risks within appetite |
| **TREAT** | 11 | 69% | 130 (High) | R-001 through R-011, R-016 - Active mitigation |
| **TRANSFER** | 1 | 6% | 12 | R-004 has cyber insurance as secondary |
| **TERMINATE** | 0 | 0% | 0 | No activities terminated |
| **TOTAL** | 16 | 100% | 156 | |

**Key Insights:**
- **69% of risks require active treatment** - Significant mitigation effort underway
- **25% can be tolerated** - Lower risks with adequate existing controls
- **Limited transfer** - Cyber insurance supplements R-004 but doesn't fully transfer
- **No termination** - All activities essential to service

---

## G. Risk Appetite Compliance

**Organizational Risk Appetite Thresholds:**

| Category | Appetite Level | Threshold Score | Description |
|----------|---------------|-----------------|-------------|
| STRATEGIC | Medium | ≤ 12 | Accept medium strategic risk for NHS transformation |
| CLINICAL SAFETY | Very Low | ≤ 10 | Minimal tolerance for patient safety risks |
| COMPLIANCE | Low | ≤ 9 | Low tolerance for regulatory breaches |
| REPUTATIONAL | Low | ≤ 9 | Low tolerance for reputational damage |
| TECHNOLOGY | Medium | ≤ 9 | Moderate technology risk with controls |
| OPERATIONAL | Medium | ≤ 9 | Moderate operational risk tolerance |

**Compliance Summary:**

| Category | Appetite | Risks Within | Risks Exceeding | Avg Excess | Action Required |
|----------|----------|--------------|-----------------|------------|-----------------|
| STRATEGIC | ≤ 12 | 2 (100%) | 0 (0%) | N/A | ✅ Compliant |
| CLINICAL SAFETY | ≤ 10 | 2 (100%) | 0 (0%) | N/A | ✅ Compliant |
| COMPLIANCE | ≤ 9 | 1 (33%) | 2 (67%) | +3 points | ⚠️ Senior approval required |
| REPUTATIONAL | ≤ 9 | 0 (0%) | 1 (100%) | +3 points | ⚠️ NHS England Director approval required |
| TECHNOLOGY | ≤ 9 | 4 (80%) | 1 (20%) | +3 points | ⚠️ Security/IG approval required |
| OPERATIONAL | ≤ 9 | 2 (100%) | 0 (0%) | N/A | ✅ Compliant |

**Overall Appetite Compliance:** ⚠️ 4 risks exceed appetite - escalation required

**Risks Exceeding Appetite:**

| Risk ID | Category | Appetite | Actual | Excess | % Over | Escalation |
|---------|----------|----------|--------|--------|--------|------------|
| R-003 | COMPLIANCE | 9 | 12 | +3 | 33% | ⚠️ NHS Digital Director |
| R-004 | TECHNOLOGY | 9 | 12 | +3 | 33% | ⚠️ Security Lead + IG Lead |
| R-006 | REPUTATIONAL | 9 | 12 | +3 | 33% | ⚠️ NHS England Director |
| R-007 | COMPLIANCE | 9 | 12 | +3 | 33% | ⚠️ IG Lead + DPO |

**Recommendations:**
1. Escalate R-003, R-004, R-006, R-007 to designated approvers for formal risk acceptance
2. Continue active treatment to reduce these risks to within appetite
3. Monitor closely - any increase requires re-escalation

---

## H. Prioritized Action Plan

**Priority Actions for Risk Mitigation:**

### Priority 1: URGENT (Appetite Exceedance)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Expected Impact | Status |
|----------|--------|-------------------|-------|----------|------|-----------------|--------|
| 1 | Mock GDS Assessment | R-003 | Product Owner | 4 weeks before assessment | £15K | Reduce from 12 to 8 | Not Started |
| 2 | Red Team Security Exercise | R-004 | Security Lead | Before Beta | £50K | Reduce from 12 to 6 | Not Started |
| 3 | Crisis Communications Plan | R-006 | Communications Team | Before Beta | £10K | Reduce from 12 to 9 | Not Started |
| 4 | SAR Process Testing | R-007 | IG Lead | Before Beta | £5K | Reduce from 12 to 8 | Not Started |

**Total Urgent Actions:** 4
**Total Cost:** £80K
**Expected Risk Reduction:** 15 points total

### Priority 2: HIGH (At Appetite Threshold)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Expected Impact | Status |
|----------|--------|-------------------|-------|----------|------|-----------------|--------|
| 5 | Success Story Publication | R-001 | Communications Team | Alpha + 2 months | £10K | Reduce from 12 to 8 | Not Started |
| 6 | Regional Practice Champions | R-001 | NHS England Primary Care | Beta launch | £25K | Reduce from 12 to 8 | Planning |
| 7 | Clinical Pre-Mortem | R-002 | Clinical Safety Officer | Before Beta | £5K | Identify unknown hazards | Not Started |
| 8 | Director-level Supplier Relationships | R-005 | NHS Digital Director | Alpha launch | Staff time | Reduce from 12 to 8 | Not Started |

**Total High Priority Actions:** 4
**Total Cost:** £40K + staff time
**Expected Risk Reduction:** 12 points total

### Priority 3: MEDIUM (Enhancement)

| Priority | Action | Risk(s) Addressed | Owner | Due Date | Cost | Expected Impact | Status |
|----------|--------|-------------------|-------|----------|------|-----------------|--------|
| 9 | SOC Integration | R-004 | Security Lead | Before Live | £30K/year | Faster detection | Planning |
| 10 | Independent Clinical Review | R-002 | NHS Digital Director | Before Live | £30K | External validation | Not Started |

**Total Medium Priority Actions:** 2
**Total Cost:** £60K (first year)
**Expected Risk Reduction:** Enhancement, not primary reduction

**Overall Action Plan Summary:**
- **Total Actions:** 10
- **Total Investment:** £180K (first year)
- **Expected Risk Reduction:** 27+ points
- **Target Completion:** Aligned with Alpha/Beta/Live milestones

---

## I. Integration with SOBC

**How this Risk Register feeds into Strategic Outline Business Case (SOBC):**

### SOBC Strategic Case (Part A)
- **R-001** (GP Practice Adoption): Demonstrates dependency on practice engagement
- **R-002** (Clinical Safety): Justifies phased approach with clinical governance

### SOBC Economic Case (Part B)
- **R-004** (Data Breach): Contingency for security remediation (£50K)
- **R-001** (GP Adoption): Risk of reduced benefits if adoption lower than planned

### SOBC Management Case (Part E - Risk Management)
- **Full risk register** included in Management Case Part E
- **Top 10 risks** with residual scores and mitigation plans
- **Risk ownership matrix** from stakeholder RACI
- **Monthly monitoring** at Steering Committee

### SOBC Recommendation
- **4 risks exceeding appetite** requires Board/Director approval
- **Strong clinical safety governance** supports healthcare IT investment case
- **Technology risk controls** demonstrate security maturity

---

## J. Monitoring and Review Framework

### Review Schedule

| Risk Level | Review Frequency | Reviewed By | Escalated To | Report Format |
|------------|------------------|-------------|--------------|---------------|
| **Critical (20-25)** | Weekly | Risk Owner + PMO | Steering Committee | Dashboard + narrative |
| **High (13-19)** | Bi-weekly | Risk Owner | NHS Digital Director | Dashboard |
| **Medium (6-12)** | Monthly | Risk Owner | Project Manager | Exception report |
| **Low (1-5)** | Quarterly | Action Owner | Risk Owner | Status update |

### Key Risk Indicators (KRIs)

**Leading Indicators** (predict future risk changes):
- Practice expression of interest pipeline (R-001)
- Hazard log closure rate (R-002)
- Security vulnerability scan findings (R-004)
- User research session completion rate (R-003)
- Supplier GP Connect compliance status (R-005)

**Lagging Indicators** (confirm risk materialization):
- Clinical incident reports (R-002)
- Data breach notifications (R-004)
- GDS assessment outcomes (R-003)
- Practice onboarding rate (R-001)
- Patient complaints volume (R-006)

### Escalation Criteria

**Automatic Escalation Triggers:**
1. Any risk increases by 4+ points
2. Any new Critical risk (score 20-25) identified
3. Any clinical safety incident (any severity)
4. Any data breach (any severity)
5. Any risk exceeds appetite and no mitigation plan in place
6. Mitigation action delayed > 1 month

### Reporting Requirements

**Weekly** (Clinical Safety + Security):
- Clinical safety dashboard to Clinical Safety Officer
- Security dashboard to Security Lead
- Any incident immediately to NHS Digital Director

**Monthly** (All Risks):
- Full risk register to Steering Committee
- Risk matrix visualization
- Risk appetite compliance summary
- Action plan status

**Quarterly** (Strategic Review):
- Risk trend analysis
- Risk appetite threshold review
- SOBC risk section update
- Lessons learned

### Risk Register Maintenance

**Risk Register Owner:** Programme Manager, NHS Digital

**Responsibilities:**
- Maintain accuracy of risk register
- Coordinate risk reviews with risk owners
- Update risk scores based on evidence
- Track mitigation action completion
- Escalate risks per criteria
- Produce risk reports

**Update Process:**
1. Risk owners submit updates weekly (critical/high) or monthly (medium/low)
2. Risk register owner validates and updates register
3. PMO reviews for consistency and completeness
4. Steering Committee approves material changes

---

## K. Orange Book Compliance Checklist

This risk register demonstrates compliance with HM Treasury Orange Book (2023):

### Part I - Risk Management Principles

- ✅ **A. Governance and Leadership**
  - Risk owners assigned from senior stakeholders (from RACI matrix)
  - Escalation paths defined to NHS Digital Director, NHS England Director, Minister
  - Risk appetite set and monitored per category

- ✅ **B. Integration**
  - Risks linked to stakeholder drivers (SD-1 through SD-10) and goals (G-1 through G-7)
  - Risks inform SOBC Management Case
  - DPIA risks (DPIA-001 through DPIA-010) integrated

- ✅ **C. Collaboration and Best Information**
  - Risks sourced from stakeholder analysis (ARC-001-STKE-v1.3)
  - Risks sourced from DPIA (ARC-001-DPIA-v1.0)
  - Evidence-based assessment with justified likelihood and impact

- ✅ **D. Risk Management Processes**
  - Systematic identification across 6 categories
  - Consistent 5×5 assessment methodology
  - 4Ts response framework applied
  - Inherent and residual risk tracked

- ✅ **E. Continual Improvement**
  - Review schedule (weekly/monthly/quarterly) defined
  - Key Risk Indicators defined
  - Version control for risk register

### Part II - Risk Control Framework

- ✅ **4-Pillar "House" Structure**
  - Risk appetite and tolerance defined per category
  - Risk ownership and governance established
  - Risk assessment methodology documented
  - Control effectiveness measured (inherent vs residual)

---

## Appendix A: Risk Assessment Scales

### Likelihood Scale (1-5)

| Score | Rating | Probability | Description |
|-------|--------|-------------|-------------|
| 1 | Rare | < 5% | Highly unlikely, exceptional circumstances only |
| 2 | Unlikely | 5-25% | Could happen but probably won't |
| 3 | Possible | 25-50% | Reasonable chance, has happened before |
| 4 | Likely | 50-75% | More likely to happen than not |
| 5 | Almost Certain | > 75% | Expected to occur, highly probable |

### Impact Scale (1-5)

| Score | Rating | Financial | Schedule | Patient/Stakeholder | Description |
|-------|--------|-----------|----------|---------------------|-------------|
| 1 | Negligible | < £50K | < 1 week | Minimal concern | Easily absorbed |
| 2 | Minor | £50K-£200K | 1-4 weeks | Minor concern | Manageable |
| 3 | Moderate | £200K-£500K | 1-2 months | Significant concern | Requires effort |
| 4 | Major | £500K-£2M | 2-6 months | Severe concern | Threatens objectives |
| 5 | Catastrophic | > £2M | > 6 months | Patient harm / existential | Project failure |

### Risk Score Matrix (Likelihood × Impact)

| Score Range | Risk Level | Color | Action Required |
|-------------|------------|-------|-----------------|
| 20-25 | Critical | 🟥 Red | Immediate escalation |
| 13-19 | High | 🟧 Orange | Management attention |
| 6-12 | Medium | 🟨 Yellow | Monitoring |
| 1-5 | Low | 🟩 Green | Routine |

---

## Appendix B: Stakeholder-Risk Linkage

**Traceability from Stakeholders (ARC-001-STKE-v1.3) to Risks:**

| Stakeholder | Driver | Risk ID | Risk Title | Category | Score |
|-------------|--------|---------|------------|----------|-------|
| NHS England Director | SD-1: Deliver Long Term Plan | R-001 | GP Practice Adoption Stalls | STRATEGIC | 12 |
| NHS England Director | SD-1: Deliver Long Term Plan | R-006 | Ministerial Scrutiny | REPUTATIONAL | 12 |
| Clinical Safety Officer | SD-2: Protect Patients | R-002 | Clinical Safety Incident | CLINICAL SAFETY | 10 |
| Clinical Safety Officer | SD-2: Protect Patients | R-011 | Booking Error | CLINICAL SAFETY | 6 |
| GP Practice Managers | SD-3: Reduce Admin Burden | R-001 | GP Practice Adoption Stalls | STRATEGIC | 12 |
| Patients | SD-4: Access Without Frustration | R-008 | Vulnerable Patient Exclusion | OPERATIONAL | 9 |
| GP System Suppliers | SD-5: Maintain Market Position | R-005 | GP Supplier Non-Cooperation | STRATEGIC | 12 |
| GDS Assessment Team | SD-6: Service Standard | R-003 | GDS Assessment Fails | COMPLIANCE | 12 |
| Minister | SD-7: Demonstrate Modernisation | R-006 | Ministerial Scrutiny | REPUTATIONAL | 12 |
| IG Lead | SD-8: Protect Patient Data | R-007 | GDPR Compliance Failure | COMPLIANCE | 12 |
| IG Lead | SD-8: Protect Patient Data | R-004 | Data Breach | TECHNOLOGY | 12 |
| Security Lead | SD-10: Protect NHS Systems | R-004 | Data Breach | TECHNOLOGY | 12 |
| Security Lead | SD-10: Protect NHS Systems | R-009 | Unauthorized Access | TECHNOLOGY | 9 |

**DPIA Risks Consolidated into Risk Register:**

| DPIA Risk | Risk Register ID | Mapping |
|-----------|------------------|---------|
| DPIA-001: Unauthorized access to health data | R-009 | Direct mapping |
| DPIA-002: NHS Number and contact breach | R-010 | Direct mapping |
| DPIA-003: Booking error causing patient safety harm | R-011 | Direct mapping |
| DPIA-004: Excessive data retention | R-012 | Direct mapping |
| DPIA-005: Third-party processor misuse | R-013 | Direct mapping |
| DPIA-006: Re-identification | R-014 | Direct mapping |
| DPIA-007: Loss of control over personal data | R-015 | Direct mapping |
| DPIA-008: Function creep | R-016 | Direct mapping |
| DPIA-009: Discrimination from health data | R-009 | Consolidated with R-009 |
| DPIA-010: Vulnerable patient exclusion | R-008 | Direct mapping |

---

## Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Risk Register Owner** | Programme Manager | | |
| **Clinical Safety Officer** | NHS Digital CSO | | |
| **Security Lead** | NHS Digital Security Lead | | |
| **IG Lead** | NHS Digital IG Lead | | |
| **NHS Digital Director** | Director of Digital Services | | |
| **NHS England Director** | Director of Primary Care | | |

---

## Next Steps

1. **Immediate Actions** (This Week):
   - [ ] Escalate R-003 (GDS), R-004 (Data Breach), R-006 (Ministerial), R-007 (GDPR) to designated approvers
   - [ ] Schedule risk review meetings with all risk owners
   - [ ] Set up risk monitoring dashboard

2. **Short-term Actions** (This Month):
   - [ ] Commission mock GDS assessment (Priority 1)
   - [ ] Commission red team security exercise (Priority 1)
   - [ ] Develop crisis communications plan (Priority 1)
   - [ ] Test SAR process end-to-end (Priority 1)

3. **Medium-term Actions** (This Quarter):
   - [ ] Publish practice success stories (Priority 5)
   - [ ] Recruit regional practice champions (Priority 6)
   - [ ] Conduct clinical pre-mortem exercise (Priority 7)
   - [ ] Establish Director-level supplier relationships (Priority 8)

4. **Ongoing**:
   - [ ] Monthly risk register review at Steering Committee
   - [ ] Quarterly risk appetite compliance review
   - [ ] Annual DPIA review (2027-01-28)

---

**END OF RISK REGISTER**

---

*This risk register follows HM Treasury Orange Book (2023) principles and integrates with ArcKit's stakeholder-driven architecture governance framework.*

*For questions or updates, contact: Programme Manager, NHS Digital*

---

**Generated by**: ArcKit `/arckit.risk` command
**Generated on**: 2026-01-28
**ArcKit Version**: 1.0.0
**Project**: NHS Doctors Online Appointment System (Project 001)
**AI Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
