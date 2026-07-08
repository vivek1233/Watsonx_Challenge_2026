# Agent 3 — Staffing & Resource Planning Agent

> **Role:** Delivery Manager / Resource Manager  
> **Reports To:** Orchestrator Agent  
> **Receives From:** Agent 2 (Estimation Agent)  
> **Outputs To:** Partner / Delivery Lead / HR

---

## 1. Agent Purpose

Agent 3 consumes the effort estimation from Agent 2 and produces a **complete staffing plan** covering:

- Role definitions and skill requirements per phase
- Headcount ramp-up and ramp-down plan (12-month implementation)
- Managed service org structure (4-year steady state)
- RACI matrix
- Onboarding and knowledge transfer plan
- Cost-per-resource breakdown

---

## 2. Inputs

| Input | Format | Source |
|---|---|---|
| Phase Effort Breakdown | JSON | Agent 2 Output |
| Managed Service Tower Breakdown | JSON | Agent 2 Output |
| Skill Requirements Matrix | JSON | Agent 2 Output |
| Rate Card | JSON | Finance Team |
| Resource Availability Pool | JSON | HR / Resource Management System |
| Role Competency Framework | Markdown | HR / Practice |

---

## 3. Role Taxonomy

### 3.1 Implementation Roles

| Role Code | Role Title | Seniority | Key Skills |
|---|---|---|---|
| R-01 | Delivery Manager | Senior | PMP/Prince2, stakeholder mgmt, risk, Agile |
| R-02 | Solution Architect | Senior | WatsonX, IBM Cloud, enterprise architecture |
| R-03 | AI/ML Engineer | Mid–Senior | Python, WatsonX.ai, prompt engineering, MLOps |
| R-04 | Data Engineer | Mid–Senior | SQL, Spark, WatsonX.data, ETL/ELT pipelines |
| R-05 | Backend Developer | Mid | Python/Node.js, REST APIs, microservices |
| R-06 | Frontend Developer | Mid | React/Next.js, UX, accessibility |
| R-07 | Integration Specialist | Mid–Senior | MQ, Kafka, API Connect, ESB patterns |
| R-08 | DevOps / SRE Engineer | Mid | Kubernetes, Docker, GitHub Actions, IBM Cloud |
| R-09 | Test Lead / QA Engineer | Mid | Selenium, pytest, k6, test strategy |
| R-10 | Business Analyst | Mid | Process mapping, requirements, user stories |
| R-11 | Change & Training Lead | Mid | Change management, LMS, training delivery |
| R-12 | Security Architect | Senior | IBM Guardium, IAM, pen testing, compliance |
| R-13 | PMO Analyst | Junior–Mid | MS Project, RAID log, reporting |

### 3.2 Managed Service Roles

| Role Code | Role Title | Seniority | Key Skills |
|---|---|---|---|
| MS-01 | Service Delivery Manager | Senior | ITIL, SLA management, client relationship |
| MS-02 | Application Support Lead | Mid–Senior | Application triage, patch mgmt, enhancements |
| MS-03 | AI Operations Engineer | Mid | Model monitoring, drift detection, retraining |
| MS-04 | Data Operations Analyst | Mid | Pipeline monitoring, data quality, reconciliation |
| MS-05 | Platform Engineer | Mid | Cloud ops, infrastructure monitoring, upgrades |
| MS-06 | Service Desk Analyst (L1) | Junior | ITSM tools, incident logging, first-line support |
| MS-07 | Support Engineer (L2/L3) | Mid | Deep-dive troubleshooting, bug fixing |
| MS-08 | Security & Compliance Analyst | Mid | Vulnerability scans, audit support |

---

## 4. Implementation Staffing Plan — 12 Months

### 4.1 Headcount by Phase

| Role | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 | M9 | M10 | M11 | M12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Delivery Manager (R-01) | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| Solution Architect (R-02) | 1 | 1 | 1 | 1 | 1 | 1 | — | — | — | — | — | — |
| AI/ML Engineer (R-03) | — | 1 | 2 | 2 | 2 | 2 | 2 | 1 | 1 | — | — | — |
| Data Engineer (R-04) | — | 1 | 1 | 2 | 2 | 2 | 2 | 2 | 1 | — | — | — |
| Backend Developer (R-05) | — | — | 2 | 2 | 2 | 2 | 2 | 2 | 1 | 1 | — | — |
| Frontend Developer (R-06) | — | — | 1 | 1 | 2 | 2 | 1 | 1 | — | — | — | — |
| Integration Specialist (R-07) | — | — | 1 | 1 | 2 | 2 | 2 | 1 | 1 | — | — | — |
| DevOps / SRE (R-08) | — | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| Test Lead / QA (R-09) | — | — | — | 1 | 1 | 1 | 2 | 2 | 2 | 2 | 1 | — |
| Business Analyst (R-10) | 1 | 2 | 1 | 1 | 1 | 1 | 1 | — | — | — | — | — |
| Change & Training (R-11) | — | — | — | — | — | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| Security Architect (R-12) | — | 1 | — | — | — | — | 1 | 1 | 1 | 1 | — | — |
| PMO Analyst (R-13) | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| **Total Headcount** | **4** | **9** | **12** | **14** | **16** | **16** | **15** | **13** | **11** | **7** | **5** | **4** |

### 4.2 FTE Cost Summary — Implementation

