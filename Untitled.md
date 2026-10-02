For a modern AI/software prototyping team, the intake process should optimize for **speed, learning, and strategic alignment**, not governance. 

A good intake process should answer one question: **“Is this worth spending the next 1-2 weeks learning?”**

---

# **Stage 0 — Self-Service Discovery (Optional)**

Before someone even requests a prototype, give them:
- examples of previous prototypes
- reusable components
- LLM capabilities catalog
- FAQ
- prompt engineering examples
- architecture patterns

Many requests disappear once people realize something already exists.

---

# **Stage 1 : Lightweight Intake**

Instead of a 20-page template, use a 5 minute form.

| **Question**                          | **Why**                            |
| ------------------------------------- | ---------------------------------- |
| What problem are you trying to solve? | Focuses on business need           |
| Who is the user?                      | Prevents technology-first thinking |
| What does success look like?          | Defines measurable outcome         |
| Why now?                              | Determines urgency                 |
| Have you tried anything already?      | Avoids repeating work              |
| Who will champion this?               | Ensures ownership                  |

---

# **Stage 2 : 30 Minute Discovery**

This is the most important step. Rather than reading documents, have a conversation.

**Agenda:**
- Explain the problem
- Whiteboard current process
- Identify assumptions
- Challenge and narrow down scope
- Identify data sources & data requierments
- Define success criteria

---

# **Stage 3: Scoring & Estimation** 

Keep scoring intentionally lightweight. The goal is prioritization, not precision.

| **Criteria**        | **Score**                     |
| ------------------- | ----------------------------- |
| Strategic alignment | High / Med / Low              |
| Business value      | High / Med / Low              |
| AI fit              | High / Med / Low              |
| Technical risk      | High / Med / Low              |
| Time to prototype   | <5 days / <10 days / >10 days |

---

# **Stage 4:  Prototype Definition**

Every prototype should answer:

**Hypothesis**

“We believe AI can reduce proposal review time by 50%.”

**Success Criteria**

Example:

- summarize document
- accuracy >90%
- users prefer it
- response under 10 seconds

**Timebox**

Usually:

- 5 days
- 10 days
- absolute maximum 2 weeks

---

# **Stage 5 — Prototype Sprint**

No daily standups.

No sprint planning.

Just:

- kickoff
- mid-point demo
- final demo

The team spends nearly all its time building.

---

# **Stage 6 — Demo & Decision**

Every prototype ends with one of four outcomes:

✅ Kill it

Not valuable.

✅ Learn

Interesting idea but needs refinement.

✅ Another prototype

A second experiment is justified.

✅ Graduate

Ready for engineering production.

The prototype team should never own production implementation.

---

# **Intake Board**

A simple Kanban board is usually enough:

```
Ideas

↓

Discovery

↓

Ready

↓

Building

↓

Demo

↓

Graduated

↓

Archived
```

No complicated workflows.

---

# **Service Level Expectations**

Set clear expectations:

|**Stage**|**SLA**|
|---|---|
|Intake review|2 business days|
|Discovery meeting|5 business days|
|Prioritization|Weekly|
|Prototype duration|5–10 business days|
|Final recommendation|Within 2 weeks|

This creates predictability without unnecessary bureaucracy.

---

# **Intake One-Pager**

Each request should fit on a single page:

```
Title

Business Problem

Current Process

Desired Future

Users

Expected Value

Data Sources

Prototype Hypothesis

Success Metrics

Estimated Effort

Sponsor

Decision
```

If it doesn’t fit on one page, the request is probably too large for a prototype.

---

# **AI-Specific Additions**

For AI prototypes, capture a few extra details up front:

- **Primary use case:** chat, agent, RAG, document processing, workflow automation, code generation, etc.
- **Available data:** where it lives, quality, sample availability, and any access restrictions.
- **Security/compliance:** sensitivity of the data (e.g., public, internal, regulated).
- **Expected human involvement:** fully automated, human-in-the-loop, or decision support.
- **Evaluation approach:** how you’ll measure quality (accuracy, latency, cost, user satisfaction, task completion rate).

These questions help determine whether the request is technically feasible before development begins.

## **What this looks like in practice**

For a high-performing innovation or rapid prototyping team—similar to the Rapid Prototyping Team (RPT) model you’ve described previously—a practical flow is:

```text
Idea Submitted
        │
        ▼
5-Minute Intake Form
        │
        ▼
30-Minute Discovery Session
        │
        ▼
Weekly Triage (Go / Park / Reject)
        │
        ▼
Prototype Charter (1 page)
        │
        ▼
5–10 Day Build
        │
        ▼
Midpoint Demo
        │
        ▼
Final Demo
        │
        ▼
Graduate • Iterate • Archive
```

This approach minimizes administrative overhead while ensuring that every prototype has a clear business hypothesis, a committed sponsor, a short delivery window, and a deliberate decision point. It keeps the team’s focus on rapid learning and validating ideas rather than managing lengthy project processes.