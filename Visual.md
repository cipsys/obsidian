
## Analytics Dashboard
```
You are responsible for monitoring the traffic into a Health Network Information Exchange that processes HL7v2 particularly ADT messages. 

I want you to come up with a design of a dashboard that allows tracking traffic in the network by message types, errors, per customer. 

Dashboard should allow to analyze volumes and be useful to recover costs based on these volumes at customer level. It should allow filtering by timerange, customers, message type, etc.

The UI should support dark/light mode and the user should be able to switch between them. The UI should repsect the best material design practices and be responsive.

```

## Health Claims Processor
```markdown

Build a **two-screen React application** for a health plan claims adjudication workstation. The system should reflect a professional, high-density clinical/government operations aesthetic — think air traffic control meets medical records — not a generic SaaS dashboard.

---

**SCREEN 1: Claims Work Queue (Landing Page)**

A prioritized work queue for claims assigned to the logged-in adjudicator.

**Stats Bar (top):**

- Total claims in queue
- Claims pending today
- Average processing time
- Approval rate
- FWA flags count (claims flagged for Fraud, Waste & Abuse)

**Claims Queue Table/List:** Each row represents a claim and must show:

- Claim ID
- Member name + Member ID
- Provider name + NPI
- Service date
- Claim type (Professional / Institutional / Dental / Rx)
- Billed amount
- FWA Risk Score (0–100) displayed as a color-coded badge (green → yellow → red)
- Status (Pending Review / Needs Info / Escalated / On Hold)
- Age of claim (days in queue)
- Priority indicator (urgent, normal, low)

Clicking a row navigates to Screen 2 (claim detail view).

---

**SCREEN 2: Claim Detail — AI-Assisted Adjudication View**

A focused, context-rich workstation for reviewing and deciding on a single claim. Layout should be split into logical panels:

**Left Panel — Claim & Clinical Context:**

- Claim header: Claim ID, received date, claim type, payer, plan
- Member card: name, DOB, member ID, plan type, eligibility status, deductible met/remaining, out-of-pocket status
- Provider card: name, NPI, specialty, network status (in/out), prior authorization status
- Service lines table: procedure codes (CPT/HCPCS/ICD-10), description, units, billed amount, allowed amount, patient responsibility
- Diagnosis codes (ICD-10) with descriptions
- Attachments / supporting documents list

**Right Panel — AI Copilot Chat Interface:** A persistent chat interface with full awareness of the current claim context (member, provider, service lines, diagnosis, history). The copilot should be able to:

- Answer adjudicator questions about coverage, policy rules, coding guidelines
- Surface similar historical claims for reference
- Explain the FWA risk score and its contributing factors
- Suggest a recommended adjudication decision with rationale
- Flag missing information or required documents
- Answer natural language questions: _"Is this procedure covered under this plan?"_, _"Has this provider had prior claims denied?"_

The chat input should be prominent, with suggested prompt chips (quick-action buttons) like:

- "Explain FWA risk factors"
- "Check coverage for this procedure"
- "Summarize member history"
- "Recommend decision"
- "What's missing?"

**FWA Risk Panel (visible, prominent):**

- Large numeric score (0–100) with risk tier label: No Risk / Low / Moderate / High / Critical
- Visual gauge or ring indicator
- Top contributing risk signals listed (e.g., "Unbundling pattern detected", "Provider billing anomaly", "Duplicate claim within 30 days")

**Decision Panel (bottom or sidebar):**

- Adjudication decision selector: Approve / Deny / Pend / Request Additional Info / Escalate to SIU
- Denial reason code selector (if deny selected)
- Notes / audit trail text area
- Submit / Save Draft buttons

---

**Data:** Use realistic mock/static data. Include at least 8–10 claims in the queue with varied statuses, claim types, and FWA scores. Claim detail should feel fully populated — no empty states.

```
