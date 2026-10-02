
## HL7v2 ADT Message Processing

The platform ingests HL7v2 ADT (Admission, Discharge, Transfer) messages — the standard format emitted by hospital EMR and HIE systems when patients are admitted, transferred, or discharged.

### Supported ADT Event Types

| Event | Description                | Simulated Frequency |
| ----- | -------------------------- | ------------------- |
| A04   | Register/Admit patient     | 80%                 |
| A01   | Admit patient (inpatient)  | 15%                 |
| A08   | Update patient information | 3%                  |
| A03   | Discharge patient          | 2%                  |
  
### ADT Message Anatomy

Each ADT message carries a full clinical snapshot:

```
MSH — Message header (event type, facility, timestamp)
EVN — Event type record
PID — Patient demographics (ID, name, DOB, sex, county FIPS)
NK1 — Next of kin
PV1 — Patient visit class (Emergency vs Inpatient)
IN1 — Insurance
AL1 — Allergies
DG1 — Diagnosis codes (ICD-10)
OBX — Observations: vitals AND lab results (LOINC-coded)
```

**Important:** Lab results are embedded as OBX segments within the ADT message itself — the platform does not currently ingest separate ORU (lab result) feeds. This simplifies integration while still enabling lab-based case classification from the clinical data present at admit/discharge time.

---
## Three-Tier Classification Hierarchy
Every incoming ADT flows through a deterministic scoring pipeline that assigns cases to one of three confirmation tiers (plus a gray zone that triggers AI evaluation):

### Tier 1: ICD-10 Definitive (Confidence: 100%)
The highest-certainty classification. Triggered when a DG1 segment contains a billing diagnosis code that directly matches the tracked condition.
- **Example:** `B33.4` (Hantavirus cardiopulmonary syndrome)
- **Meaning:** A clinician has already diagnosed this condition
- **Action:** Immediate case creation, no further scoring needed

### Tier 2: Lab Confirmed (Confidence: 95%)
Triggered when OBX lab segments contain a LOINC code matching a configured lab marker AND the result value matches known positive indicators.
- **Matching logic:** Exact LOINC code match + case-insensitive value comparison against configured `positive_values` (e.g., "positive", "detected", "reactive")
- **Example:** LOINC `94500-6` (SARS-CoV-2 RNA) with value "Detected"
- **Meaning:** Laboratory evidence confirms infection, even without a formal diagnosis code

### Tier 3: Syndromic (Confidence: 50–94%)
When neither ICD-10 codes nor lab markers trigger, the system extracts clinical symptoms from vitals and lab observations using configurable extraction rules:
- **Extraction rules:** LOINC code + threshold + operator → emitted symptom (e.g., temp ≥ 38.0°C → "fever")
- **Weighted scoring:** High-priority symptoms (20pts), medium (12pts), low (5pts)
- **Boosters:** Geographic proximity to known clusters, temporal alignment with expected seasonality, epidemiological risk factors

### Gray Zone → LLM Evaluation
Cases scoring between the gray-zone minimum and the match threshold are escalated to an LLM (Claude) for clinical reasoning:
- **Input:** Full condition definition (diagnostic criteria, epidemiology, differentials) + county epi profile + patient clinical details
- **Output:** Structured verdict — match (yes/no), confidence (50–95%), one-sentence clinical reasoning
- **Value:** Catches atypical/early presentations that rigid rules miss, while keeping an auditable reasoning trail- 

---
## Tracked Conditions
The platform ships with three high-impact pathogen configurations:

| Condition          | ICD-10       | CFR      | Transmission                                                 |
| ------------------ | ------------ | -------- | ------------------------------------------------------------ |
| Hantavirus (Andes) | B33.4        | ~38%     | Aerosolized rodent excreta; person-to-person (Andes variant) |
| Influenza A H3N2   | J10.x, J11.x | 0.1–0.2% | Airborne/droplet; R0 1.3–2.5                                 |
| Ebola (Zaire)      | A98.4        | 60–70%   | Direct contact with blood/secretions                         |

New conditions are added via configuration (ICD-10 codes, LOINC markers, symptom maps, geographic risk zones) — no code changes required.

---
## Key Platform Capabilities
- **Real-time SSE streaming** — Live case detections, tier upgrades, and KPI updates pushed to all connected dashboards

- **Interactive geographic intelligence** — Deck.GL maps with county-level choropleth, pulse animations at detection coordinates, and drill-down analytics

- **Scenario simulation engine** — LLM-generated outbreak scenarios with realistic ADT message production, phased spread mechanics, and configurable playback speed

- **Conversational AI chat** — Context-aware queries against live tracker state for epidemiological analysis and forecasting

- **Extensible tracker architecture** — Add new pathogens via config; each tracker maintains independent case databases and scoring rules

---
## Talk Track

### The Problem (30 seconds)
Today, outbreak detection relies on manual chart reviews and delayed batch reporting. Borderline cases — a patient with fever and travel history but no definitive lab yet — sit in limbo while epidemiologists debate classification. Meanwhile, the outbreak clock is ticking. Every 48 hours of delay in early detection can mean exponential community spread.

### Opening (30 seconds)
Pandemic Tracker is an AI-powered disease surveillance platform that detects emerging outbreaks in real time by processing the same clinical messages hospitals already send — ADT feeds. Instead of waiting days for CDC reporting, public health teams see new cases the moment a patient hits a hospital with matching symptoms, lab results, or diagnosis codes.


### How It Works (60 seconds)
We plug into existing hospital data feeds — standard HL7 ADT messages — and run every admission through a three-tier classification engine:

First, we check for definitive diagnosis codes. If a clinician already coded Hantavirus, that's an immediate confirmed case.

Second, we look at embedded lab results. A positive PCR or antigen test triggers lab-confirmed status at 95% confidence — even before the billing code catches up.

Third, we extract symptoms from vitals and observations. Fever plus respiratory distress plus geographic proximity to a known cluster builds a syndromic case with weighted confidence scoring.

The breakthrough is what happens in the gray zone. When a case scores between thresholds — not clearly positive, not clearly negative — we escalate to an AI clinical reasoner. It evaluates the full clinical picture against the condition's diagnostic criteria and local epidemiological context, and returns a structured verdict with transparent reasoning. This catches early and atypical presentations that rule-based systems miss.

### Differentiation (30 seconds)
Unlike legacy surveillance systems, every classification decision has an auditable reasoning trail. Unlike commercial outbreak detection services, the AI reasoning is transparent and runs on your infrastructure — no black boxes. And unlike academic EHR projects, this is production-ready today with real-time streaming, interactive maps, and scenario simulation for training and capacity planning.
  