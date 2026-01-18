---
name: WF-01-WEEKLY-TRIAGE
description: "Weekly analysis of GIS request patterns to identify workload balance, strategic opportunities, and automation candidates, supporting the shift from 60% reactive to 40% reactive work"
cadence: Weekly (Every Monday)
owner: Patrick Gethin, GIS Team Leader
skills_used:
  - SK-ANALYZE-WEEKLY-REQUESTS
  - SK-IDENTIFY-IMPROVEMENT-OPPORTUNITIES
  - SK-GENERATE-WEEKLY-DIGEST
  - SK-REFLECT-AND-TRANSLATE
feeds_into:
  - WF-02-STRATEGIC-PLANNING (monthly)
  - WF-03-EXECUTIVE-REPORTING (monthly)
---

# WF-01: WEEKLY REQUEST TRIAGE & INTELLIGENCE

## Workflow Purpose

Transform weekly GIS request data into strategic intelligence that:
1. **Balances team workload** across Patrick, Catherine, Allan, and Elaine
2. **Surfaces automation opportunities** to reduce reactive work from 60% to 40%
3. **Identifies strategic enterprise initiatives** hidden in simple map requests
4. **Develops Patrick's leadership thinking** through structured reflection
5. **Builds executive communication** by translating GIS work to business value

## Success Metrics

**Operational:**
- Weekly digest completed every Monday by 11am
- 3-5 actionable recommendations per week
- 80%+ of reflection questions lead to insights or actions

