# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Project Context

**Doctors Online Appointment System** - An NHS-aligned digital service for booking GP and specialist appointments online.

### Key Domain Concepts

- **Patient**: NHS registered individual booking appointments
- **Appointment**: Scheduled consultation with healthcare professional
- **Practice**: GP surgery or healthcare facility
- **Clinician**: GP, nurse, specialist, or other healthcare provider
- **Slot**: Available appointment time window

### NHS Integration Points

- **NHS Spine**: Patient demographics, GP registration (PDS/FHIR)
- **NHS Login**: Patient authentication and identity verification
- **GP Connect**: Access to GP clinical systems
- **MESH**: Secure file transfer for NHS communications

## Architecture Approach

When generating architecture artifacts, consider:

1. **User-Centered Design**: Follow GDS principles, focus on patient needs
2. **NHS Standards**: Align with NHS Digital interoperability standards
3. **Clinical Safety**: DCB0129 (manufacturer) and DCB0160 (deployer) compliance
4. **Data Protection**: DPIA required for health data processing
5. **Accessibility**: WCAG 2.2 AA mandatory for public services

## Recommended Command Sequence

1. `/arckit.principles` - NHS-aligned architecture principles
2. `/arckit.stakeholders` - Patients, clinicians, practice staff, NHS Digital
3. `/arckit.requirements` - Capture booking, scheduling, notification requirements
4. `/arckit.dpia` - Health data processing impact assessment
5. `/arckit.data-model` - Patient, appointment, practitioner entities
6. `/arckit.secure` - NCSC CAF and NHS DSPT alignment
7. `/arckit.service-assessment` - GDS Service Standard preparation

## Key Compliance Frameworks

| Framework | Relevance |
|-----------|-----------|
| GDS Service Standard | Mandatory for public-facing services |
| NHS Digital Standards | Interoperability and data standards |
| DSPT | NHS data security self-assessment |
| DCB0129/DCB0160 | Clinical safety for health IT |
| UK GDPR | Health data is special category |
| WCAG 2.2 AA | Accessibility for public services |

## Project Structure

```
projects/001-doctors-appointment/
├── ARC-001-*.md          # Architecture artifacts
└── vendors/              # Vendor evaluation materials
```

Use `.arckit/scripts/bash/create-project.sh` to create the project directory.
