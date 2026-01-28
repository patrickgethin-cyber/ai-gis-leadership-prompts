# WF-02: Strategic Planning

**Workflow ID:** WF-02-STRATEGIC-PLANNING  
**Version:** 1.0  
**Status:** Active  
**Cadence:** Monthly (First Monday)  
**Owner:** Pat Gethin  
**Last Updated:** 2026-01-28

---

## Purpose

Creates and maintains the GIS Team Strategic/Business Plan as a living document informed by operational data from WF-01-WEEKLY-TRIAGE. Transforms static planning into a dynamic strategic asset that evolves with reality.

**Business Value:**
- Strategy stays connected to operational reality  
- Data-driven basis for resource requests
- Demonstrates automation ROI to leadership
- Tracks progress toward 60% → 40% reactive work goal
- Time saved: 2 hrs/week (~100 hrs/year)

---

## Dual-Mode Operation

### 🔵 Mode 1: Initial Creation (Run Once)
Create comprehensive strategic plan v1.0 from existing planning materials

### 🔄 Mode 2: Monthly Updates (Recurring)
Update living strategic plan with operational insights and progress tracking

---

## Mode 1: Initial Creation

### Inputs
- Planning presentations (PPT/Slides)
- Planning notes (Excel/Sheets/Docs)
- Team context (structure, goals, constraints)
- Current initiatives and recent wins

### Process
1. Gather all planning materials
2. Provide context to Claude (team, goals, initiatives)
3. Generate comprehensive 12-section strategic plan
4. Review and refine with team input
5. Publish to Google Drive and GitHub
6. Update Notion registry

### Output
- **Strategic Plan v1.0** (~40-50 pages)
- Location: `Google Drive/Strategic Planning/Strategic Plan (Master Document)`
- Also saved to GitHub as markdown
- Notion registry updated with links

### Time to Complete
~2 hours (one-time investment)

---

## Mode 2: Monthly Updates

### Trigger
**First Monday of each month** (after 4 WF-01 reports complete)

### Inputs Required
```
From Google Drive:
- Current Strategic Plan (Master Document)
- 4 x WF-01 Weekly Triage Reports from previous month
  Location: Weekly Operations/YYYY/Month/

From You:
- Completed milestones or initiatives
- New priorities from leadership  
- Capacity or resource changes
- Significant wins or challenges
```

### Process
1. Collect WF-01 reports and note any major changes
2. Run monthly update with Claude:
   - Reviews current plan
   - Analyzes month's WF-01 insights
   - Updates relevant sections (progress, metrics, timeline)
   - Generates "What Changed This Month" summary
   - Increments version number
3. Review changes and validate accuracy
4. Publish updated plan to Google Drive and GitHub
5. Save monthly update summary
6. Update Notion "Last Run" date

### Sections Typically Updated
- **Always:** Current State, Initiative status, Timeline, Metrics
- **If changed:** Team structure, Automation roadmap, Resources, Risks
- **Rarely:** Vision/Mission, Value Prop, Strategic Framework

### Output
- **Strategic Plan v1.x** (incremented version)
- **Monthly Update Summary** (concise change log)
- Location: `Strategic Planning/Monthly Updates/YYYY-MM Strategic Update`
- Feeds WF-03-EXECUTIVE-REPORTING

### Time to Complete
~45 minutes (monthly maintenance)

---

## Strategic Plan Structure

The plan follows this standardized 12-section structure:

1. **Executive Summary** - Key goals and approach
2. **Vision & Mission** - Geospatial vision and guiding principles  
3. **Value Proposition** - Value by stakeholder type
4. **Current State Assessment** - Team, capacity, workload, constraints
5. **Strategic Framework** - Three organizing themes
6. **Strategic Initiatives** - 12+ detailed initiatives with owners/timelines
7. **Automation Roadmap** - Current and planned automation, ROI
8. **Timeline & Priorities** - Quarterly breakdown (Q1-Q4)
9. **Success Metrics & KPIs** - Measurable outcomes
10. **Resource Requirements** - Team capacity, budget, dependencies
11. **Risks & Mitigation** - Critical and medium risks
12. **Governance** - Maintenance cadence, decision-making

---

## Integration Points

### Google Drive
```
Inputs:
- Strategic Planning/Source Materials/ (initial creation)
- Strategic Planning/Strategic Plan (Master Document) (monthly updates)
- Weekly Operations/YYYY/Month/ (WF-01 reports)

Outputs:
- Strategic Planning/Strategic Plan (Master Document)
- Strategic Planning/Monthly Updates/YYYY-MM Strategic Update
```

### GitHub
```
This file: /workflows/WF-02-STRATEGIC-PLANNING.md
Strategic Plan: /strategic-plan-v[X.Y].md (versioned)

Versioning:
- v1.0, v1.1, v1.2 (monthly increments)
- v2.0 (major strategic refresh)
```

### Notion
```
Database: Workflows
Entry: WF-02-STRATEGIC-PLANNING
Links to: GitHub (this workflow), Google Drive (strategic plan)
Properties: Status, Cadence, Last Run, Business Impact, Time Saved
```

---

## Related Assets

### Uses
- **weekly-triage-skill** - Pattern recognition from WF-01
- **business-value-library** - ROI framing
- **roi-scoring-guide** - Prioritization methodology

### Feeds
- **WF-03-EXECUTIVE-REPORTING** - Quarterly exec reports

### Informed By
- **WF-01-WEEKLY-TRIAGE** - Monthly operational insights

---

## Success Metrics

### Initial Creation
- ✅ Time to create: <2 hours
- ✅ All 12 sections completed
- ✅ Initiatives have owners and timelines
- ✅ Saved to GitHub, Google Drive, Notion

### Monthly Updates
- ✅ Time to update: <45 minutes
- ✅ Reflects WF-01 operational reality
- ✅ Metrics and timelines current
- ✅ Change summary generated

### Overall
- 📊 Demonstrates progress toward 60% → 40% goal
- 💰 Provides ROI justification for automation
- 👔 Improves executive visibility
- 🎯 Informs actual decision-making (not shelfware)

---

## Quick Start

### First Time (Mode 1)
```bash
1. Gather planning materials
2. Open Claude (claude.ai or Cursor)
3. Prompt: "Run WF-02 Initial Creation mode..."
4. Provide materials and context
5. Review generated plan
6. Save to Google Drive and GitHub
7. Update Notion
```

### Monthly (Mode 2)
```bash
1. First Monday arrives
2. Collect 4 WF-01 reports
3. Open Claude
4. Prompt: "Run WF-02 Monthly Update for [Month]..."
5. Provide reports and any updates
6. Review changes
7. Publish and update systems
```

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-28 | Initial workflow documentation with dual-mode operation |

**Next Review:** 2026-02-03 (monthly cycle)
