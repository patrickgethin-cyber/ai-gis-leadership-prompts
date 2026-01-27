# Weekly Triage Skill - Resource Catalog

This folder contains the weekly-triage Agent Skill and its supporting resources.

---

## 📁 Skill Structure (3 Levels)

### Level 1: Metadata (Always Loaded)
**File:** `SKILL.md` (YAML frontmatter)
- Lightweight discovery information
- Loaded at Claude startup in system prompt
- No context window penalty

### Level 2: Instructions (Loaded When Triggered)
**File:** `SKILL.md` (main body)
- Procedural knowledge and workflows
- Loaded from filesystem when skill is invoked
- Only enters context when needed

### Level 3: Resources (Loaded As Needed)
**Folders:** `examples/`, `templates/`, `resources/`
- Supporting materials loaded on-demand
- Keeps context window efficient

---

## 📂 Resource Files

### examples/
Sample inputs and outputs showing "what good looks like"

- `sample-input.csv` - Example M&D request data (anonymized)
- `sample-output.md` - Example weekly digest report

### templates/
Reusable formats for consistent output

- `weekly-digest-template.md` - Report structure template

### resources/
Supporting materials and reference guides

- `roi-scoring-guide.md` - ROI calculation methodology
- `business-value-library.md` - Executive language examples

---

## 🎯 How Claude Uses This Skill

**Discovery (Level 1):**
```
Claude scans metadata and knows:
- This skill exists
- When to use it (trigger patterns)
- What it does (description)
```

**Invocation (Level 2):**
```
User: "Analyze this week's M&D requests"
Claude: Recognizes trigger → Loads SKILL.md instructions
Claude: Executes analysis framework
```

**Resource Loading (Level 3):**
```
Claude: Needs example format → Loads templates/
Claude: Unsure about ROI scoring → Loads resources/roi-scoring-guide.md
Claude: Only loads what's needed for current task
```

---

## 🔄 Version History

**v2.0** (2026-01-27)
- Upgraded to proper 3-level Agent Skill anatomy
- Enhanced YAML metadata with trigger patterns
- Added auto-invoke conditions
- Created Level 3 resource structure
- Production-ready for autonomous Claude discovery

**v1.0** (2026-01-15)
- Initial skill creation
- Basic instructions and methodology

---

## 📊 Usage Statistics

Track these metrics over time:
- Skill invocations per month
- Average analysis time
- Automation opportunities identified
- ROI of implemented automations

---

## 🤝 Contributing

To improve this skill:
1. Test with real M&D data
2. Note which sections are most/least useful
3. Identify missing patterns or edge cases
4. Update SKILL.md with improvements
5. Increment version number
6. Commit to GitHub with descriptive message

---

**Skill Owner:** Patrick Gethin, GIS Team Leader  
**Organization:** Pilbara Ports Authority  
**Repository:** ai-gis-leadership-prompts/skills/weekly-triage/  
**Status:** Production (v2.0)
