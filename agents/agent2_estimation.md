# Agent 2 — Product Fitment & Estimation Agent

> **Role:** Delivery Architect / Estimation Lead  
> **Reports To:** Orchestrator Agent  
> **Receives From:** Agent 1 (RFP Analyzer)  
> **Feeds Into:** Agent 3 (Staffing Agent)

---

## 1. Agent Purpose

Agent 2 consumes the structured requirements mapping output from Agent 1 and produces a **detailed effort estimation** broken down by:

- Implementation workstreams
- Delivery phases (12-month implementation)
- Managed service scope (4-year post-go-live)
- Cost model (T&M and Fixed Price views)
- Assumptions and exclusions

---

## 2. Inputs

| Input | Format | Source |
|---|---|---|
| Requirements Mapping Matrix | JSON | Agent 1 Output |
| Effort Estimation Templates | Excel / JSON | PMO Library |
| Rate Card | JSON | Finance / Commercial Team |
| Historical Project Data | JSON | Delivery CRM |
| Product Complexity Matrix | Markdown | Architecture Team |

---

## 3. Estimation Methodology

### 3.1 Estimation Approach — Three-Point Estimation

For each work item, estimate using:

```
E = (O + 4M + P) / 6
```
Where:
- **O** = Optimistic estimate (best case)
- **M** = Most Likely estimate
- **P** = Pessimistic estimate (worst case)
- **E** = Expected effort in person-days

### 3.2 Work Breakdown Structure (WBS)

Each requirement is decomposed into tasks across these activity types:

| Activity Code | Activity Type | Typical % of Total Effort |
|---|---|---|
| ACT-01 | Discovery & Workshops | 8% |
| ACT-02 | Solution Design & Architecture | 10% |
| ACT-03 | Configuration & Development | 35% |
| ACT-04 | Integration Development | 15% |
| ACT-05 | Data Migration | 10% |
| ACT-06 | Testing (Unit, Integration, UAT, Performance) | 12% |
| ACT-07 | Training & Change Management | 5% |
| ACT-08 | Deployment & Go-Live Support | 5% |

### 3.3 Complexity Multipliers

Applied to base estimates based on fit score from Agent 1:

| Fit Score | Complexity | Multiplier |
|---|---|---|
| 5 | Trivial | 1.0x |
| 4 | Low | 1.2x |
| 3 | Medium | 1.5x |
| 2 | High | 2.0x |
| 1 | Very High (Custom Build) | 2.8x |

### 3.4 Risk Buffer
- **Low Risk Project:** +10% contingency
- **Medium Risk Project:** +15% contingency
- **High Risk Project:** +20% contingency

---

## 4. Implementation Estimation — 12-Month Plan

### Phase Breakdown

| Phase | Duration | Focus |
|---|---|---|
| **Phase 0** — Mobilisation | Month 1 | Project setup, governance, environment provisioning |
| **Phase 1** — Discovery & Design | Months 1–2 | Workshops, detailed design, architecture sign-off |
| **Phase 2** — Core Build | Months 3–6 | Platform configuration, core feature development |
| **Phase 3** — Integration & Data | Months 5–8 | Integration layer, data migration, ETL pipelines |
| **Phase 4** — Testing & Hardening | Months 7–10 | SIT, UAT, performance, security testing |
| **Phase 5** — Go-Live & Stabilisation | Months 10–12 | Cutover, go-live, hypercare (30–60 days) |

### Effort Estimation Output (sample)

