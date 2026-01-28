# Doctors Online Appointment System

An NHS-aligned digital service for booking GP and specialist appointments online.

## Project Overview

This project implements a modern online appointment booking system for healthcare services, designed to:

- Enable patients to book, reschedule, and cancel appointments online
- Integrate with NHS Spine for patient demographics and GP registration
- Support multiple appointment types (GP, specialist, nurse, video consultations)
- Provide SMS and email appointment reminders
- Ensure accessibility compliance (WCAG 2.2 AA)
- Meet NHS Digital and GDS Service Standard requirements

## Target Users

- **Patients**: Book and manage their own appointments
- **Practice Staff**: Manage appointment availability and patient communications
- **GPs/Clinicians**: View daily schedules and patient appointment history
- **Practice Managers**: Configure services, reporting, and system settings

## Compliance Requirements

- GDS Service Standard (14 points)
- NHS Digital standards and interoperability
- WCAG 2.2 Level AA accessibility
- UK GDPR and Data Protection Act 2018
- NHS Data Security and Protection Toolkit (DSPT)
- Clinical safety standards (DCB0129/DCB0160)

## Architecture Commands

Use ArcKit commands to generate architecture documentation:

### Core Workflow
- `/arckit.principles` - Establish architecture principles
- `/arckit.stakeholders` - Analyze stakeholder drivers, goals, and outcomes
- `/arckit.requirements` - Capture requirements (BR/FR/NFR)
- `/arckit.data-model` - Design patient and appointment data model
- `/arckit.diagram` - Create architecture diagrams

### Compliance & Security
- `/arckit.dpia` - Data Protection Impact Assessment
- `/arckit.secure` - Secure by Design assessment (NCSC CAF)
- `/arckit.service-assessment` - GDS Service Standard preparation
- `/arckit.tcop` - Technology Code of Practice assessment

### Risk & Business Case
- `/arckit.risk` - Create risk register (Orange Book)
- `/arckit.sobc` - Strategic Outline Business Case (Green Book)

## Project Structure

```
projects/
└── 001-doctors-appointment/
    ├── ARC-001-PRIN-v1.0.md     # Architecture principles
    ├── ARC-001-STKE-v1.0.md     # Stakeholder analysis
    ├── ARC-001-REQ-v1.0.md      # Requirements specification
    ├── ARC-001-DATA-v1.0.md     # Data model
    ├── ARC-001-DPIA-v1.0.md     # DPIA
    ├── ARC-001-RISK-v1.0.md     # Risk register
    └── vendors/                  # Vendor evaluations
```

## Getting Started

1. Start your AI assistant: `claude`
2. Establish principles: `/arckit.principles`
3. Analyze stakeholders: `/arckit.stakeholders`
4. Capture requirements: `/arckit.requirements`

## Documentation

- See `docs/` for command guides
- See `DEPENDENCY-MATRIX.md` for command dependencies
- See `WORKFLOW-DIAGRAMS.md` for visual workflows

---

*This is an ArcKit test repository (v16) for testing architecture governance commands.*
