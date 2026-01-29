# Registry Keeper Agent

**Agent ID:** registry-keeper  
**Version:** 1.0  
**Status:** Active  
**Owner:** Pat Gethin  
**Last Updated:** 2026-01-28

---

## Purpose

Autonomous agent that maintains sync between GitHub repository (`ai-gis-leadership-prompts`) and Notion AI Operations Registry. Eliminates 30 min/week manual catalog maintenance.

**Solves:**
- Manual Notion updates after GitHub commits
- Broken links and version drift
- Missing catalog entries
- Stale metadata

---

## How to Use

### Quick Sync (Most Common)

In Claude, just say:
```
"Run Registry Keeper to sync my GitHub with Notion"
```

Agent will:
1. Scan your GitHub repo
2. Find new/changed files
3. Update Notion automatically
4. Report what changed

**Time: ~2 minutes (vs. 30 min manual)**

---

### Full Audit

```
"Run Registry Keeper audit"
```

Gets complete health check:
- Missing catalog entries
- Broken links
- Stale assets (60+ days)
- Recommendations

---

## What It Does

### 1. GitHub → Notion Sync

**Scans for:**
- New `.md` files
- Modified files (via git timestamps)
- Deleted files

**Updates Notion:**
- Creates missing entries in AI Assets
- Updates "Last Updated" dates
- Populates GitHub links
- Sets correct Type (Agent/Skill/Prompt/Workflow/Context File)

**How it knows Type:**
- `agents/*.md` → Agent
- `skills/*.md` → Skill
- `prompts/*.md` → Prompt
- `workflows/*.md` → Workflow (goes in Workflows database)
- Support files → Context File

### 2. Relationship Mapping

**Analyzes files for references:**
- "uses weekly-triage-skill" → creates relation
- "WF-01-WEEKLY-TRIAGE" mentioned → links workflow

**Auto-creates:**
- "Uses Assets" relations in Workflows
- "Used In Workflows" backlinks in Assets

### 3. Validation

**Checks:**
- All GitHub links work
- All Notion entries have valid links
- No orphaned files (in GitHub but not Notion)
- No missing files (in Notion but not GitHub)

**Flags:**
- Broken links
- Stale assets (not updated 60+ days)
- Version mismatches

### 4. Recommendations

**Analyzes patterns to suggest:**
- "WF-02 hasn't been updated in 21 days - should we work on it?"
- "3 prompts are Active but unused - archive or integrate?"
- "High priority business process 'Heritage Queries' has no workflow yet"

---

## Configuration

### Required Access

**GitHub:**
- Repo: `patrickgethin-cyber/ai-gis-leadership-prompts`
- Read access to files and commit history

**Notion:**
- AI Assets database (read/write)
- Workflows database (read/write)
- Business Processes database (read)

### File Metadata Standard (Optional but Recommended)

Add frontmatter to GitHub files for better automation:

```markdown
---
title: weekly-triage-skill
type: skill
version: 1.2
status: active
last_updated: 2026-01-20
used_by:
  - WF-01-WEEKLY-TRIAGE
description: Analyzes weekly GIS requests
---

# Content starts here
```

**Benefits:**
- Agent reads Type directly (no guessing)
- Version tracking automatic
- Relations auto-created
- Status stays current

**Without frontmatter:**
- Agent infers from file location
- Works fine, just less precise

---

## Execution Modes

### Mode 1: Quick Sync (Default)
```
"Sync my registry"
```
- Scans for changes since last run
- Updates Notion entries
- Quick report (1-2 min)

### Mode 2: Full Audit
```
"Audit my registry"
```
- Complete scan of all files
- Validation checks
- Recommendations
- Detailed report (3-5 min)

### Mode 3: Specific File
```
"Add workflows/WF-04-NEW-WORKFLOW.md to Notion"
```
- Syncs single file
- Immediate (30 sec)

---

## How Registry Keeper Works

### Step 1: Scan GitHub
```
1. Connect to GitHub repo
2. List all .md files
3. Get last modified dates
4. Compare to last sync timestamp
```

