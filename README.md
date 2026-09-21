# Third-Party Risk Assessment Playbook

> A structured, end-to-end TPRM playbook that standardizes vendor onboarding, risk tiering, and control assessments to reduce third-party exposure across an organization.

## Overview

Third-party relationships introduce some of the most difficult-to-manage risks in a modern enterprise. Vendors with access to sensitive data or critical systems can become significant attack surfaces if they are not properly evaluated before onboarding and monitored continuously afterward. This project addresses that gap by delivering a practical, repeatable playbook for assessing and managing third-party risk from initial intake through ongoing oversight.

I built this playbook to reflect the real-world workflows a Cybersecurity Risk and Compliance Analyst would own or contribute to at a professional services firm like Teneo. The artifacts mirror the types of documentation used in mature TPRM programs: risk tiering matrices, questionnaire templates, control narratives, and escalation workflows.

The playbook is designed to be framework-agnostic at its core while mapping controls and assessment criteria to recognized standards including NIST SP 800-161 (Supply Chain Risk Management), ISO 27001 Annex A, and SOC 2 Trust Service Criteria. This makes the outputs portable across different client environments and regulatory contexts.

## What I Built / Key Features

- **Vendor Intake Form**: A structured intake questionnaire capturing vendor profile data, data classification, system access scope, and sub-processor relationships before any formal assessment begins.
- **Risk Tiering Matrix**: A scoring model that classifies vendors into four tiers (Critical, High, Moderate, Low) based on data sensitivity, access level, regulatory exposure, and business dependency.
- **TPRM Assessment Questionnaire**: A domain-structured questionnaire covering information security, data privacy, business continuity, incident response, and access management, mapped to ISO 27001 and SOC 2 controls.
- **Control Narrative Templates**: Pre-written narrative templates for common controls that analysts can tailor to a vendor's environment, reducing assessment time while maintaining documentation consistency.
- **Risk Register Template**: A tracked log of identified findings, inherent and residual risk scores, remediation owners, and target closure dates.
- **Escalation and Exception Workflow**: A documented decision tree for handling high-risk findings, exceptions, and contract-level remediation requirements.
- **Ongoing Monitoring Checklist**: A periodic review schedule and checklist tied to vendor tier, covering certificate renewals, re-assessment triggers, and incident notification requirements.

## Skills & Tools Demonstrated

**Frameworks and Standards**
- NIST SP 800-161 (C-SCRM)
- ISO/IEC 27001:2022 Annex A
- SOC 2 Trust Service Criteria
- NIST CSF (Identify and Govern functions)

**Documentation and Collaboration**
- Markdown for playbook authoring and version control via Git/GitHub
- Microsoft Excel and Google Sheets for risk scoring matrices and registers
- Mermaid for workflow diagrams embedded in documentation

**Risk and Compliance Practices**
- Third-party risk tiering and inherent risk scoring
- Control gap analysis and residual risk calculation
- Control narrative writing
- Vendor lifecycle management (onboarding, periodic review, offboarding)

## Architecture & Approach

The playbook follows a linear vendor lifecycle, divided into four phases: Intake, Assessment, Decision, and Ongoing Monitoring. Each phase has defined inputs, outputs, and responsible roles, so the process can be handed off between team members without losing continuity.

Risk scoring uses a 5x5 likelihood-impact matrix applied at the domain level. Domain scores roll up into a composite vendor risk score that determines the tier assignment and the depth of assessment required. Tier 1 (Critical) vendors require full questionnaire review, evidence collection, and annual re-assessment. Tier 4 (Low) vendors complete a lightweight self-attestation on a two-year cycle.

```text
Vendor Intake
     |
     v
Risk Tiering (Tier 1-4)
     |
     v
Assessment Questionnaire (depth scaled to tier)
     |
     v
Control Gap Analysis + Narrative Drafting
     |
     v
Risk Register Update + Decision (Accept / Remediate / Escalate)
     |
     v
Contract / SLA Alignment
     |
     v
Ongoing Monitoring (periodic review schedule)
```

All templates are stored as editable flat files so they can be adapted to different tools, including GRC platforms, without rework.

## Suggested Repository Structure

```text
third-party-risk-playbook/
├── README.md
├── playbook/
│   ├── 00_overview_and_scope.md
│   ├── 01_vendor_intake_form.md
│   ├── 02_risk_tiering_matrix.md
│   ├── 03_assessment_questionnaire.md
│   ├── 04_control_narratives/
│   │   ├── access_management.md
│   │   ├── data_privacy.md
│   │   ├── incident_response.md
│   │   └── business_continuity.md
│   ├── 05_risk_register_template.xlsx
│   ├── 06_escalation_workflow.md
│   └── 07_ongoing_monitoring_checklist.md
├── diagrams/
│   └── vendor_lifecycle_flow.mmd
├── mappings/
│   ├── iso27001_control_mapping.csv
│   └── soc2_tsc_mapping.csv
└── examples/
    └── sample_vendor_assessment_redacted.md
```

## What This Demonstrates to Employers

- **Shows ability to design end-to-end TPRM processes**, from vendor intake through offboarding, with documentation quality suitable for audit review.
- **Demonstrates familiarity with industry frameworks**, including NIST SP 800-161, ISO 27001, and SOC 2, and the ability to apply them to practical vendor assessment scenarios.
- **Illustrates control narrative writing skills**, a core deliverable for compliance analysts supporting audits, client assessments, or internal reviews.
- **Reflects risk-based thinking**, using tiered assessment depth to allocate analyst effort proportionally to actual exposure rather than applying a one-size-fits-all process.
- **Proves readiness for cross-functional collaboration**, since the playbook defines roles, handoff points, and escalation paths that require coordination across security, legal, procurement, and business owners.
- **Highlights documentation discipline**, using version-controlled, structured markdown artifacts that can integrate into a GRC platform or standalone workflow at an advisory firm like Teneo.

## Getting Started

**Prerequisites:** Git, a Markdown viewer (VS Code with the Markdown Preview extension recommended), and Microsoft Excel or Google Sheets for the register templates.

```bash
git clone https://github.com/your-username/third-party-risk-playbook.git
cd third-party-risk-playbook
```

Open `playbook/00_overview_and_scope.md` to begin. For diagram rendering, install the Mermaid CLI or use the Mermaid Live Editor to preview `.mmd` files in `diagrams/`.

```bash
npm install -g @mermaid-js/mermaid-cli
mmdc -i diagrams/vendor_lifecycle_flow.mmd -o diagrams/vendor_lifecycle_flow.png
```