**Strategic (measured over time):**
- Reactive work percentage trending down (target: 60% → 40%)
- Number of repeat requests declining (via automation/enterprise solutions)
- Patrick's execution workload decreasing (delegation effectiveness)
- Team automation adoption increasing (Elaine's collaborative approach scaling)

## Workflow Execution

### STEP 1: Data Collection (Monday, 9:00-9:15am)

**Actions:**
1. Export M&D Request List from Microsoft List as CSV
   - Filter: All requests with activity in past 7 days
   - File naming: `M_D_Requests_YYYY-MM-DD.csv`
   
2. (Optional) Collect any flagged emails from the week
   - Complex external requests
   - Strategic triggers from stakeholders
   - Save as text or forward to analysis folder

3. Locate previous week's digest (if exists) for trend comparison

**Inputs Required:**
- [ ] M&D CSV export
- [ ] Previous digest (optional)
- [ ] Flagged emails (optional)
- [ ] Week date range

**Time Investment:** 15 minutes

---

### STEP 2: Request Pattern Analysis (Monday, 9:15-9:45am)

**Skill:** `SK-ANALYZE-WEEKLY-REQUESTS`

**Process:**
1. Upload M&D CSV to Claude
2. Provide context:
   ```
   Analyze this week's GIS requests using SK-ANALYZE-WEEKLY-REQUESTS.
   
   Week: [Start Date] to [End Date]
   Team: Patrick Gethin (Leader), Catherine Higgins (Enterprise), 
         Allan Blake (Dampier), Elaine Klava (Port Hedland)
   
   Focus on:
   - Repeat request patterns
   - Workload distribution and balance
   - Timing/performance metrics
   - Strategic context signals
   ```

3. Review output for:
   - Data quality issues
   - Surprising patterns
   - Missing context that needs manual interpretation

**Outputs:**
- Request volume analysis (by theme, location, department)
- Repeat pattern identification
- Workload distribution assessment
- Performance metrics (cycle time, overdue items)
- Strategic signals flagged

**Time Investment:** 30 minutes (20 min AI analysis + 10 min review)

---

### STEP 3: Opportunity Identification (Monday, 9:45-10:15am)

**Skill:** `SK-IDENTIFY-IMPROVEMENT-OPPORTUNITIES`

**Process:**
1. Feed Step 2 output to Claude
2. Provide context:
   ```
   Using the request analysis, apply SK-IDENTIFY-IMPROVEMENT-OPPORTUNITIES.
   
   Strategic priority: Shift team from 60% reactive to 40% reactive work.
   
   Technology context:
   - ArcGIS Desktop/Pro, ArcGIS Online, Portal
   - FME Desktop & FME Flow for automation
   - Python for scripting
   - Drone Deploy for imagery
   
   Team capability:
   - Elaine: Strong automation skills, collaborative approach
   - Catherine: Enterprise focus, technical depth
   - Allan: Solid GIS analyst, building strategic thinking
   - Patrick: Should be reducing execution, building team capability
   ```

3. Score and prioritize opportunities

**Outputs:**
- Strategic opportunities (enterprise datasets, self-service tools, standardization)
- Automation candidates with ROI scores
- Prioritized recommendations
- Quick wins vs. long-term initiatives

**Time Investment:** 30 minutes (20 min AI analysis + 10 min validation)

---

### STEP 4: Reflection & Translation (Monday, 10:15-10:30am)

**Skill:** `SK-REFLECT-AND-TRANSLATE`

**Process:**
1. Feed Steps 2 & 3 outputs to Claude
2. Generate reflection questions:
   ```
   Using SK-REFLECT-AND-TRANSLATE, generate strategic reflection questions.
   
   Focus areas:
   - Delegation opportunities (Patrick's execution load)
   - Strategic pattern recognition (what am I missing?)
   - Team development (building collective capability)
   - Executive positioning (communicating GIS value)
   - Leadership growth (operating at senior manager level)
   ```

3. Create business value translations:
   ```
   Translate this week's technical GIS work to business value language.
   
   Executive context:
   - GM and Manager have limited GIS knowledge
   - They understand business impact across: Marine, Engineering, Customer,
     Planning, Critical Port Services, Environment, Projects, Assets, Operations
   - Need to see GIS as strategic capability, not just "map making"
   ```

**Outputs:**
- 5-7 strategic reflection questions
- Business value translations of key work items
- Executive communication snippets

**Time Investment:** 15 minutes

---

### STEP 5: Digest Generation (Monday, 10:30-10:45am)

**Skill:** `SK-GENERATE-WEEKLY-DIGEST`

**Process:**
1. Compile all outputs from Steps 2-4
2. Generate digest:
   ```
   Using SK-GENERATE-WEEKLY-DIGEST, create the weekly report.
   
   Week: [Date Range]
   Inputs: [Analysis, Opportunities, Reflections from Steps 2-4]
   
   Format: Markdown for Notion import
   Tone: Professional but conversational, action-oriented
   Length: 4-6 pages, executive summary in 60 seconds
   ```

3. Quality check:
   - [ ] Executive summary clear and concise
   - [ ] Numbers reconcile correctly
   - [ ] 1-3 actionable recommendations present
   - [ ] Strategic opportunities have next steps
   - [ ] Delegation opportunities specific
   - [ ] Tone encouraging and forward-looking

**Outputs:**
- Complete weekly digest markdown file
- `Weekly-GIS-Digest-YYYY-MM-DD.md`

**Time Investment:** 15 minutes

---

### STEP 6: Save & Distribute (Monday, 10:45-11:00am)

**Actions:**
1. **Save Locally:**
   - `/workflows/outputs/weekly-digests/Weekly-GIS-Digest-YYYY-MM-DD.md`

2. **Push to GitHub:**
   ```bash
   git add workflows/outputs/weekly-digests/Weekly-GIS-Digest-YYYY-MM-DD.md
   git commit -m "Weekly digest: [Date]"
   git push origin main
   ```

3. **Import to Notion:**
   - Open Notion "Workflow Runs" database
   - Create new entry
   - Import markdown content
   - Tag: WF-01-WEEKLY-TRIAGE, Week: [Date]

4. **Share with Team (optional):**
   - Post in Teams GIS channel
   - Or discuss in Tuesday team standup
   - Or keep as leadership reference only

**Time Investment:** 15 minutes

---

## Total Time Investment Per Week

| Step | Activity | Duration |
|------|----------|----------|
| 1 | Data collection | 15 min |
| 2 | Request analysis | 30 min |
| 3 | Opportunity identification | 30 min |
| 4 | Reflection & translation | 15 min |
| 5 | Digest generation | 15 min |
| 6 | Save & distribute | 15 min |
| **TOTAL** | | **2 hours** |

**ROI Justification:** 2 hours/week invested to:
- Identify 5-10 hours/week of automation opportunities
- Surface strategic initiatives worth 10-20 hours/week of team capacity
- Develop leadership capability for career progression
- Build evidence for executive reporting and resource justification

---

## Workflow Dependencies

### Required Tools
- [ ] Microsoft List access (M&D Request system)
- [ ] Claude.ai or Claude Code (for AI analysis)
- [ ] Notion workspace (for report storage)
- [ ] GitHub repository (for version control)
- [ ] Git command line or Cursor integration

### Required Skills (Markdown Files)
- [ ] `SK-ANALYZE-WEEKLY-REQUESTS.md`
- [ ] `SK-IDENTIFY-IMPROVEMENT-OPPORTUNITIES.md`
- [ ] `SK-GENERATE-WEEKLY-DIGEST.md`
- [ ] `SK-REFLECT-AND-TRANSLATE.md`

### Context Files Needed
- [ ] Team roster with roles
- [ ] Technology stack list
- [ ] Strategic priorities document
- [ ] Previous digests (for trend analysis)

---

## Iteration & Improvement

### After First 4 Weeks (Monthly Review)
**Evaluate:**
- Which sections of digest are most/least useful?
- Which reflection questions led to action vs. which fell flat?
- Are automation opportunities being acted on?
- Is Patrick's delegation improving?
- What template adjustments needed?

**Adjust:**
- Refine skill prompts based on learning
- Add/remove digest sections
- Calibrate reflection question types
- Update ROI scoring criteria

### Integration with Other Workflows

**Feeds WF-02-STRATEGIC-PLANNING (Monthly):**
- 4 weeks of digests aggregated
- Automation candidates prioritized
- Strategic opportunities scoped
- Team capacity trends analyzed

**Feeds WF-03-EXECUTIVE-REPORTING (Monthly):**
- Business value translations accumulated
- Key contributions highlighted
- Strategic gap analysis informed
- Executive communication drafted

---

## Troubleshooting

### "Analysis feels generic or misses context"
**Fix:** Provide more specific team context, recent strategic initiatives, or known challenges in the prompt

### "Reflection questions don't push my thinking"
**Fix:** Give examples of questions that DID work, or specific blind spots you know you have

### "Opportunities identified aren't actionable"
**Fix:** Add more technical constraints (what tools are available, what skills team has) to scoring criteria

### "Digest is too long / too detailed"
**Fix:** Adjust SK-GENERATE-WEEKLY-DIGEST template to shorten sections or focus on top 3 insights only

### "Can't maintain 2-hour commitment weekly"
**Fix:** 
- Streamline to Steps 2, 3, 5 only (skip separate reflection step, integrate into digest)
- Run bi-weekly instead of weekly
- Delegate Step 1 data collection to team member

---

## Success Stories to Track

Document when this workflow directly leads to:
- [ ] Automation implemented that saves X hours/week
- [ ] Strategic opportunity identified that becomes enterprise project
- [ ] Delegation conversation that shifts work from Patrick to team
- [ ] Executive communication that results in positive feedback/budget/headcount
- [ ] Reflection insight that changes leadership approach

These become evidence for Maven course case study and internal justification for continuing the workflow.

---

## Version History

- **v1.0** - [Date] - Initial workflow design for Maven AI Agentic Leadership course
- **v1.1** - [Date] - [Adjustments based on first month usage]

---

**Last Updated:** [Date]  
**Next Review:** [Date]  
**Owner:** Patrick Gethin, GIS Team Leader, Pilbara Ports Authority
