# ROI Scoring Guide for Automation Opportunities

Quick reference for calculating automation ROI scores consistently.

---

## Formula

```
ROI Score = (Volume × Repeatability × Effort) / Complexity
```

---

## Scoring Dimensions

### Volume Score (1-5)
How often does this request occur?

| Score | Frequency | Requests/Month | Example |
|-------|-----------|----------------|---------|
| **5** | Daily | 20+ | Database maintenance, daily exports |
| **4** | Weekly | 8-19 | Weekly reports, regular updates |
| **3** | Bi-weekly | 4-7 | Fortnightly analysis, periodic checks |
| **2** | Monthly | 2-3 | Monthly summaries, quarterly prep |
| **1** | Occasional | <2 | Ad-hoc requests, rare needs |

### Repeatability Score (1-5)
How standardized is the process?

| Score | Standardization | Description | Example |
|-------|----------------|-------------|---------|
| **5** | Completely standard | Exact same steps every time, no variation | Database backup script |
| **4** | Mostly standard | Minor variations, 90% identical | Standard map with different extents |
| **3** | Standard core | Core process same, some customization | Analysis with varying parameters |
| **2** | Moderate judgment | Requires decision-making, 50% standard | Site assessment with context |
| **1** | Highly customized | Each instance very different | Complex strategic analysis |

### Effort Score (1-5)
How much time does each request take?

| Score | Time Investment | Hours | Example |
|-------|----------------|-------|---------|
| **5** | Very high | 4+ hours | Complex spatial analysis, multi-day projects |
| **4** | High | 2-4 hours | Detailed mapping, significant processing |
| **3** | Medium | 1-2 hours | Standard analysis, moderate complexity |
| **2** | Low | 30min-1hr | Simple maps, basic queries |
| **1** | Very low | <30 min | Quick exports, simple updates |

### Complexity Score (1-5)
How difficult is it to automate?

| Score | Difficulty | Description | Example |
|-------|-----------|-------------|---------|
| **5** | Expert required | Needs GIS analyst judgment, cannot standardize | Strategic planning, complex decisions |
| **4** | Complex workflow | Multi-step GIS workflow, advanced tools | Multi-source integration, complex modeling |
| **3** | Intermediate | Standard GIS operations, some scripting | Spatial joins, buffer analysis |
| **2** | Simple | Basic GIS operations, straightforward | Single-tool operations, simple exports |
| **1** | Self-service | Could be self-service with training | Data download, simple map viewer |

---

## Interpretation

### ROI Score Ranges

| ROI Score | Priority | Action | Example |
|-----------|----------|--------|---------|
| **> 40** | 🔥 Quick Win | URGENT - Implement ASAP | Daily export taking 2hrs (5×5×4÷1=100) |
| **20-40** | ⚡ Strong Candidate | HIGH - Schedule within quarter | Weekly report, standardized (4×4×3÷2=24) |
| **10-20** | 💡 Consider | MEDIUM - Add to backlog | Monthly task, moderate effort (2×3×3÷3=6) |
| **< 10** | ⏸️ Keep Manual | LOW - Not worth automation | Rare, complex task (1×2×3÷4=1.5) |

---

## Example Calculations

### Example 1: Standard Data Export

**Request:** "Export parcels shapefile for Port Hedland"
- Occurs 4× per week = **Volume: 4**
- Exact same process every time = **Repeatability: 5**
- Takes 2 hours per instance = **Effort: 4**
- Simple export operation = **Complexity: 1**

**ROI = (4 × 5 × 4) ÷ 1 = 80**
**Priority: 🔥 QUICK WIN** (Urgent - implement immediately!)

**Time Savings:** 4 requests/week × 2hrs = 8 hrs/week = 32 hrs/month

---

### Example 2: Weekly Biosecurity Map

**Request:** "Update Port Hedland biosecurity area map"
- Occurs 1× per week = **Volume: 4**
- Same map, different data = **Repeatability: 4**
- Takes 3 hours to complete = **Effort: 3**
- Requires GIS skill but standardizable = **Complexity: 2**

**ROI = (4 × 4 × 3) ÷ 2 = 24**
**Priority: ⚡ STRONG CANDIDATE** (High - schedule this quarter)

**Time Savings:** 1 request/week × 3hrs = 3 hrs/week = 12 hrs/month

---

### Example 3: Complex Coastal Analysis

**Request:** "Analyze coastal erosion impact on infrastructure"
- Occurs 1× per month = **Volume: 2**
- Each site different, requires judgment = **Repeatability: 2**
- Takes 8 hours per analysis = **Effort: 5**
- Needs expert GIS analyst = **Complexity: 5**

**ROI = (2 × 2 × 5) ÷ 5 = 4**
**Priority: ⏸️ KEEP MANUAL** (Low - not worth automating)

**Reasoning:** High complexity and low standardization make automation cost > benefit. Better to improve documentation/templates.

---

## Tips for Accurate Scoring

### Volume
- Count actual occurrences from M&D data
- Look back 3 months for patterns
- Don't inflate based on "feels like" more

### Repeatability
- Ask: "Could a junior analyst follow a checklist?"
- If requires "expert judgment" → score lower
- If "exact same buttons every time" → score higher

### Effort
- Use actual time tracking if available
- Include ALL time (data prep, QA, documentation)
- Don't just count "active GIS work"

### Complexity
- Be honest about automation difficulty
- FME workbench = Medium (2-3)
- Python script with error handling = High (4)
- "Just needs button in Portal" = Low (1-2)

---

## Common Mistakes

❌ **Overestimating volume** because recent requests feel frequent  
✅ Count actual instances from data

❌ **Underestimating complexity** because "it should be easy"  
✅ Consider edge cases, error handling, maintenance

❌ **Conflating effort with ROI**  
✅ High effort alone doesn't mean high ROI (complexity matters!)

❌ **Ignoring maintenance cost**  
✅ Some automation = creates technical debt

---

## When to Adjust Scores

**Increase Volume if:**
- Pattern is growing (trending up)
- New initiative will increase demand
- Currently ad-hoc but should be regular

**Decrease Complexity if:**
- You have existing similar automation
- Team has expertise in the tool
- Vendor provides templates/starting point

**Increase Effort if:**
- Includes hidden time (meetings, revisions, QA)
- Current process is inefficient (opportunity to redesign)

---

## Strategic Considerations

### Beyond ROI Score

**Also consider:**
- **Strategic alignment:** Does this support 60%→40% goal?
- **Team development:** Learning opportunity for automation skills?
- **Executive visibility:** High-profile work that demonstrates value?
- **Risk reduction:** Does automation reduce errors/inconsistency?

**Example:** Even medium ROI (15) might be priority if it's:
- Highly visible executive reporting
- Error-prone manual process
- Teaching moment for team automation skills

---

**Version:** 1.0  
**Last Updated:** January 27, 2026  
**For Use With:** weekly-triage skill v2.0