| Role | Days | Daily Rate (USD) | Total Cost (USD) |
|---|---|---|---|
| Delivery Manager | 240 | $1,500 | $360,000 |
| Solution Architect | 160 | $1,800 | $288,000 |
| AI/ML Engineers (avg 1.5 FTE) | 280 | $1,400 | $392,000 |
| Data Engineers (avg 1.5 FTE) | 260 | $1,300 | $338,000 |
| Backend Developers (avg 1.5 FTE) | 240 | $1,100 | $264,000 |
| Frontend Developer (avg 1 FTE) | 120 | $1,000 | $120,000 |
| Integration Specialist (avg 1 FTE) | 160 | $1,300 | $208,000 |
| DevOps / SRE | 220 | $1,200 | $264,000 |
| Test Lead / QA (avg 1.5 FTE) | 180 | $1,100 | $198,000 |
| Business Analyst | 120 | $1,000 | $120,000 |
| Change & Training Lead | 100 | $900 | $90,000 |
| Security Architect | 80 | $1,600 | $128,000 |
| PMO Analyst | 240 | $700 | $168,000 |
| **Risk Buffer (15%)** | | | **$276,600** |
| **Total Implementation** | | | **$3,014,600** |

---

## 5. Managed Service Staffing Plan — 4 Years

### 5.1 Steady-State Org Structure

```
Service Delivery Manager (MS-01)  [1 FTE]
    │
    ├── Application Support Lead (MS-02)  [1 FTE]
    │       └── Support Engineers L2/L3 (MS-07)  [2 FTE]
    │               └── Service Desk L1 (MS-06)  [2 FTE]
    │
    ├── AI Operations Engineer (MS-03)  [1 FTE]
    │
    ├── Data Operations Analyst (MS-04)  [1 FTE]
    │
    ├── Platform Engineer (MS-05)  [1 FTE]
    │
    └── Security & Compliance Analyst (MS-08)  [0.5 FTE]
```

**Total Steady-State Team Size: 9.5 FTE**

### 5.2 Managed Service Headcount by Year

| Role | Year 1 | Year 2 | Year 3 | Year 4 |
|---|---|---|---|---|
| Service Delivery Manager (MS-01) | 1.0 | 1.0 | 1.0 | 1.0 |
| Application Support Lead (MS-02) | 1.0 | 1.0 | 1.0 | 1.0 |
| AI Operations Engineer (MS-03) | 1.5 | 1.0 | 1.0 | 1.0 |
| Data Operations Analyst (MS-04) | 1.5 | 1.0 | 1.0 | 1.0 |
| Platform Engineer (MS-05) | 1.0 | 1.0 | 1.0 | 1.0 |
| Service Desk L1 (MS-06) | 2.0 | 2.0 | 2.0 | 2.0 |
| Support Engineer L2/L3 (MS-07) | 2.0 | 2.0 | 2.0 | 2.0 |
| Security & Compliance (MS-08) | 1.0 | 0.5 | 0.5 | 0.5 |
| **Total FTE** | **11.0** | **9.5** | **9.5** | **9.5** |

> **Year 1** is higher due to hypercare and knowledge transfer overlap from the implementation team.

### 5.3 Managed Service Cost by Year

| Year | FTE | Annual Cost (USD) |
|---|---|---|
| Year 1 | 11.0 | $1,540,000 |
| Year 2 | 9.5 | $1,330,000 |
| Year 3 | 9.5 | $1,330,000 |
| Year 4 | 9.5 | $1,330,000 |
| **Total 4 Years** | | **$5,530,000** |

---

## 6. RACI Matrix

| Activity | Partner Lead | Delivery Mgr | Sol. Architect | AI Engineer | Client |
|---|---|---|---|---|---|
| RFP Analysis | A | R | C | I | C |
| Solution Design | A | R | R | C | C |
| AI Model Development | I | A | C | R | I |
| Data Migration | I | A | C | C | R |
| Testing & QA | I | A | I | C | R |
| Go-Live Approval | R | A | C | I | R |
| Managed Service SLA Review | R | A | I | I | C |

**R** = Responsible | **A** = Accountable | **C** = Consulted | **I** = Informed

---

## 7. Onboarding & Knowledge Transfer Plan

### Implementation Team Onboarding (Month 1)
- [ ] Access provisioning (IBM Cloud, WatsonX, GitHub, ITSM tool)
- [ ] Project orientation: client background, RFP summary, solution overview
- [ ] Team operating model: stand-ups, sprint cadence, escalation paths
- [ ] Tool training: WatsonX.ai, WatsonX.data, WatsonX.governance
- [ ] Security and compliance briefing

### Managed Service Transition (Months 10–12)
- [ ] Shadow support: MS team shadows implementation team for 4 weeks
- [ ] Runbook documentation finalised
- [ ] Incident response playbooks created and validated
- [ ] AI model operational guide completed
- [ ] Formal handover sign-off by Delivery Manager and Service Delivery Manager

---

## 8. Staffing Risks & Mitigations

| Risk | Mitigation |
|---|---|
| Key resource unavailability | Maintain bench with 1 backup per critical role |
| Skill gap in WatsonX.governance | Schedule IBM training in Month 1 |
| Attrition during managed service | Cross-train all L2/L3 engineers across towers |
| Client SME unavailability | SLA clause for client resource commitment |
| Scope creep inflating headcount | Change control process enforced from Month 2 |

---

## 9. Output Artefacts

| Artefact | Format | Recipient |
|---|---|---|
| Staffing Plan (Implementation) | Excel / PDF | Partner, Delivery Lead |
| Managed Service Org Chart | Visio / PNG | Client, Service Delivery Manager |
| RACI Matrix | Excel | All Stakeholders |
| Onboarding Checklist | Markdown | HR, Team Leads |
| Resource Cost Summary | Excel | Finance, Commercial Director |
