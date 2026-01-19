# Incident Scenario – Primary Data Center Outage

## Background

This disaster recovery program assumes a mid‑size organization running a critical financial/billing platform in a primary data center, with limited cloud presence and a warm secondary site.

## Scenario

During the month‑end billing cycle, the primary data center in Dallas experiences a combined **power and cooling failure** that lasts longer than the UPS and on‑site generators can sustain. The outage happens at 2:15 AM local time, during a peak batch processing window.

- Core databases and application servers become unavailable.
- Customer‑facing portals start timing out.
- Batch jobs fail mid‑run, leaving partial data written.
- Internal users cannot access reporting systems.

## Business Impact

- Lost ability to process new transactions for several hours.
- Risk of data inconsistency between partially processed jobs.
- Breach of published SLA (4‑hour maximum downtime for the billing platform).
- Reputational impact if customers cannot see up‑to‑date balances.

## Recovery Objectives

- **RTO (Recovery Time Objective):** 4 hours for critical services.
- **RPO (Recovery Point Objective):** 15 minutes for transactional data.

## Activation of Project Artifacts

When this incident occurs, the following elements of the DR project are activated:

- **Gantt Chart** – Execution of phases “Infrastructure Recovery Planning”, “Communication Strategy”, and “Testing & Validation” reflects how the organization should have prepared for this exact outage. (See `/artifacts/Gantt_Chart.xlsx`.)
- **RACI Matrix** – Clarifies who is Responsible and Accountable during activation:
  - IT is **R** for technical failover and validation.
  - PM is **R** for coordination and status tracking.
  - Operations is **A/R** for business process validation.
  - Leadership is **A** for major decisions and external communications. (See `/artifacts/RACI_Matrix.xlsx`.)
- **Stakeholder Communication Plan** – Drives which channels are used to notify executives, operations, and affected teams as the incident unfolds. (See `/docs/Stakeholder_Communication_Plan.md`.)

## Success Criteria

The DR response is considered successful if:

- Critical billing services are restored at the secondary site within 4 hours.
- No more than 15 minutes of data is lost or requires manual reconciliation.
- Stakeholders receive timely, structured updates during and after the event.
- A post‑incident review generates action items that are tracked to closure.
