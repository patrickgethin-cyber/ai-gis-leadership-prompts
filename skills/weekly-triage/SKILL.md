---
name: weekly-triage
description: "Analyzes weekly GIS request data to identify patterns, workload balance, automation opportunities, and strategic initiatives. Automatically invoked when user provides M&D request CSV data or discusses weekly GIS team workload analysis."
---

# Weekly GIS Request Triage & Intelligence

## Overview
This skill analyzes weekly M&D (Maintenance & Development) request data from Pilbara Ports Authority's GIS team to identify operational patterns, strategic opportunities, and improvement recommendations.

**Auto-invoke triggers:**
- User uploads CSV file with GIS request data
- User mentions "weekly triage", "M&D requests", or "GIS workload analysis"
- User asks to analyze request patterns or team capacity

## Context

### Team Structure
- **Patrick Gethin** - GIS Team Leader (should reduce execution work, focus on strategy)
- **Catherine Higgins** - Enterprise Systems & Data Management focus
- **Allan Blake** - Dampier regional analyst
- **Elaine Klava** - Port Hedland analyst (strong automation skills, collaborative approach)

### Ports Managed
Port Hedland, Dampier, Ashburton, Cape Preston West, Beadon Creek

### Strategic Goal
Shift team from 60% reactive work to 40% reactive work through automation, enterprise solutions, and strategic capability building.

### Technology Stack
- ArcGIS Desktop/Pro, ArcGIS Online, Portal
- FME Desktop & FME Flow
- Python scripting
- Drone Deploy for imagery
- Microsoft Lists (M&D request system)

## Expected Input

### CSV Structure
M&D Request List export with fields:
- ID, Request (title), Assigned to, Requested by
- Theme, Status, Priority
- Department, Location/Port, Map Number
- Date reported, Start_Date, Due Date, Completed Date
- Parent Project, Request System Used

### Context Questions to Ask User
If CSV alone isn't sufficient, ask:
- Week date range for this analysis?
- Any known strategic initiatives or projects this week?
- Specific concerns about workload or patterns?

## Analysis Framework

### 1. REQUEST PATTERN ANALYSIS
Identify and quantify:
- **Repeat requests** - Similar titles/themes done multiple times
- **Volume by theme** - Map Request, Enterprise Systems, Data Request, DA/CA, Tenure, etc.
- **Volume by location** - Which ports generate most work
- **Volume by department** - Which business units are heavy users
- **Priority distribution** - Critical/High/Medium/Normal breakdown

### 2. WORKLOAD DISTRIBUTION ANALYSIS
Assess team balance:
- Requests per person (current week)
- Theme alignment with roles
  - Catherine → Enterprise work
  - Allan → Regional Dampier work
  - Elaine → Port Hedland operational work
  - Patrick → Should be delegating, not executing
