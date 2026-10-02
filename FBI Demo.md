
## **Opening: Value Proposition** (1 min)

Ciprian Sabolovits - AI Innovation Lead at AFS

Today we are going show you an AI-powered background investigation system—built for speed and built to help analysts work smarter.
  
Before we jump into the demo, let me quickly give a bit of insights into the technical approach.

We're using an **agentic architecture**—AI agents that extract, correlate, analyze data and automatically build a **Graph knowledge base** that connects all the pieces together —subjects, claims, evidence, discrepancies

 And everything is build with **Open-source** technologies —no vendor lock-in, fully transparent and on-prem/in-boundary deployments. These are all technologies used right now in FBI supporting the mission such as the CTD program.

## **Let's get back to the demo**
- We are going to walk through Jerry's case. 
- In preparation for this demo, we've already processed his SF-86 and initial records checks.
- The system has already done the heavy lifting: extracted claims, pulled records from various data sources like FBI NCIC, credit bureaus, DHS, DMV, IRS
- Agentic Pipeline ran automatically—extraction, integration, correlation, scoring
- `Let's open this case and see what the analysis found.`

**Chat**
- `Now here's where we flip the script.`
- `Traditional systems dump data on analysts—you're drowning in PDF`
- `But what if instead of hunting through documents, **you just ask**?`

### Documents - 30 sec
- All source documents are here—SF-86, records check results
- These are mock adapters today, but they simulate real system integrations

### Dashboard - 3 minute

#### Risk Score

The risk scoring is a **deterministic multi-step calculation** that combines domain-specific scores with pattern analysis. 

Each derogatory item contributes base points (5-50) based on severity level, reduced by 40% if disclosed and 50% if mitigated, then summed per domain up to a 100-point cap. Domain scores are then weighted by importance (Criminal/Foreign/Travel at 1.0x down to Education at 0.4x), averaged together, and multiplied by a pattern multiplier (1.0-1.25x) that increases the final composite score if systematic concealment patterns are detected across multiple discrepancy types.

#### Facts

The **Facts panel** shows us verification status at a glance: 12 claims verified in green, 3 contradicted in red, 8 still unverified. The domain bars below show where the verification work is concentrated—Employment and Identity are mostly verified, but Foreign Travel still has gaps.

#### Task List
- We are seeing all the task that were executed such as extracting information through interfaces such as adapters from FBI NCIC, credit bureaus, DHS travel, DMV, IRS
- We are seeing ROI / Load tasks created by agents for identified references (friends, supervisors)

#### Derogatory Information
**Derogatory Information** surfaces the red flags—negative findings that could impact clearance. Jerry has 15 items here, tagged with ISC codes that map to adjudicative guidelines. Notice ISC-F appears 6 times.

1. **ISC Codes** - Industry Standard Codes that categorize the type of derogatory issue according to investigative guidelines (shown as badges like "ISC-4", "ISC-7", etc.)
2. Filtering built in
3. Quick information

#### Discrepancies
**Discrepancies** are inconsistencies or contradictions found between what the facts and what the evidence shows.

### Knowledge Graph - 2 min
- Let me show you what was built under the hood—this is the **knowledge graph**
- Every claim, every piece of evidence, every relationship
- Nodes: 
	- Purple nodes—**claims** Jerry made on his SF-86
	- Blue nodes—**evidence** from records checks and interviews
- Edges:
	- Green edges—where evidence **corroborates** a claim
	- Red dashed edges—where evidence **contradicts** what he said
- Node Details: click on a claim node and see details
- Filters
	- Filter by domain "Show me foreign travel"
	
---
#### Upload ROI 
Upload ROI for David


### Chat - 2 min
- `Now here's where we flip the script.`
- `Traditional systems dump data on analysts—you're drowning in PDF`
- `But what if instead of hunting through documents, **you just ask**?`

**Prompts**

```
What are the biggest red flags in this investigation?`
```

```
List all derogatory items
```

```
Draft follow-up interview questions
```

`Citations` - Analyst doesn't have to trust the AI, they verify

### Closing - 30 seconds

- AI background investigation system where AI doesn't just organize data—it empowers analysts to **ask questions** and get **cited, actionable answers** in seconds.

- And because it's built on open-source tech, you own it, you control it, and you can adapt it as your mission evolves.

- **That's the future we are envisioning!**
  
  


