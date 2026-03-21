# Decisions Log

> This file records important decisions and their reasoning.
> Format: date, decision, reason, alternatives.

---

## 2026-03-20 | Project Setup

### Decision: Documentation structure
- **What:** Created CHARACTER_BIBLE.md, CONTENT_STRATEGY.md, PROMPTS_*.md, TOOLS_RESEARCH.md
- **Why:** Complete documentation needed before starting content generation
- **Alternatives:** Could have started generating immediately, but without docs there would be no consistency

### Decision: Reference photos in repository
- **What:** Vehicle reference photos stored directly in Git repo
- **Why:** Simple access for both Claude and user
- **Risk:** Repo size may grow, consider Git LFS in the future

### Decision: AVIF → PNG conversion
- **What:** Kawasaki photos converted from AVIF to PNG
- **Why:** AVIF is not universally supported, PNG is lossless and compatible
- **Tool:** heif-convert

---

## 2026-03-21 | Claude Configuration

### Decision: Create .claude/ folder with memory + decisions + style-guide
- **What:** Added CLAUDE.md + .claude/memory.md, decisions.md, style-guide.md
- **Why:** Ensure consistency across Claude sessions
- **Alternatives:** Could have used just CLAUDE.md, but separate files are cleaner

### Decision: All .md files in English
- **What:** Switched all documentation files from Slovak to English
- **Why:** User requested English for all .md files; better for international consistency
- **Alternatives:** Keep in Slovak, but English is more universal

---

## Template for New Decisions
```
## YYYY-MM-DD | Area Name

### Decision: Short description
- **What:** What exactly was decided
- **Why:** Reason for the decision
- **Alternatives:** What else was considered
- **Impact:** What impact it has on the project
```
