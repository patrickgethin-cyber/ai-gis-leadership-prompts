---
# LEVEL 1: METADATA (Always loaded - lightweight discovery)
name: weekly-triage
version: 2.0
category: workflow-analysis
subcategory: gis-operations
author: Patrick Gethin, GIS Team Leader
organization: Pilbara Ports Authority
created: 2026-01-15
updated: 2026-01-27
status: production

# Description for Claude's discovery system
description: >
  Analyzes weekly GIS request data to identify workload patterns, automation 
  opportunities, and strategic initiatives. Transforms M&D request data into 
  executive-ready insights with ROI-scored recommendations.

# Trigger patterns - when Claude should load this skill
trigger_patterns:
  - "weekly triage"
  - "M&D requests"
  - "GIS workload"
  - "analyze requests"
  - "team capacity"
  - "automation opportunities"
  - "workload distribution"
  - "request patterns"

# When Claude should auto-invoke this skill
auto_invoke_conditions:
  - user uploads CSV with request data columns
  - user mentions analyzing weekly GIS team workload
  - user provides M&D request export
  - user asks about team capacity or patterns

# Tags for categorization
tags: 
  - gis
  - workload-analysis
  - automation-scoring
  - team-management
  - strategic-planning
  - pilbara-ports

# Prerequisites
prerequisites:
  required:
    - M&D request CSV data (last 7-30 days)
  optional:
    - Previous week's analysis for comparison
    - Current strategic initiatives context
    
# Expected outputs
outputs:
  - Comprehensive weekly digest report (markdown)
  - ROI-scored automation recommendations
  - Executive summary with business value language
  - Strategic reflection questions for leadership
  - Actionable next steps

# Success metrics
success_criteria:
  - All team members analyzed for capacity
  - At least 2 patterns identified if data sufficient
  - Top 3 automation opportunities ranked with ROI
  - Business value articulated in executive language
  - Analysis completes in <10 minutes review time

---

# LEVEL 2: INSTRUCTIONS (Loaded when skill is triggered)

# Weekly GIS Request Triage & Intelligence Skill

## Overview

This skill transforms raw M&D (Maintenance & Development) request data into 
strategic intelligence for GIS team leadership at Pilbara Ports Authority.

**Purpose:** Enable data-driven decision making on automation priorities, 
workload balance, and strategic positioning by systematically analyzing 
weekly request patterns.

**Business Value:** Supports the team's transformation from 60% reactive 
work to 40% through identification of high-ROI automation candidates and 
strategic enterprise solution opportunities.

---

## Context

### Team Structure & Roles

**Patrick Gethin** - GIS Team Leader
- Strategic focus: Should delegate execution, focus on leadership
- Watch for: Execution work that could be delegated

**Catherine Higgins** - Enterprise Systems Specialist  
- Focus area: Enterprise data management, system architecture
- Watch for: Operational tasks consuming enterprise strategy time

**Allan Blake** - Regional Dampier Analyst
- Focus area: Dampier port operational support
- Watch for: Regional specialization opportunities

**Elaine Klava** - Port Hedland Analyst
- Strength: Automation skills, collaborative approach
- Watch for: Automation leadership opportunities

### Organizational Context

**Ports Managed:** Port Hedland, Dampier, Ashburton, Cape Preston West, Beadon Creek

**Strategic Mission:** Transform from reactive service provider to strategic 
business partner with executive influence

**Current State:** 60% reactive work  
**Target State:** 40% reactive work  
**Approach:** Automation, enterprise solutions, strategic capability building

**Technology Stack:**
- ArcGIS Desktop/Pro, ArcGIS Online, Portal
- FME Desktop & FME Flow
- Python scripting
- Drone Deploy for imagery
- Microsoft Lists (M&D request tracking system)

---

## Input Expectations

### Required CSV Structure

M&D Request List export must include:

**Core Fields:**
- ID, Request (title), Assigned to, Requested by
- Theme, Status, Priority
- Department, Location/Port
- Date reported, Due Date, Completed Date

**Optional Fields:**
- Map Number, Parent Project, Request System Used
- Start_Date, Hours Spent

**Data Quality Requirements:**
- Minimum 10 requests for pattern detection
- Date range: Last 7-30 days preferred
- All team member names consistently spelled

### Clarifying Questions

If CSV data alone insufficient, ask user:

1. "What week date range does this data cover?"
2. "Are there any known strategic initiatives or projects this week I should consider?"
3. "Any specific concerns about workload distribution or patterns to investigate?"
4. "Do you have previous week's data for trend comparison?"

---

## Analysis Framework

### STEP 1: Request Pattern Analysis

**Identify and quantify:**

**A) Repeat Request Detection**
- Flag requests with similar titles (≥70% title match)
- Group by theme/type for frequency counting
- Threshold: Appears 3+ times = significant pattern

**B) Volume Distribution**
- By theme: Map Request, Enterprise Systems, Data Request, DA/CA, Tenure, etc.
- By location: Which ports generate most work
- By department: Which business units are heavy users
- By priority: Critical/High/Medium/Normal breakdown

**C) Pattern Significance**
- High-value patterns: High volume + High repeatability
- Strategic patterns: Simple requests suggesting enterprise need
- Efficiency patterns: Time-consuming manual work appearing repeatedly

### STEP 2: Workload Distribution Analysis

**Capacity Assessment per Team Member:**

```
For each team member, calculate:
- Request count (current week)
- Theme alignment with role
- Complexity distribution (simple/medium/complex)
- Capacity signal: balanced | heavy | overloaded
```

**Role Alignment Check:**
- Catherine → Enterprise systems work (should not be doing basic maps)
- Allan → Dampier regional work (specialization appropriate?)
- Elaine → Port Hedland operational (automation opportunity?)
- Patrick → Strategy focus (any execution work to delegate?)

**Delegation Opportunity Detection:**
- Patrick handling requests below Team Leader level?
- Work that could be distributed for team development?
- Opportunities for cross-training or skill building?

### STEP 3: Automation Opportunity Scoring

**ROI Calculation Formula:**

```
For each repeat pattern:

Volume Score (1-5):
  5 = Daily (20+/month)
  4 = Weekly (8-19/month)  
  3 = Bi-weekly (4-7/month)
  2 = Monthly (2-3/month)
  1 = Occasional (<2/month)

Repeatability Score (1-5):
  5 = Completely standardized process
  4 = Mostly standard with minor variations
  3 = Standard with some customization
  2 = Requires moderate judgment
  1 = Highly customized each time

Effort Score (1-5):
  5 = 4+ hours per request
  4 = 2-4 hours per request
  3 = 1-2 hours per request
  2 = 30min-1 hour per request
  1 = <30 minutes per request

Complexity Score (1-5):
  5 = Requires expert GIS analyst judgment
  4 = Complex multi-step GIS workflow
  3 = Intermediate GIS task
  2 = Simple GIS operation
  1 = Could be self-service with training

ROI Score = (Volume × Repeatability × Effort) / Complexity

Prioritization:
  ROI > 40  = QUICK WIN (urgent priority)
  ROI 20-40 = STRONG CANDIDATE (high priority)
  ROI 10-20 = CONSIDER (medium priority)  
  ROI < 10  = KEEP MANUAL (low priority)
```

### STEP 4: Strategic Opportunity Detection

**Enterprise Dataset Needs:**

Detect when simple map requests suggest permanent enterprise layer:

```
Trigger: Same map/data requested by multiple departments
Signal: "Can you add [feature] to the map?" appearing repeatedly
Opportunity: Create enterprise dataset with self-service access
Value: Eliminate repetitive work, empower departments
```

**Self-Service Tool Opportunities:**

Detect when departmental friction suggests tool need:

```
Trigger: Same department requesting similar outputs repeatedly
Signal: "Can I get updated [standard report]?" pattern
Opportunity: Self-service reporting tool or automated delivery
Value: Reduce interruptions, enable 24/7 access
```

**Standardization Wins:**

Detect cross-port duplication:

```
Trigger: Similar work done separately for each port
Signal: Port-specific variations of same request
Opportunity: Standard template applicable to all ports
Value: Consistency, efficiency, scalability
```

### STEP 5: Business Value Translation

**Convert technical GIS work to executive language:**

**Avoid saying:**
- "Created map"
- "Updated spatial layer"  
- "Processed data"
- "Ran analysis"

**Instead articulate:**
- "Enabled [department] to [business outcome]"
- "Prevented [risk] before [consequence]"
- "Protected [revenue/asset] by identifying [issue]"
- "Accelerated [decision] with spatial intelligence"

