

## Introduction

Innovation Lead at AFS:
	* seeded into the latest technical advancement and work closely helping Federal Agencies tackle and solve some of their most complex challenges by tapping into the power of AI
	* build and manage AFS repository of AI assets & accelerators. DeepSee which we are going to demo today is such an asset AFS has built in house to help with data extraction from documents


## Create a DEA Knowledge Base

App Name
```
DEA Procedures
```

Descritption
```
Get all the help and support you need when having questions about DEA (Drug Enforcement Administration) procedures and drug testing policies.
```


```
You are an expert in DEA (Drug Enforcement Administration) policies and procedures. Your job is to provide clear responses to all user questions in regards to DEA policy and procedures to the best of your abilities.
```


## Create a tailored FedGenius App

GOALS: 
- Provide the most value and insights into the provided data set
- Provide a flexible user experience  that allows the user to quickly access data and identify next steps


### Data Tab
- Displays the data set provided information after clean-up and data augmentation
- Already supports some basic insights based on raw data via filters and grouping

### Analytics Dashboard
Traditional analytics empowered by FedGenius platform. This dashboard is able to display:
- summary information
- trends
- aggregations
- focused analysis





## Drug Type Distribution Explained
**Drug Type Distribution** shows the breakdown of all drug seizures by narcotic type, presented in two complementary visualizations to help investigators understand the drug landscape in their operational area.

**The Two Views**
 1. **Pie Chart** - Drug Type Distribution
 2. **Bar Chart** - Seizures by Drug Type

### Investigative Questions This Answers

✓ "What drugs are most prevalent in our jurisdiction?" 
✓ "Has the drug landscape changed over time?" 
✓ "Which drug should we prioritize for enforcement?" 
✓ "Are we seeing emerging drug threats?" 
✓ "Do we need to adjust our enforcement strategy?"


#### Drug Purity Analysis Explained
**Drug Purity Analysis** shows the average purity percentage of seized drugs, helping investigators understand drug quality and supply chain patterns.

### Investigative Use
**High purity (>75%)** - Priority investigation targets:
- Likely connected to high-level suppliers
- Direct import/manufacturing operations
- Professional distribution networks

**Low purity (<50%)** - Different investigation approach:
- Street-level distribution
- Multiple intermediaries
- Local cutting operations

**Comparing seizures**: Similar purity levels between different cases may indicate they're part of the same distribution network.




#### Top Suspects Analysis
Color Code by Schedule



## Criminal Network Analysis

Crypto Tracing - similar graph based analysis

1. **Start with Type Filtering**: Select only "suspect" nodes to see the core criminal network
2. **Use Centrality Threshold**: Slide it up to 0.1-0.2 to focus on key brokers
3. **Explore with Ego Network**: Click a suspect, enable Ego Network, adjust depth to 2 to see their immediate network
4. **Community Analysis**: Filter by specific communities to analyze sub-groups
5. **Strong Connections Only**: Increase edge weight threshold to 3+ to see only frequent interactions


### Key Players Explained

**Key Players** are the most influential individuals in the criminal network based on their position and connections. Think of them as the "power brokers" or "critical nodes" in the organization.

#### What the Score Means

The **composite score** (0-1 scale) measures how central and important each person is to the network's operation. It combines three factors:

1. **Betweenness (40% of score)** - How often this person acts as a bridge between others
    - High score = They connect different parts of the network
    - They're often intermediaries or brokers in the organization
    - Removing them would fragment the network
2. **Degree (30% of score)** - How many direct connections they have
    - High score = They know/interact with many people
    - They're well-connected hubs in the network
3. **PageRank (30% of score)** - How important their connections are
    - High score = They're connected to other important people
    - Quality of connections, not just quantity

Key players are priority targets for:

- **Surveillance** - Monitoring them reveals network activities
- **Interviews** - They have knowledge of multiple network members
- **Disruption** - Removing them fragments the organization
- **Evidence collection** - Their communications likely contain valuable intelligence

#### Example
**Stephanie Lee (Score: 0.070)** is the #1 key player because:
- She's likely a crucial intermediary connecting different groups
- She has many direct contacts in the network
- She's connected to other important players
- **Disrupting her activity would significantly impact the network's operations**


#### Chat:

- which cases Rachel Turner is showing up on?
- are there license plates associated with Rachel Turner?

which cases is license plate KLM-8473 associated with
show me more details on case 2024-CR-1576







- 