### Step 2: Identify Changes
```
New files: Not in Notion yet
Modified: GitHub timestamp > Notion "Last Updated"
Deleted: In Notion but missing from GitHub
```

### Step 3: Update Notion
```
For each new file:
  - Determine Type from path
  - Create entry in correct database
  - Set properties (Name, Status, GitHub Link)
  - Read frontmatter if present

For each modified file:
  - Find Notion entry
  - Update "Last Updated"
  - Check for version bump
  - Refresh relationships
```

### Step 4: Validate & Report
```
Check all links work
Flag stale entries
Generate recommendations
Show summary
```

---

## Example Sessions

### Example 1: Weekly Sync

**User:** "Run Registry Keeper"

**Agent:**
```
🔄 Scanning GitHub repo...
Found 27 files (2 new since last sync)

📝 Changes Detected:
✅ NEW: prompts/heritage-automation.md
✅ MODIFIED: workflows/WF-01-WEEKLY-TRIAGE.md

🔧 Updating Notion...
✅ Created: heritage-automation (Prompt, Active)
✅ Updated: WF-01-WEEKLY-TRIAGE (Last Updated → 2026-01-28)

✅ Sync Complete
- 2 entries updated
- 0 broken links
- 100% catalog coverage
- Time: 1m 23s
```

### Example 2: Full Audit

**User:** "Audit my registry"

**Agent:**
```
🔍 Full Registry Audit

📊 Sync Status:
✅ 27 files in GitHub
✅ 18 entries in Notion
✅ 100% coverage (excludes READMEs)

🔗 Link Validation:
✅ All 18 GitHub links working
✅ 0 broken references

⚠️ Attention Needed:
- WF-02-STRATEGIC-PLANNING: No updates in 21 days
- email-drafter: Not used by any workflow
- business-value-library: Last updated 14 days ago

💡 Recommendations:
1. WF-02 is marked "Planned" - time to activate?
2. Consider archiving unused prompts (email-drafter)
3. 3 Business Processes have no linked workflows

🎯 Priority Suggestion:
Based on business process priorities,
recommend working on: "Heritage Site Query Automation"

Audit complete - Time: 3m 47s
```

### Example 3: Quick Add

**User:** "I just created WF-04-DATA-QUALITY.md - add it to Notion"

**Agent:**
```
🔍 Found: workflows/WF-04-DATA-QUALITY.md

📝 Creating Notion entry...
✅ Added to Workflows database
   - Name: WF-04-DATA-QUALITY
   - Status: Planned (inferred)
   - GitHub: https://github.com/.../WF-04-DATA-QUALITY.md
   - Last Updated: 2026-01-28

Done in 34 seconds.
```

---

## Success Metrics

**Efficiency:**
- Manual sync: 30 min/week
- With agent: <2 min/week
- **Time saved: 97%**

**Quality:**
- Catalog accuracy: 60% → 100%
- Broken links: Eliminated
- Stale metadata: Auto-detected

**Strategic:**
- Proactive recommendations
- Gap identification
- Priority suggestions

---

## Related Assets

**Uses:**
- GitHub API
- Notion API
- Git log analysis

**Supports:**
- All Workflows (keeps cataloged)
- All AI Assets (maintains registry)
- Business Processes (links implementation)

---

## Troubleshooting

### "Can't find new file"
- Wait 1 minute after commit (GitHub API sync)
- Check file is .md format
- Verify it's not in .gitignore

### "Notion entry exists"
- Agent won't duplicate
- Updates existing entry instead
- Check by Name match

### "Wrong Type assigned"
- Add frontmatter with correct type
- Or manually fix in Notion after sync

---

## Future Enhancements

**Planned:**
- Real-time webhook triggers (instant sync on commit)
- Notion → GitHub file creation
- Automated weekly digest emails
- Integration with WF-01 for automation candidates

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-28 | Initial agent creation |

---

**To run: Just ask Claude "Run Registry Keeper" anytime!**
