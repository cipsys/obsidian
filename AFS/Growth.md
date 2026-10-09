---
aliases:
---

## 2027

### Navy Intel Prototype Effort
Help them with a surge to create a prod ready prototype ~200k dollars
Consolidated use cases
Focusing on water down agentic AI
#### One mission Specific Use-case

Commercial ship vessel data tracking and answer question such as what 

#### One Enterprise Use-case

Extract Agent Canvas
### 10/26- DCSA CSO Prototype  
Designed and built, end to end and in about two days, a working prototype of an AI-assisted DCSA security-clearance applicant portal to support AFS growth with DCSA. Applicants sign in through OIDC (Keycloak or Cognito) and fill out the SF-86. The form is checked by standard rules and by AI that catches meaning-level gaps, such as a school in DC with no matching DC residence, and an AI agent can pre-fill it from uploaded documents. After submission, an autonomous Security Officer agent (Google ADK) reviews the full form and decides on its own whether to send it back to the applicant with a request for information. The prototype also covers foreign-travel reporting (pre-travel notifications and post-travel debriefs) and a case assistant chat that answers questions about the applicant's case and travel through a self-hosted MCP tool server. Stack: React/TypeScript, Python/FastAPI, LLMs on AWS Bedrock, packaged as a single Docker image with EKS deployment manifests. The result is a realistic demo that shows how GenAI can cut applicant errors and back-and-forth during clearance processing, and it reuses patterns from the TSA prototype and the mygpt platform.

### 09/26 - TSA Prototype  
Designed and built, end to end, a working prototype of a TSA checkpoint wait-time and bottleneck dashboard. It runs on real TSA operational data from three airports covering June to September 2026 and was built in about a week. I modeled six raw TSA data files as a medallion (bronze/silver/gold) warehouse that runs both locally (DuckDB) and in the cloud (Databricks Unity Catalog). Users drill down from airport to checkpoint to flow to lane and see wait times, throughput, PreCheck split, demand mix, staffing against demand, and a surge-risk forecast. I used analysis of the data to set the story of the demo. Averages hide the problem: one airport's checkpoint is 99.7% within the 30-minute goal yet had 33 surge episodes. Surges come from capacity shortfalls rather than crowds: 88% of surge hours were at least one lane short. So the dashboard leads with surge risk instead of averages. An "Ask Ops" AI chat answers operational questions about the selected airport through a self-hosted MCP tool server, using the same data layer as the dashboard. Stack: React/TypeScript, Python/FastAPI, OIDC login, packaged as a single Docker image deployed to Kubernetes. This established the reusable architecture (data layer, MCP chat, single-image deployment) that the DCSA prototype built on.


