# Orchestrator Agent — Multi-Agent Coordinator

> **Role:** Engagement Director / AI Orchestration Layer  
> **Controls:** Agent 1 → Agent 2 → Agent 3  
> **Stakeholder Interface:** Partner, Client, Delivery Lead

---

## 1. Purpose

The Orchestrator is the **central coordination layer** that:
- Triggers and sequences Agent 1 → Agent 2 → Agent 3
- Manages state and data handoff between agents
- Enforces quality gates before each agent transition
- Provides a unified engagement dashboard to the Partner
- Handles exceptions, re-runs, and human escalations

---

## 2. Orchestration Flow

```
                    ┌─────────────────────────────┐
                    │      PARTNER / CLIENT        │
                    │   Submits RFP Document       │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │        ORCHESTRATOR          │
                    │  - Validates RFP document    │
                    │  - Creates engagement record │
                    │  - Triggers Agent 1          │
                    └──────────────┬──────────────┘
                                   │
                    ┌──────────────▼──────────────┐
                    │          AGENT 1             │
                    │   RFP Analyzer &             │
                    │   Requirements Mapper        │
                    └──────────────┬──────────────┘
                                   │ Quality Gate 1
                                   │ (Human Review)
                    ┌──────────────▼──────────────┐
                    │          AGENT 2             │
                    │   Product Fitment &          │
                    │   Estimation Agent           │
                    └──────────────┬──────────────┘
                                   │ Quality Gate 2
                                   │ (Commercial Approval)
                    ┌──────────────▼──────────────┐
                    │          AGENT 3             │
                    │   Staffing & Resource        │
                    │   Planning Agent             │
                    └──────────────┬──────────────┘
                                   │ Quality Gate 3
                                   │ (Delivery Approval)
                    ┌──────────────▼──────────────┐
                    │     FINAL DELIVERABLE        │
                    │  Proposal Package Ready      │
                    │  (RFP Response + SOW + Plan) │
                    └─────────────────────────────┘
```

---

## 3. Orchestrator Responsibilities

### 3.1 Engagement Lifecycle Management

| Stage | Orchestrator Action |
|---|---|
| **Initiation** | Validate RFP, create engagement ID, initialise state store |
| **Agent 1 Trigger** | Pass RFP doc + product catalogue to Agent 1; set timeout |
| **Quality Gate 1** | Check all requirements mapped; flag gaps; notify reviewer |
| **Agent 2 Trigger** | Pass Agent 1 JSON output + rate card to Agent 2 |
| **Quality Gate 2** | Validate cost model; check buffer applied; commercial review |
| **Agent 3 Trigger** | Pass Agent 2 JSON output + resource pool to Agent 3 |
| **Quality Gate 3** | Validate staffing plan; headcount vs. effort reconciliation |
| **Package Assembly** | Compile all outputs into final Proposal Package |
| **Delivery** | Notify Partner; archive all artefacts |

### 3.2 State Management

The Orchestrator maintains a **central state object** for each engagement:

```json
{
  "engagement_id": "ENG-2026-001",
  "client": "Client Name",
  "rfp_received": "2026-01-10T09:00:00Z",
  "status": "Agent3_InProgress",
  "agents": {
    "agent1": {
      "status": "Completed",
      "output_path": "outputs/ENG-2026-001/agent1_output.json",
      "completed_at": "2026-01-12T14:00:00Z",
      "quality_gate_passed": true,
      "reviewer": "John Smith"
    },
    "agent2": {
      "status": "Completed",
      "output_path": "outputs/ENG-2026-001/agent2_output.json",
      "completed_at": "2026-01-14T11:00:00Z",
      "quality_gate_passed": true,
      "reviewer": "Jane Doe"
    },
    "agent3": {
      "status": "InProgress",
      "output_path": null,
      "completed_at": null,
      "quality_gate_passed": false,
      "reviewer": null
    }
  },
  "final_package_ready": false
}
```

### 3.3 Exception Handling

| Exception | Orchestrator Response |
|---|---|
| Agent times out | Retry once; escalate to human if second timeout |
| Quality gate fails | Return to originating agent with reviewer comments |
| Missing input data | Pause engagement; notify Partner; request missing data |
| Conflicting outputs | Flag to human reviewer; hold handoff until resolved |
| Scope change mid-run | Re-trigger affected agents; version-stamp all outputs |

---

## 4. Quality Gates Summary

| Gate | After Agent | Reviewer | Pass Criteria |
|---|---|---|---|
| QG-1 | Agent 1 | Solution Architect | All reqs mapped, fit scores validated |
| QG-2 | Agent 2 | Commercial Director | Cost model approved, assumptions signed off |
| QG-3 | Agent 3 | Delivery Lead | Staffing plan reconciled with effort; RACI complete |

---

## 5. Final Proposal Package

Upon successful completion of all three agents and quality gates, the Orchestrator assembles:

| Document | Generated By | Format |
|---|---|---|
| Requirements Mapping Matrix | Agent 1 | Excel / JSON |
| Pain Area Heatmap | Agent 1 | PDF |
| Executive Summary | Agent 1 | Word / PDF |
| Effort Estimation Report | Agent 2 | Excel / PDF |
| Commercial Cost Summary | Agent 2 | Excel / PDF |
| Implementation Staffing Plan | Agent 3 | Excel / PDF |
| Managed Service Org Chart | Agent 3 | Visio / PDF |
| RACI Matrix | Agent 3 | Excel |
| **Master Proposal Document** | Orchestrator | Word / PDF |

---

## 6. Engagement KPIs

| KPI | Target |
|---|---|
| Time from RFP receipt to proposal ready | ≤ 5 business days |
| Requirements coverage (% mapped) | 100% |
| Estimation accuracy (vs. actuals on past projects) | ±15% |
| Quality gate pass rate (first attempt) | ≥ 80% |
| Partner satisfaction with proposal quality | ≥ 4.5 / 5 |
