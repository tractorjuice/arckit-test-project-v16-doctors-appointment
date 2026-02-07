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

## Getting Started

This project uses [ArcKit](https://github.com/tractorjuice/arc-kit) for enterprise architecture governance and vendor procurement.

1. Start your AI assistant (Claude Code, Gemini CLI, or Codex CLI)
2. Run `/arckit.principles` to establish architecture governance
3. Run `/arckit.stakeholders` to analyze stakeholder drivers and goals
4. Run `/arckit.requirements` to define requirements for the appointment system

Full dependency ordering is documented in [`DEPENDENCY-MATRIX.md`](DEPENDENCY-MATRIX.md).

## Available Commands

Once you start your AI assistant, you'll have access to 43 commands:

#### Project Planning
- `/arckit.plan` - Create project plan with timeline, phases, and gates

#### Core Workflow
- `/arckit.principles` - Create or update architecture principles
- `/arckit.stakeholders` - Analyze stakeholder drivers, goals, and outcomes
- `/arckit.risk` - Create comprehensive risk register (Orange Book)
- `/arckit.sobc` - Create Strategic Outline Business Case (Green Book 5-case)
- `/arckit.requirements` - Define comprehensive requirements
- `/arckit.data-model` - Create data model with ERD, GDPR compliance, data governance
- `/arckit.research` - Research technology, services, and products with build vs buy analysis
- `/arckit.datascout` - Discover external data sources, APIs, and open data portals
- `/arckit.wardley` - Create strategic Wardley Maps for build vs buy and procurement strategy
- `/arckit.adr` - Document architectural decisions with options analysis

#### Cloud Research
- `/arckit.aws-research` - Research AWS services using AWS Knowledge MCP
- `/arckit.azure-research` - Research Azure services using Microsoft Learn MCP

#### Vendor Procurement
- `/arckit.sow` - Generate Statement of Work (RFP)
- `/arckit.dos` - Digital Outcomes and Specialists (DOS) procurement
- `/arckit.gcloud-search` - Search G-Cloud services on UK Digital Marketplace
- `/arckit.gcloud-clarify` - Validate G-Cloud services and generate clarification questions
- `/arckit.evaluate` - Create vendor evaluation framework and score vendors

#### Design & Delivery
- `/arckit.diagram` - Generate visual architecture diagrams using Mermaid
- `/arckit.hld-review` - Review High-Level Design
- `/arckit.dld-review` - Review Detailed Design
- `/arckit.backlog` - Generate prioritised product backlog with GDS user stories
- `/arckit.devops` - Create DevOps strategy with CI/CD pipelines
- `/arckit.finops` - Create FinOps strategy for cloud cost management
- `/arckit.mlops` - Create MLOps strategy with model lifecycle and governance
- `/arckit.operationalize` - Create operational readiness pack with runbooks and DR/BCP
- `/arckit.roadmap` - Create strategic architecture roadmap
- `/arckit.platform-design` - Create platform strategy using Platform Design Toolkit

#### Service Management
- `/arckit.servicenow` - Generate ServiceNow service design
- `/arckit.traceability` - Generate requirements traceability matrix
- `/arckit.analyze` - Comprehensive governance quality analysis
- `/arckit.data-mesh-contract` - Federated data product contracts
- `/arckit.principles-compliance` - Architecture principles compliance scorecard

#### UK Government Compliance
- `/arckit.service-assessment` - GDS Service Standard assessment preparation
- `/arckit.tcop` - Technology Code of Practice assessment
- `/arckit.ai-playbook` - AI Playbook compliance for responsible AI
- `/arckit.dpia` - Data Protection Impact Assessment (UK GDPR Article 35)
- `/arckit.atrs` - Algorithmic Transparency Recording Standard (ATRS) record

#### Security Assessment
- `/arckit.secure` - UK Government Secure by Design
- `/arckit.mod-secure` - MOD Secure by Design
- `/arckit.jsp-936` - MOD JSP 936 AI assurance documentation

#### Reporting
- `/arckit.story` - Generate project story with timeline and governance achievements
- `/arckit.pages` - Generate GitHub Pages site for project documentation

## Project Structure

```
doctors-online-appointment-system/
├── .arckit/
│   ├── templates/        # Document templates
│   └── scripts/bash/     # Helper scripts
│   ├── commands/         # ArcKit slash commands
│   └── agents/           # Autonomous research agents
├── .codex/prompts/       # Codex CLI commands
├── .gemini/commands/     # Gemini CLI commands
├── docs/
│   ├── guides/           # Command usage guides
│   └── README.md         # Documentation index
├── projects/
│   ├── 000-global/
│   │   ├── policies/     # Organisation-wide policy documents
│   │   └── ARC-000-PRIN-v1.0.md
│   └── 001-doctors-appointment/
│       ├── ARC-001-REQ-v1.0.md
│       ├── ARC-001-STKE-v1.0.md
│       ├── external/     # External documents (PDFs, images)
│       └── vendors/      # Vendor submissions
├── DEPENDENCY-MATRIX.md  # Command dependencies
├── WORKFLOW-DIAGRAMS.md  # Visual workflows
└── VERSION
```

## Documentation

- [ArcKit Documentation](https://github.com/tractorjuice/arc-kit)
- [Command Guides](docs/guides/)
- [Dependency Matrix](DEPENDENCY-MATRIX.md)
- [Workflow Diagrams](WORKFLOW-DIAGRAMS.md)

---

*This is an ArcKit test repository (v16) for testing architecture governance commands.*