- Capacity signals (who's overloaded, who has capacity)
- Delegation opportunities for Patrick

### 3. OPPORTUNITY DETECTION

**Strategic Opportunities (Enterprise Solutions):**
- Simple map requests suggesting need for permanent enterprise dataset
- Multiple requests from same department suggesting self-service tool need
- Cross-port duplication suggesting standardization opportunity

**Automation Candidates (ROI Scoring):**
Score each repeat pattern using:
- Volume (1-5): How often it occurs
- Repeatability (1-5): How standardized the request is
- Effort (1-5): Time investment per request
- Complexity (1-5): Technical difficulty to automate

**ROI Score = (Volume × Repeatability × Effort) / Complexity**

Prioritization:
- ROI > 40: Quick Win (high priority)
- ROI 20-40: Strong Candidate (medium priority)
- ROI 10-20: Consider (lower priority)
- ROI < 10: Keep manual

### 4. BUSINESS VALUE TRANSLATION
Convert technical GIS work to executive-friendly language:

**Don't say:** "Created map", "Updated spatial layer"
**Do say:** "Enabled [department] to [business outcome]", "Prevented [risk]"

**Value categories:**
- Safety: Prevented incidents, reduced risk
- Compliance: Maintained regulatory standing, avoided penalties
- Revenue: Protected revenue stream, enabled opportunity
- Efficiency: Saved time/cost, accelerated process
- Risk: Identified exposure before consequence
- Strategic: Informed major decision with spatial intelligence

### 5. LEADERSHIP REFLECTION QUESTIONS
Generate 5-7 strategic questions across:

**Delegation & Capacity:**
- Which specific requests could team members have handled with light guidance?
- What's the 80/20 - could you create a template/example to save time?

**Pattern Recognition:**
- What systemic need are we solving piecemeal?
- If you were the department head, what GIS capability would you want proactively?

**Team Development:**
- How could automation wins become team learning moments vs. silos?
- Who's ready for a stretch assignment to grow leadership potential?

**Executive Positioning:**
- Which work has highest C-suite visibility and how do we highlight it?
- What's the business risk if this GIS work wasn't done?

**Personal Growth:**
- What would a Head of Digital Infrastructure see in these patterns?
- Are you operating at Team Leader or Senior Manager level?

## Output Format

Generate a comprehensive weekly digest with these sections:

### Executive Summary (2-3 sentences)
Total volume, key pattern, top strategic opportunity, one key action

### Request Landscape
- Volume distribution (by theme, location, priority)
- Status snapshot
- Notable changes from prior weeks if data available

### Repeat Work Patterns
- List requests done 3+ times
- Current approach and automation potential
- Interpretation of what patterns reveal

### Team Workload Analysis
- Distribution table (person, request count, themes, capacity signal)
- Observations on balance and role alignment
- Specific delegation opportunities for Patrick

### Strategic Opportunities Identified
**Enterprise Dataset Needs:**
- Trigger requests
- Current vs. proposed solution
- Business value and effort estimate

**Self-Service Tool Opportunities:**
- Department need and current friction
- Proposed solution
- Users served and effort estimate

**Standardization Wins:**
- Current duplication detected
- Standardization approach
- Cross-port value

### Top Automation Candidates
Table with: Rank, Request Type, ROI Score, Priority, Approach, Time Savings

Detail top 3 quick wins with:
- Current manual process
- Automation approach
- Implementation effort
- Success criteria
- Owner recommendation (consider Elaine's collaborative philosophy)

### Business Value Translation
- Week's work in executive language
- Key value delivered by business function
- Strategic contributions to highlight
- Executive communication snippets (pre-written phrases)

### Strategic Reflection Questions
5-7 questions across delegation, pattern recognition, team development, executive positioning, personal growth

### Recommended Actions
- Immediate (this week)
- Validate for monthly planning
- Team discussion topics

## Usage Notes

### When to Run
Every Monday morning with previous week's CSV export

### Output Delivery
- Generate markdown report
- User can save to Notion
- User can commit to GitHub
- Feeds into monthly strategic planning (WF-02)

### Iteration Approach
After first 4 weeks, ask user:
- Which sections most/least useful?
- Which reflection questions led to action?
- What template adjustments needed?

## Example Patterns to Watch For

**Automation Signals:**
- "Compress database, rebuild indexes" appearing weekly → Schedule automation
- "Port Hedland Biosecurity area map" monthly → Template opportunity
- "Upload Drone Mapping to Port Maps" after every capture → Workflow automation

**Strategic Signals:**
- Multiple lease/licence maps from different requesters → Standardized template need
- Repeated CAD file requests → Enterprise data conversion project
- Similar heritage/environmental maps → Spatial analysis framework opportunity

**Workload Signals:**
- Patrick handling routine map requests → Delegation needed
- Catherine doing operational tasks → Enterprise time being consumed
- One person with 15+ requests → Capacity issue or automation opportunity

## Success Metrics

Track over time:
- Reactive work percentage (target: 60% → 40%)
- Automation count increasing
- Repeat request volume decreasing
- Patrick's execution workload decreasing
- Team capacity hours freed up

---

**Skill Version:** 1.0  
**Last Updated:** January 2026  
**Owner:** Patrick Gethin, GIS Team Leader, Pilbara Ports Authority