**Value Categories to Apply:**

- **Safety:** Prevented incidents, reduced risk, ensured safe operations
- **Compliance:** Maintained regulatory standing, avoided penalties
- **Revenue:** Protected revenue stream, enabled commercial opportunity
- **Efficiency:** Saved time/cost, accelerated critical process
- **Risk:** Identified exposure before consequence materialized
- **Strategic:** Informed major decision with spatial intelligence

### STEP 6: Leadership Reflection Questions

**Generate 5-7 strategic questions across these themes:**

**Delegation & Capacity:**
- "Which specific requests could team members have handled with light guidance?"
- "What's the 80/20 - could you create a template/example once to save repeated effort?"
- "Are you operating at Team Leader level or still in Senior Analyst mode?"

**Pattern Recognition:**
- "What systemic business need are we solving piecemeal?"
- "If you were the department head, what GIS capability would you want proactively?"
- "What's the business risk if this GIS work wasn't done?"

**Team Development:**
- "How could automation wins become team learning moments vs. individual silos?"
- "Who's ready for a stretch assignment to grow their leadership potential?"
- "What cross-training would improve team resilience and capacity?"

**Executive Positioning:**
- "Which work has highest C-suite visibility and how do we highlight it?"
- "What would a Head of Digital Infrastructure see in these patterns?"
- "How does this week's work demonstrate strategic business partnership vs. technical service?"

**Personal Growth:**
- "Are you focusing on what only you can do as Team Leader?"
- "What leadership capability are you building this week?"

---

## Output Format

### Complete Weekly Digest Structure

**Generate markdown report with these sections:**

#### 1. Executive Summary
2-3 sentences covering:
- Total volume and key pattern
- Top strategic opportunity with business value
- One key action with expected impact

Example:
```
"Analyzed 43 requests this week. Identified 4 standard export requests 
consuming 8hrs/week - strong automation candidate (ROI: 9/10). 
Recommend: Build self-service export portal to save 32hrs/month and 
reduce team interruptions."
```

#### 2. Request Landscape
- Volume distribution by theme, location, priority
- Status snapshot (completed/in-progress/pending)
- Week-over-week changes if historical data available

#### 3. Repeat Work Patterns
For each significant pattern (3+ occurrences):
- Pattern description
- Frequency and requestors
- Current manual approach
- Automation potential assessment
- Interpretation: What does this pattern reveal about business needs?

#### 4. Team Workload Analysis

**Distribution Table:**
```
| Team Member | Requests | Themes | Capacity Signal | Notes |
|-------------|----------|--------|----------------|-------|
| Patrick     | N        | [list] | balanced/heavy | [observations] |
| Catherine   | N        | [list] | balanced/heavy | [observations] |
| Allan       | N        | [list] | balanced/heavy | [observations] |
| Elaine      | N        | [list] | balanced/heavy | [observations] |
```

**Observations:**
- Balance assessment across team
- Role alignment evaluation
- Specific delegation opportunities for Patrick
- Cross-training or development suggestions

#### 5. Strategic Opportunities Identified