```json
{
  "project_id": "PROJ-2026-001",
  "estimated_by": "Agent2",
  "estimation_model": "Three-Point",
  "total_effort_days": 1240,
  "phases": [
    {
      "phase": "Phase 0 - Mobilisation",
      "months": "Month 1",
      "effort_days": 40,
      "activities": ["Project kickoff", "Environment setup", "Governance framework"]
    },
    {
      "phase": "Phase 1 - Discovery & Design",
      "months": "Months 1-2",
      "effort_days": 120,
      "activities": ["Stakeholder workshops", "AS-IS process mapping", "TO-BE design", "Architecture review"]
    },
    {
      "phase": "Phase 2 - Core Build",
      "months": "Months 3-6",
      "effort_days": 480,
      "activities": ["Platform configuration", "AI model integration", "Core feature dev", "Unit testing"]
    },
    {
      "phase": "Phase 3 - Integration & Data",
      "months": "Months 5-8",
      "effort_days": 280,
      "activities": ["API development", "Data migration scripts", "ETL pipelines", "Interface testing"]
    },
    {
      "phase": "Phase 4 - Testing & Hardening",
      "months": "Months 7-10",
      "effort_days": 200,
      "activities": ["SIT", "UAT", "Performance testing", "Security pen test"]
    },
    {
      "phase": "Phase 5 - Go-Live & Stabilisation",
      "months": "Months 10-12",
      "effort_days": 120,
      "activities": ["Cutover planning", "Go-live execution", "Hypercare", "Knowledge transfer"]
    }
  ],
  "risk_buffer_pct": 15,
  "total_with_buffer_days": 1426,
  "currency": "USD",
  "blended_daily_rate": 1200,
  "total_cost_estimate": 1711200
}
```

---

## 5. Managed Service Estimation — 4-Year Plan

### Service Tower Breakdown

| Service Tower | Description | Annual Effort (days) |
|---|---|---|
| **ST-01** Application Management | Break-fix, patches, enhancements backlog | 300 |
| **ST-02** Platform Operations | Infrastructure monitoring, upgrades, capacity | 180 |
| **ST-03** AI Model Management | Model drift monitoring, retraining, governance | 120 |
| **ST-04** Data Operations | Data pipeline monitoring, quality, reconciliation | 150 |
| **ST-05** Security & Compliance | Vulnerability management, audits, certifications | 80 |
| **ST-06** Service Desk (L1/L2) | Incident, problem, change management | 240 |
| **ST-07** Reporting & Analytics | Dashboard maintenance, new report development | 60 |

### Managed Service SLA Tiers

| Priority | Response Time | Resolution Time |
|---|---|---|
| P1 — Critical | 30 minutes | 4 hours |
| P2 — High | 2 hours | 8 hours |
| P3 — Medium | 4 hours | 2 business days |
| P4 — Low | 1 business day | 5 business days |

### 4-Year Managed Service Cost Model

| Year | Scope | Effort (days) | Est. Cost (USD) |
|---|---|---|---|
| Year 1 (Post Go-Live) | Full towers + hypercare tail | 1,250 | $1,500,000 |
| Year 2 | Steady state + minor enhancements | 1,130 | $1,356,000 |
| Year 3 | Steady state + platform upgrade | 1,180 | $1,416,000 |
| Year 4 | Steady state + renewal negotiation | 1,100 | $1,320,000 |
| **Total** | | **4,660** | **$5,592,000** |

---

## 6. Total Commercial Summary

| Component | Effort (days) | Cost (USD) |
|---|---|---|
| 12-Month Implementation | 1,426 | $1,711,200 |
| 4-Year Managed Service | 4,660 | $5,592,000 |
| **Grand Total (5 Years)** | **6,086** | **$7,303,200** |

---

## 7. Assumptions & Exclusions

### Assumptions
- Client provides timely access to SMEs, data, and environments.
- No more than 2 major scope changes during implementation.
- Client owns infrastructure licensing costs (IBM Cloud, WatsonX subscriptions).
- Legacy data quality is within acceptable thresholds for migration.
- UAT conducted by client team with Partner support.

### Exclusions
- Third-party software licensing and procurement.
- Hardware procurement.
- Business process re-engineering beyond defined scope.
- Training of more than 2 cohorts of end users.

---

## 8. Handoff to Agent 3

Agent 2 passes the following to **Agent 3 (Staffing Agent)**:

```json
{
  "phase_effort_days": "<per_phase_breakdown>",
  "managed_service_towers": "<per_tower_annual_days>",
  "skill_requirements": "<inferred_from_wbs>",
  "timeline": "12 months implementation + 48 months managed service",
  "peak_headcount_period": "Months 3-8",
  "total_project_cost": 7303200
}
```

---

## 9. Quality Gates

- [ ] Estimation reviewed against 3 comparable historical projects.
- [ ] Three-point estimates completed for all work items.
- [ ] Risk buffer applied and justified.
- [ ] Commercial summary approved by Partner / Commercial Director.
- [ ] Assumptions and exclusions signed off by Delivery Lead.
