# LinkedIn Thought Leadership Agent

**Version:** 1.0  
**Created:** 2025-01-23  
**Author:** GIS Team Leader, Pilbara Ports Authority

---

## OVERVIEW

This is a Claude-powered agent system for creating high-quality LinkedIn thought leadership articles about 3D spatial technology and asset management. The system uses 3 specialized subagents with approval checkpoints to research trends, draft articles, and ensure quality.

**Target Audience:** GIS professionals seeking to mature their capabilities  
**Writing Style:** Problem-first, punchy, challenge+guide  
**Article Structure:** Problem → Insight → Action Ladder  
**Output:** 800-1200 word LinkedIn articles with credible sources

---

## SYSTEM ARCHITECTURE

### Main Orchestrator
- **File:** `SKILL.md`
- **Role:** Coordinates 3 subagents, manages 4 approval checkpoints
- **Workflows:** Weekly scan, research, drafting, quality validation

### 3 Subagents

**1. Research Agent** (`/subagents/research-agent.md`)
- Discovers trending topics
- Conducts deep research
- Gathers ROI data and case studies
- Validates sources

**2. Writing Agent** (`/subagents/writing-agent.md`)
- Drafts articles in user's voice
- Follows Problem → Insight → Action structure
- Creates maturity-based action ladders
- Connects tech to business value

**3. Quality Agent** (`/subagents/quality-agent.md`)
- Validates structure and completeness
- Verifies source credibility
- Polishes voice and readability
- Final QA before publication

### 4 Approval Checkpoints

1. **Topic Selection** - Choose from 3 trending topics
2. **Research Brief** - Approve research direction
3. **Article Draft** - Review and edit content
4. **Final Validation** - Approve for publication

---

## FILE STRUCTURE

```
linkedin-thought-leadership/
├── SKILL.md                          # Main orchestrator
├── README.md                         # This file
│
├── subagents/
│   ├── research-agent.md             # Topic discovery + research
│   ├── writing-agent.md              # Article drafting
│   └── quality-agent.md              # Validation + polish
│
├── config/
│   ├── style-guide.md                # Voice & tone rules
│   ├── maturity-frameworks.md       # GIS/AM framework reference
│   └── source-criteria.md            # Credibility standards
│
├── templates/
│   ├── article-template.md           # (To be created)
│   ├── research-brief-template.md    # (To be created)
│   └── checkpoint-template.md        # (To be created)
│
├── prompts/
│   ├── weekly-scan.md               # (To be created)
│   ├── topic-approval.md            # (To be created)
│   ├── draft-approval.md            # (To be created)
│   └── final-approval.md            # (To be created)
│
└── examples/
    └── example-article.md            # (To be created)
```

---

## SETUP INSTRUCTIONS

### Step 1: Download Files

Download all files from this skill system to your local machine.

### Step 2: Version Control (Recommended)

```bash
# Initialize Git repository
cd linkedin-thought-leadership
git init

# Create .gitignore
echo "# Ignore temporary files
*.tmp
.DS_Store
" > .gitignore

# Initial commit
git add .
git commit -m "Initial commit: LinkedIn Thought Leadership Agent v1.0"

# Connect to GitHub (create repo first on GitHub)
git remote add origin https://github.com/your-username/linkedin-thought-leadership-agent.git
git push -u origin main
```

### Step 3: Manage in Cursor

1. Open Cursor
2. Open folder: `linkedin-thought-leadership/`
3. Edit files as needed
4. Commit changes to Git
5. Push to GitHub

### Step 4: Upload to Claude Projects

**Option A: Upload Main Files**
1. Go to Claude Projects
2. Create new project: "LinkedIn Thought Leadership"
3. Upload to Project Knowledge:
   - `SKILL.md`
   - All files from `/subagents/`
   - All files from `/config/`

**Option B: Use as User Skill (Advanced)**
1. Upload entire folder to `/mnt/skills/user/linkedin-thought-leadership/`
2. Claude will automatically detect and load when relevant

### Step 5: Set Custom Instructions (Optional)

