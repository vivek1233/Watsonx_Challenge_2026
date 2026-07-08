# Agent 1 — RFP Analyzer & Requirements Mapper

> **Role:** Senior Solution Consultant / Pre-Sales Architect  
> **Reports To:** Orchestrator Agent  
> **Feeds Into:** Agent 2 (Product Fitment & Estimation)

---

## 1. Agent Purpose

Agent 1 is the **entry point** of the multi-agent framework. It ingests a raw Request for Proposal (RFP) document and produces a structured output covering:

- Decoded client asks (explicit and implicit)
- Pain area identification
- Product fitment mapping
- Requirement classification and prioritisation
- Risk & gap analysis

---

## 2. Inputs

| Input | Format | Source |
|---|---|---|
| RFP Document | PDF / Word / Text | Client / Procurement Portal |
| Product Catalogue | JSON / Markdown | Internal Knowledge Base |
| Industry Templates | Markdown | Pre-Sales Library |
| Previous RFP Learnings | JSON | Historical CRM Data |

---

## 3. Processing Steps

### Step 1 — Document Ingestion & Parsing
- Extract all sections from the RFP (scope, SLAs, technical requirements, commercial terms, evaluation criteria).
- Identify document structure: sections, sub-sections, tables, appendices.
- Strip boilerplate and focus on requirement-carrying content.

### Step 2 — Client Ask Extraction
Classify every requirement statement into one of:

| Category | Description |
|---|---|
| **Functional Ask** | What the system must do (features, workflows, integrations) |
| **Non-Functional Ask** | Performance, security, scalability, availability targets |
| **Commercial Ask** | Budget constraints, pricing model preference, licensing |
| **Compliance Ask** | Regulatory, data residency, audit, certifications required |
| **Operational Ask** | Support model, SLAs, incident response, managed services |
| **Strategic Ask** | Digital transformation goals, business outcomes expected |

### Step 3 — Pain Area Identification
Map each ask to a **pain area** using the following taxonomy:

| Pain Area Code | Description |
|---|---|
| PA-01 | Legacy system modernisation |
| PA-02 | Data silos and lack of unified analytics |
| PA-03 | Manual / inefficient business processes |
| PA-04 | Poor customer experience / engagement |
| PA-05 | Compliance and regulatory risk |
| PA-06 | Scalability bottlenecks |
| PA-07 | Security vulnerabilities |
| PA-08 | High operational costs |
| PA-09 | Lack of AI / ML capabilities |
| PA-10 | Integration complexity |

### Step 4 — Product Fitment Mapping
For each identified requirement, map to the best-fit product / module from the product catalogue:

```
Requirement → Pain Area → Recommended Product/Module → Fit Score (1–5) → Gaps
```

**Fit Score Definition:**
- **5** — Full out-of-the-box fit
- **4** — Fit with minor configuration
- **3** — Fit with moderate customisation
- **2** — Partial fit; significant development needed
- **1** — No fit; third-party or custom build required

### Step 5 — Overall Client Ask Summary
Produce a one-page executive summary covering:
- Client's top 3 business objectives
- Critical success factors
- Must-have vs. nice-to-have requirements
- Key risks and unknowns

---

## 4. Outputs

### 4.1 Requirements Mapping Matrix

```json
{
  "rfp_id": "RFP-2026-001",
  "client": "Client Name",
  "analyzed_by": "Agent1",
  "timestamp": "2026-01-01T00:00:00Z",
  "requirements": [
    {
      "req_id": "REQ-001",
      "section": "3.2",
      "raw_text": "The system must support single sign-on (SSO) via SAML 2.0.",
      "category": "Non-Functional Ask",
      "pain_area": "PA-07",
      "priority": "Must Have",
      "recommended_product": "IBM App ID",
      "fit_score": 5,
      "gap": "None",
      "notes": "Native SAML 2.0 support available."
    }
  ],
  "pain_areas_summary": ["PA-07", "PA-09", "PA-02"],
  "overall_client_ask": "Modernise legacy data platform with AI capabilities and enterprise security.",
  "critical_success_factors": ["Data migration < 3 months", "Zero downtime cutover", "GDPR compliance from day 1"],
  "must_have_count": 12,
  "should_have_count": 8,
  "nice_to_have_count": 5
}
```

### 4.2 Pain Area Heatmap (summary table)

| Pain Area | Req Count | Severity | Product Coverage |
|---|---|---|---|
| PA-09 (AI/ML) | 6 | Critical | WatsonX.ai |
| PA-02 (Data Silos) | 4 | High | WatsonX.data |
| PA-07 (Security) | 3 | High | IBM App ID + Guardium |
| PA-05 (Compliance) | 2 | Medium | WatsonX.governance |

### 4.3 Executive Summary Document
- 1-page narrative for Partner / Client leadership review.

---

## 5. Handoff to Agent 2

Agent 1 passes the following structured payload to **Agent 2 (Estimation Agent)**:

```json
{
  "requirements_matrix": "<path_to_json>",
  "fit_scores": "<aggregated_fit_scores>",
  "gap_list": "<list_of_gaps>",
  "complexity_rating": "High | Medium | Low",
  "total_requirements": 25
}
```

---

## 6. Quality Gates

Before handoff, Agent 1 must validate:
- [ ] All RFP sections have been processed.
- [ ] Every requirement has a pain area, category, priority, and fit score.
- [ ] At least one recommended product is mapped per requirement.
- [ ] Executive summary reviewed by a human Solution Architect.
- [ ] Fit score < 3 requirements flagged for Partner review.

---

## 7. Human-in-the-Loop Checkpoints

| Checkpoint | Reviewer | Action |
|---|---|---|
| Requirements completeness | Solution Architect | Approve / Add missed reqs |
| Product fitment validation | Product SME | Validate fit scores |
| Client ask summary | Partner / Delivery Lead | Approve before Agent 2 trigger |
