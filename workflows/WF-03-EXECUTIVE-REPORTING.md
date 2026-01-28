# WF-03: Executive Reporting

**Workflow ID:** WF-03-EXECUTIVE-REPORTING  
**Version:** 1.0  
**Status:** Planned (Q2 2026)  
**Cadence:** Quarterly  
**Owner:** Pat Gethin  
**Last Updated:** 2026-01-28

---

## Purpose

Creates concise executive reports from strategic plan progress. Translates operational reality into business value language for leadership.

**Business Value:**
- Executive visibility into GIS strategic progress
- ROI justification for automation investments
- Demonstrates shift from reactive to strategic work
- Supports resource requests and budget planning
- Time saved: 4 hrs/quarter (~16 hrs/year)

---

## How It Works

**Simple:** Read current strategic plan → Extract key updates → Format for executives

**Input:** Strategic Plan (from WF-02) + 3 months of WF-01 summaries  
**Output:** 2-3 page executive summary

---

## When to Run

**Quarterly:** End of Q1, Q2, Q3, Q4 (after 3 months of WF-02 updates)

**Or:** Before major leadership meetings, budget reviews, or strategic planning sessions

---

## Inputs Required

**From Google Drive:**
```
Required:
- Current Strategic Plan 
  Location: Strategic Planning/Strategic Plan (Master Document)

- Three monthly update summaries
  Location: Strategic Planning/Monthly Updates/
  Files: Month 1, Month 2, Month 3 summaries
```

**From You (Optional):**
- Specific topics leadership cares about
- Recent wins to highlight
- Budget requests to support
- Upcoming priorities to preview

---

## Process

**In Claude:**

```
Prompt:
"Run WF-03 Executive Reporting for Q[X] 2026.

Strategic Plan: [link or key sections]
Monthly updates: [paste 3 summaries]

Focus areas:
- [Any specific leadership priorities]
- [Budget requests]
- [Wins to highlight]

Generate executive report covering:
1. Progress on 60% → 40% reactive work goal
2. Quarterly highlights and wins
3. Automation ROI (time/cost saved)
4. Key initiatives status
5. Risks and mitigation
6. Next quarter priorities
"
```

---

## Output Structure

### Executive Summary (1 page max)

**Quarter at a Glance:**
- Reactive work progress: [X%] → [Y%] (target: 40%)
- Time saved through automation: [X] hrs/week
- Major milestones achieved: [2-3 bullets]
- Strategic initiatives on track: [X/Y]

### Progress Highlights (1 page)

**What We Delivered:**
- Platform: [e.g., VertiGIS completed, ArcGIS upgraded]
- Automation: [e.g., Marine FME live, saving 8 hrs/week]
- Data Quality: [e.g., 10 datasets rationalized]
- Capabilities: [e.g., Underground services flagship launched]

**Business Impact:**
- Safety improvements
- Efficiency gains
- Risk reductions
- Decision quality enhancements

### Looking Ahead (0.5 page)

**Next Quarter Focus:**
- Top 3 priorities
- Expected outcomes
- Resource needs
- Dependencies

**Risks to Watch:**
- [1-2 key risks with mitigation]

---

## Success Criteria

- ✅ Report completed in <2 hours
- ✅ Fits on 2-3 pages (executive-friendly)
- ✅ Demonstrates measurable progress
- ✅ Business value clearly articulated
- ✅ Supports decision-making (budget, resources, priorities)

---

## Output Location

**Google Drive:**
```
GIS Team - AI Operations/Executive Reporting/Quarterly Reports/
Filename: Q[X] 2026 Executive Report
Format: Google Doc (can export as PDF)
```

**Also saved to GitHub:** `reports/Q[X]-2026-executive-report.md`

---

## Integration Points

**Consumes:**
- WF-02-STRATEGIC-PLANNING (strategic plan + monthly updates)
- WF-01-WEEKLY-TRIAGE (operational metrics)

**Feeds:**
- Executive leadership meetings
- Budget planning
- Strategic reviews
- Stakeholder communications

---

## Example Output Snippet

```markdown
# Q1 2026 Executive Report: GIS Team Strategic Progress

## Quarter at a Glance
- **Reactive Work:** 60% → 55% (on track for 40% by year-end)
- **Time Saved:** 13 hrs/week through automation (up from 3)
- **Major Win:** VertiGIS transition completed ahead of schedule
- **Initiatives:** 9/12 on track, 2 ahead of schedule, 1 delayed

## Key Achievements

**Platform Modernization**
✅ VertiGIS transition completed Q2 (1 month early)
- Zero downtime during transition
- All PortMaps users migrated successfully
- Foundation for future 3D capabilities

**Automation ROI**
✅ Marine bathymetry FME automation deployed
- Saves 8 hrs/week (was manual processing)
- Improves AHO chart update timeliness by 50%
- Reduces navigation safety compliance risk

**Data Quality**
✅ Underground services data collection accelerated
- 90% of known services now digitized (up from 80%)
- Field capture tools adopted by operations teams
- Direct safety impact: Supports utility strike prevention

## Business Value Delivered
- **Safety:** Underground services visibility reduces utility strike risk
- **Efficiency:** 13 hrs/week freed for strategic work (675 hrs/year)
- **Compliance:** Improved AHO chart update responsiveness
- **Risk Reduction:** Platform on supported version

## Next Quarter Priorities
1. Complete ArcGIS Enterprise upgrade to v11.5
2. Launch request routing automation (target: 5 hrs/week saved)
3. Deliver first data quality monitoring automation

## Resource Request
- ICT support for ArcGIS upgrade (2 weeks)
- Budget for data quality automation tools ($X)
```

---

## Tips

**Keep it executive-friendly:**
- Lead with outcomes, not activities
- Quantify impact (time, cost, risk)
- Use business language, not tech jargon
- Visuals help (charts, metrics dashboards)
- 2-3 pages max

**Highlight the right things:**
- Progress toward strategic goals
- ROI and efficiency gains
- Risk mitigation
- Alignment with org priorities
- Team capability growth

**Don't:**
- List every task completed
- Use technical terminology
- Bury the lead
- Make excuses for delays
- Forget to ask for what you need

---

## Related Assets

**Uses:**
- gis-strategic-plan-v1 (primary source)
- business-value-library (framing)
- WF-02 monthly summaries

**Related Workflows:**
- WF-02-STRATEGIC-PLANNING (provides content)
- WF-01-WEEKLY-TRIAGE (provides metrics)

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-28 | Initial workflow documentation |

**Next Review:** Q2 2026 (first execution)