In Project Settings, add:
```
Load /SKILL.md to act as LinkedIn Thought Leadership Agent.
Follow orchestrator workflow with 4 approval checkpoints.
Use 3 subagents: Research, Writing, Quality.
```

---

## USAGE

### Basic Commands

**Weekly Topic Scan:**
```
Run weekly scan
```
→ Research Agent finds 3 trending topics
→ You select one at Checkpoint 1

**Full Article Creation:**
```
Find topics and write an article
```
→ Runs all workflows with checkpoints

**Specific Topic:**
```
Write an article about digital twins for infrastructure asset management
```
→ Skips topic discovery, goes straight to research

**Continue Workflow:**
At any checkpoint, say:
```
Proceed
```
or
```
Approved, continue
```

**Request Changes:**
At any checkpoint:
```
Make the problem section more punchy
```
→ Agent adjusts and re-presents checkpoint

---

## WORKFLOWS IN DETAIL

### Workflow A: Weekly Automated Scan

**Trigger:** "Run weekly scan"

**Steps:**
1. Research Agent searches for 3 trending topics
2. Topics scored by: recency, business impact, maturity mapping, source quality
3. **CHECKPOINT 1:** You choose a topic (1, 2, or 3)

**Output:** 3 topic summaries with business value and maturity fit

---

### Workflow B: Deep Research Phase

**Trigger:** After topic selection

**Steps:**
1. Research Agent conducts deep research
2. Gathers ROI data, case studies, technical details
3. Maps to GIS/AM maturity frameworks
4. Compiles research brief
5. **CHECKPOINT 2:** You approve research direction

**Output:** Complete research brief with sources and maturity mapping

---

### Workflow C: Article Drafting

**Trigger:** After research brief approval

**Steps:**
1. Writing Agent drafts article
2. Follows Problem → Insight → Action Ladder structure
3. Writes in your voice (problem-first, punchy, challenge+guide)
4. Creates 3-tier maturity-based action steps
5. **CHECKPOINT 3:** You review draft

**Output:** Full article draft (800-1200 words) with sources

---

### Workflow D: Quality Validation

**Trigger:** After draft approval

**Steps:**
1. Quality Agent validates all quality standards
2. Verifies sources are credible
3. Polishes voice and readability
4. Checks structure and completeness
5. **CHECKPOINT 4:** Final approval

**Output:** Polished article with quality report, ready to publish

---

## CUSTOMIZATION

### Updating Your Voice

Edit `/config/style-guide.md`:
- Modify voice characteristics
- Add/remove forbidden phrases
- Update sentence patterns
- Change tone calibration

**After editing:**
1. Save in Cursor
2. Commit to Git
3. Re-upload to Claude Project

### Adding New Maturity Frameworks

Edit `/config/maturity-frameworks.md`:
- Add framework documentation
- Include maturity levels
- Provide usage guidance

### Adjusting Source Standards

Edit `/config/source-criteria.md`:
- Modify tier definitions
- Add/remove credible sources
- Update validation checklist

---

## WEEKLY AUTOMATION SETUP

### Manual Weekly Scan

Every Monday:
1. Open Claude Project
2. Type: "Run weekly scan"
3. Review 3 topics, select one
4. Approve at each checkpoint
5. Publish article by Friday

### Future: Scheduled Automation

*Coming soon: Integration with scheduling tools to auto-trigger weekly scans*

**Planned features:**
- Monday morning auto-scan
- Email notification with topics
- Slack integration for approvals
- Auto-post to LinkedIn (with approval)

---

## TROUBLESHOOTING

### Issue: Agent doesn't load skill files

**Solution:**
```
Load /SKILL.md and begin orchestration workflow
```

### Issue: Voice doesn't match style guide

**Solution:**
At Checkpoint 3, say:
```
Rewrite using the style guide - make it more punchy and problem-first
```

### Issue: Sources are weak

**Solution:**
At Checkpoint 2, say:
```
Find stronger sources from Tier 1 organizations like IAM or Deloitte
```

### Issue: Maturity ladder is unclear

**Solution:**
At Checkpoint 3, say:
```
Make each maturity tier more specific with concrete actions
```