**Enterprise Dataset Needs:**
For each opportunity:
- Trigger requests (what's being asked repeatedly)
- Current approach vs. proposed solution
- Business departments served
- Estimated effort and value

**Self-Service Tool Opportunities:**
For each opportunity:
- Department need and current friction
- Proposed self-service solution
- Users served and usage estimate
- Implementation effort and approach

**Standardization Wins:**
For each opportunity:
- Current duplication detected across ports
- Standardization approach (template/process/dataset)
- Cross-port value and efficiency gain

#### 6. Top Automation Candidates

**Summary Table:**
```
| Rank | Request Type | ROI Score | Priority | Time Savings |
|------|--------------|-----------|----------|--------------|
| 1    | [type]       | XX        | Quick Win | Xhrs/week   |
| 2    | [type]       | XX        | Strong    | Xhrs/week   |
| 3    | [type]       | XX        | Strong    | Xhrs/week   |
```

**Detail Top 3 Quick Wins:**

For each:
- Current manual process description
- Automation approach (FME/Python/self-service tool)
- Implementation effort estimate (hours/weeks)
- Success criteria (how to measure if working)
- Owner recommendation (consider Elaine's automation skills and collaborative approach)
- Business value articulation

#### 7. Business Value Translation

- Week's work in executive-friendly language
- Key value delivered by business function (Safety/Compliance/Revenue/etc.)
- Strategic contributions to highlight in leadership discussions
- Pre-written executive communication snippets (ready to copy into emails/briefings)

#### 8. Strategic Reflection Questions

5-7 questions across:
- Delegation & capacity optimization
- Pattern recognition & proactive thinking
- Team development & capability building
- Executive positioning & strategic influence
- Personal leadership growth

#### 9. Recommended Actions

**Immediate (this week):**
- Quick wins requiring <1 day effort
- Urgent capacity rebalancing needs

**Validate for monthly planning:**
- Medium-term automation projects (2-8 weeks)
- Strategic enterprise solution opportunities

**Team discussion topics:**
- Process improvement ideas
- Cross-training or development needs
- Strategic positioning discussions

---

## Usage Guidelines

### When to Execute

**Frequency:** Every Monday morning

**Data Source:** Previous week's M&D request CSV export (typically Friday close)

**Preparation:**
1. Export M&D List from Microsoft Lists
2. Ensure date range covers full week
3. Have previous week's analysis handy for comparison (optional but valuable)

### Output Delivery Options

User can:
- Save markdown report to Notion workspace
- Commit report to GitHub (`/outputs/weekly-triage/`)
- Use insights for Monday team standup talking points
- Feed patterns into monthly strategic planning sessions

### Iterative Improvement

After first 4 weeks of use, ask user:

- "Which sections are most/least useful for decision-making?"
- "Which reflection questions have led to actual changes?"
- "What template adjustments would make this more actionable?"
- "Are time estimates accurate? Should scoring weights adjust?"

---

## Quality Gates

**Before generating output, verify:**

- [ ] All team members have workload analysis
- [ ] At least 2 patterns identified (if sufficient data volume)
- [ ] Top 3 automation opportunities ranked with ROI scores
- [ ] All ROI scores use consistent formula
- [ ] Business value articulated (not just technical descriptions)
- [ ] Strategic reflection questions span all 5 themes
- [ ] Recommended actions are specific and time-bound

**If quality criteria not met:**
- Flag insufficient data or request clarification
- Note which sections cannot be completed with available data
- Suggest minimum data requirements for complete analysis

---

## Example Patterns Library

**Common Automation Signals:**

- "Compress database, rebuild indexes" weekly → Schedule automation
- "Port Hedland Biosecurity area map" monthly → Template + self-service
- "Upload Drone Mapping to Port Maps" after every capture → Workflow automation
- "Export parcel shapefile" 4×/week → Self-service export portal

**Common Strategic Signals:**

- Multiple lease/licence maps from different requesters → Standardized template need
- Repeated CAD file requests from Planning → Enterprise data conversion project  
- Similar heritage/environmental maps → Spatial analysis framework opportunity
- Cross-port duplication of infrastructure maps → Standardization win

**Common Capacity Signals:**

- Patrick doing execution work → Delegation needed for leadership focus
- Catherine doing operational tasks → Enterprise strategy time being consumed
- One person with 15+ requests → Capacity issue or automation opportunity
- Uneven distribution → Potential for workload rebalancing

---

## Success Metrics (Track Over Time)

**Primary Metrics:**
- Reactive work percentage: 60% → 40% (target)
- Automation count: Increasing
- Repeat request volume: Decreasing

**Team Metrics:**
- Patrick's execution workload: Decreasing
- Team capacity hours freed: Increasing
- Cross-training instances: Increasing

**Business Metrics:**
- Executive visibility of GIS value: Increasing
- Strategic project involvement: Increasing
- Self-service adoption: Increasing (when tools built)

---

## Skill Metadata

**Version:** 2.0  
**Status:** Production  
**Last Updated:** January 27, 2026  
**Owner:** Patrick Gethin, GIS Team Leader, Pilbara Ports Authority  
**Related Skills:** spatial-analysis, executive-briefing, da-compliance-check  
**Related Workflows:** weekly-triage-agentic.md  
**GitHub:** ai-gis-leadership-prompts/skills/weekly-triage/

---

# LEVEL 3: RESOURCES (Loaded as needed)

Resources for this skill are stored in subdirectories:

- `examples/` - Sample inputs and outputs
- `templates/` - Reusable report templates  
- `resources/` - Supporting materials and references

See README.md in this folder for resource catalog.