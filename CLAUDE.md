# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**ArcKit Test Project (v16)** - Doctors Online Appointment System

This is an architecture governance project using ArcKit v1.0.0 to generate enterprise architecture documentation for an NHS-aligned digital service for booking GP and specialist appointments online.

## What is ArcKit?

ArcKit is an enterprise architecture governance toolkit providing 40 slash commands for generating architecture artifacts. Commands are available across three AI assistants:
- Claude Code: `.claude/commands/arckit.*.md`
- OpenAI Codex CLI: `.codex/prompts/arckit.*.md`
- Google Gemini CLI: `.gemini/commands/arckit/*.toml`

## Key Commands

### Foundation & Governance
- `/arckit.plan` - Project plan with GDS Agile phases (Discovery → Alpha → Beta → Live)
- `/arckit.principles` - Architecture principles (outputs to `.arckit/memory/`)
- `/arckit.stakeholders` - Stakeholder analysis with Power-Interest Grid and RACI
- `/arckit.risk` - HM Treasury Orange Book risk register
- `/arckit.sobc` - HM Treasury Green Book Strategic Outline Business Case

### Requirements & Data
- `/arckit.requirements` - Business/functional/non-functional requirements
- `/arckit.data-model` - Entity-Relationship diagrams with GDPR compliance
- `/arckit.dpia` - Data Protection Impact Assessment (UK GDPR Article 35)
- `/arckit.data-mesh-contract` - Federated data product contracts (ODCS v3.0.2)

### Design & Research
- `/arckit.research` - Technology research with build vs buy analysis
- `/arckit.wardley` - Wardley Maps for strategic planning
- `/arckit.diagram` - Architecture diagrams (C4 model with Mermaid)
- `/arckit.adr` - Architecture Decision Records (MADR format)

### Compliance (UK Government)
- `/arckit.service-assessment` - GDS Service Standard (14 points)
- `/arckit.tcop` - Technology Code of Practice
- `/arckit.secure` - NCSC CAF Secure by Design
- `/arckit.ai-playbook` - UK Government AI Playbook
- `/arckit.atrs` - Algorithmic Transparency Recording Standard

### MOD Defence
- `/arckit.mod-secure` - MOD Secure by Design (CAAT continuous assurance)
- `/arckit.jsp-936` - JSP 936 AI assurance for defence AI/ML systems

## Project Structure

```
projects/
└── 001-doctors-appointment/
    ├── ARC-001-PRIN-v1.0.md     # Architecture principles
    ├── ARC-001-STKE-v1.0.md     # Stakeholder analysis
    ├── ARC-001-REQ-v1.0.md      # Requirements
    ├── ARC-001-DATA-v1.0.md     # Data model
    ├── ARC-001-DPIA-v1.0.md     # DPIA
    ├── decisions/               # ADRs (ARC-001-ADR-001-v1.0.md)
    ├── diagrams/                # Architecture diagrams
    ├── wardley-maps/            # Wardley maps
    └── vendors/                 # Vendor evaluations

.arckit/
├── memory/                      # Global artifacts (principles)
├── templates/                   # Document templates (41 templates)
└── scripts/bash/               # Utility scripts
```

## Workflow: Command Dependency Order

Commands must be run in dependency order. See `DEPENDENCY-MATRIX.md` for the full 40×40 matrix.

**Recommended sequence for this NHS project:**

1. `/arckit.principles` → Foundation (no dependencies)
2. `/arckit.stakeholders` → Patients, clinicians, practice staff, NHS Digital
3. `/arckit.risk` → Orange Book risk register
4. `/arckit.sobc` → Green Book business case
5. `/arckit.requirements` → BR/FR/NFR/DR requirements
6. `/arckit.data-model` → Patient, appointment, practitioner entities
7. `/arckit.dpia` → Health data is special category under UK GDPR
8. `/arckit.secure` → NCSC CAF and NHS DSPT alignment
9. `/arckit.service-assessment` → GDS Service Standard preparation

## Utility Scripts

Run from repository root:

```bash
# Create new project
.arckit/scripts/bash/create-project.sh --name "Project Name"

# List projects with status
.arckit/scripts/bash/list-projects.sh --verbose

# Check prerequisites
.arckit/scripts/bash/check-prerequisites.sh --project 001

# Generate document ID
.arckit/scripts/bash/generate-document-id.sh 001 REQ 1.0
# Output: ARC-001-REQ-v1.0
```

## Document ID Convention

All artifacts use the pattern: `ARC-{PROJECT_ID}-{TYPE}-v{VERSION}.md`

| Type Code | Artifact |
|-----------|----------|
| PRIN | Architecture principles |
| STKE | Stakeholder drivers |
| REQ | Requirements |
| DATA | Data model |
| DPIA | Data Protection Impact Assessment |
| RISK | Risk register |
| SOBC | Strategic Outline Business Case |
| HLD | High-level design review |
| DLD | Detailed design review |
| ADR | Architecture Decision Record |
| DIAG | Architecture diagram |
| WARD | Wardley map |

## NHS-Specific Context

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

### Compliance Frameworks

| Framework | Relevance |
|-----------|-----------|
| GDS Service Standard | Mandatory for public-facing services |
| NHS Digital Standards | Interoperability and data standards |
| DSPT | NHS Data Security and Protection Toolkit |
| DCB0129/DCB0160 | Clinical safety for health IT |
| UK GDPR | Health data is special category |
| WCAG 2.2 AA | Accessibility for public services |

## Key Files Reference

- `DEPENDENCY-MATRIX.md` - 40×40 command dependency matrix
- `WORKFLOW-DIAGRAMS.md` - Visual workflows for 5 project paths
- `docs/guides/` - Command playbooks and usage guides
- `.arckit/templates/` - 41 document templates