### Issue: Article is too long/short

**Solution:**
At Checkpoint 3:
```
Trim to 900 words, focusing on the key insights
```
or
```
Expand the insight section with more ROI data
```

---

## BEST PRACTICES

### For Best Results:

✅ **Let the agent work through checkpoints**
- Don't skip steps
- Approve when ready, request changes when needed

✅ **Be specific with feedback**
- "Make it more punchy" (good)
- "I don't like it" (not helpful)

✅ **Trust the research**
- Research Agent prioritizes credible sources
- If data seems wrong, ask for verification

✅ **Use maturity frameworks strategically**
- Pick 1-2 frameworks per article
- Don't overcomplicate

✅ **Review but don't over-edit**
- The agent knows your voice
- Focus on strategic changes, not word-smithing

### Weekly Routine:

**Monday Morning:**
- Run weekly scan
- Select topic (5 minutes)

**Monday Afternoon:**
- Approve research brief (10 minutes)

**Tuesday/Wednesday:**
- Review article draft (15 minutes)
- Request any edits

**Thursday:**
- Final approval (5 minutes)

**Friday:**
- Publish to LinkedIn

**Total time investment: ~35 minutes per week**

---

## UPDATING THE SYSTEM

### Version Control Workflow:

1. **Edit in Cursor:**
   - Make changes to skill files
   - Test with Claude if needed

2. **Commit to Git:**
   ```bash
   git add .
   git commit -m "Update: [description of changes]"
   git push
   ```

3. **Update Claude Project:**
   - Re-upload changed files to Project Knowledge
   - Or update user skill directory

### What to Version:

✅ All .md files
✅ Configuration changes
✅ New templates or prompts
✅ Example articles

❌ Temporary files
❌ Personal notes
❌ Draft articles (unless examples)

---

## SUPPORT & FEEDBACK

### Getting Help:

**For agent behavior issues:**
- Review SKILL.md orchestrator instructions
- Check relevant subagent file
- Verify config files are loaded

**For voice/style issues:**
- Review /config/style-guide.md
- Provide specific feedback at checkpoints

**For technical issues:**
- Check file paths are correct
- Verify all files uploaded to Claude Project

### Providing Feedback:

When the agent produces great work:
- Save as example in `/examples/`
- Note what worked well
- Share with team

When something needs improvement:
- Document the issue
- Update relevant config or skill file
- Commit changes to Git

---

## CHANGELOG

### Version 1.0 (2025-01-23)
- Initial release
- 3 subagents with 4 checkpoints
- Complete configuration files
- Style guide and framework documentation
- Source credibility criteria

### Planned Features

**v1.1:**
- Article templates
- Checkpoint prompt templates
- Example articles
- Weekly scan automation

**v1.2:**
- Slack/Email integration
- Auto-scheduling
- Performance analytics
- Multi-topic queue

**v2.0:**
- LinkedIn API integration
- Analytics dashboard
- A/B testing framework
- Team collaboration features

---

## LICENSE

**Private Use:** This skill system is for use by GIS Team, Pilbara Ports Authority

**Not for redistribution** without permission

---

## CONTACT

**Created by:** GIS Team Leader, Pilbara Ports Authority  
**Purpose:** Reduce reactive work, build thought leadership, advance GIS maturity  
**Questions:** Update this README with internal contact info

---

## QUICK REFERENCE

### Most Common Commands:

```
Run weekly scan                           # Start workflow
Proceed                                   # Continue at checkpoint
Topic 2                                   # Select topic at Checkpoint 1
Make it more punchy                       # Edit request at checkpoint
Show me the sources                       # Verify research
Approved, publish                         # Final approval
```

### File Quick Links:

- **Main Orchestrator:** `/SKILL.md`
- **Research Agent:** `/subagents/research-agent.md`
- **Writing Agent:** `/subagents/writing-agent.md`
- **Quality Agent:** `/subagents/quality-agent.md`
- **Style Guide:** `/config/style-guide.md`

---

**Last Updated:** 2025-01-23  
**Version:** 1.0  
**Status:** Production Ready ✅
