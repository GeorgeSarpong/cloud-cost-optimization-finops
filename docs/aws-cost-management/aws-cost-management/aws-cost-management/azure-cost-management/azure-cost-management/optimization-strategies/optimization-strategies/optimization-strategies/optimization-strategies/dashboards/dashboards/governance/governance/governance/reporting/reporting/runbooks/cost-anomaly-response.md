# Cost Anomaly Response Runbook

**Document Type:** FinOps Runbook
**Author:** George Amankwaa Sarpong
**Last Updated:** June 2026

---

## Purpose
Standardised procedure for detecting, investigating, and resolving unexpected cloud cost anomalies across AWS and Azure environments.

---

## Trigger Conditions
- Budget threshold exceeded by 10% or more
- Daily spend 50% higher than previous day average
- New unexpected service charges
- Reserved instance utilization below 80%
- Cost anomaly detection alert fired

---

## Severity Classification

| Severity | Condition | Response Time |
|---|---|---|
| P1 — Critical | Budget exceeded by 50%+ | Immediate |
| P2 — High | Budget exceeded by 25–50% | 30 minutes |
| P3 — Medium | Budget exceeded by 10–25% | 2 hours |
| P4 — Low | Approaching budget threshold | Next business day |

---

## Response Steps

### Phase 1 — Detection
1. Acknowledge cost anomaly alert
2. Log incident ticket with cost details
3. Capture current spend vs budget figures
4. Identify affected account and region

### Phase 2 — Investigation
1. Open AWS Cost Explorer or Azure Cost Analysis
2. Filter by date range of anomaly
3. Drill down by service to identify source
4. Review CloudTrail for resource creation events
5. Check for rogue or misconfigured resources

### Phase 3 — Containment
1. If rogue resources — terminate immediately
2. If misconfigured — correct and document
3. If legitimate business need — update budget
4. Apply SCPs or policies to prevent recurrence

### Phase 4 — Resolution
1. Confirm spend returning to normal
2. Update monitoring thresholds if needed
3. Document root cause and resolution
4. Schedule post-incident review
5. Close incident ticket

---

## Prevention Checklist
- [ ] Budget alerts set at 50%, 75%, 90%, 100%
- [ ] AWS Cost Anomaly Detection enabled
- [ ] All resources properly tagged
- [ ] IAM permissions follow least privilege
- [ ] Regular monthly cost reviews scheduled
- [ ] Reserved instance utilization monitored weekly
