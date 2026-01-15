# Sync Translations Skill

## Purpose
Automatically synchronize changes from Korean documents (README.md, guide.md, slides) to their English and Japanese translations.

## When to Use
- After updating Korean README.md
- After updating docs/guide.md
- After updating docs/slides/main.md
- When user explicitly requests translation sync

## How It Works

1. **Detect Changes**: Use `git diff` to identify changes in Korean documents
2. **Analyze Changes**: Read the full updated Korean document
3. **Update Translations**: Apply equivalent changes to English (.en.md) and Japanese (.ja.md) versions
4. **Verify**: Ensure translations maintain the same structure and technical terminology

## Translation Guidelines

### Technical Terms (Keep in English)
- Claude Code, Claude
- hooks, skills, agents, commands, plugins
- slash commands
- context, prompts
- YOLO mode
- ZDR (Zero Data Retention)
- CI/CD, IaC, DevOps
- SOLID, TDD, XY Problem
- TypeScript, React, Go, Flutter, Dart
- CLI, MCP
- Git, GitHub, Marp, Mermaid
- PoC (Proof of Concept)
- SAST/DAST, OWASP

### Translation Principles
- **Korean → English**: Natural, professional English
- **Korean → Japanese**: Natural Japanese with appropriate technical terms
- **Structure**: Maintain identical markdown structure, headings, and formatting
- **Links**: Keep all URLs and link references intact
- **Code blocks**: Keep code examples unchanged
- **Narrative style**: Preserve the flowing, paragraph-based narrative style (not bullet lists)

## Execution Steps

### Step 1: Check for Changes
```bash
# Check which Korean documents have changed
git diff HEAD~1 HEAD --name-only | grep -E "(README\.md|docs/guide\.md|docs/slides/main\.md)"
```

### Step 2: For Each Changed Document

#### If README.md changed:
1. Read the full current README.md
2. Compare with README.en.md and README.ja.md
3. Update both translation files to match structure and content
4. Maintain language navigation links: `[English](README.en.md) | [日本語](README.ja.md)`

#### If docs/guide.md changed:
1. Read the full current docs/guide.md
2. Compare with docs/guide.en.md and docs/guide.ja.md
3. Update translations maintaining:
   - Section numbering (1-10)
   - Narrative paragraph style
   - Technical terminology in English
   - All hyperlinks

#### If docs/slides/main.md changed:
1. Read the full current docs/slides/main.md
2. Compare with docs/slides/main.en.md and docs/slides/main.ja.md
3. Update translations maintaining:
   - Marp YAML frontmatter
   - Slide count (should be identical)
   - Mermaid diagrams (identical)
   - Slide structure and breaks (`---`)

### Step 3: Create Commit
After updating translations, create a commit:
```bash
git add README.*.md docs/guide.*.md docs/slides/main.*.md
git commit -m "Sync translations: update English and Japanese versions

- Updated based on changes to [Korean document name]
- Maintained structure and technical terminology
- Verified all links and formatting

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

## Example Usage

User: "한국어 가이드를 업데이트했어. 번역을 동기화해줘"

Assistant actions:
1. Run `git diff` to see what changed in docs/guide.md
2. Read the updated docs/guide.md
3. Update docs/guide.en.md with English translation
4. Update docs/guide.ja.md with Japanese translation
5. Commit the changes

## Notes

- Always read the FULL document, not just the diff, to maintain context
- Use the translation guidelines from CLAUDE.md
- Preserve the narrative (서술식) style in guide documents
- Keep README documents concise and structured
- Slides should have identical structure across all languages
- If unsure about translation nuance, prioritize clarity and technical accuracy

## Related Files

- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/README.md` (Korean)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/README.en.md` (English)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/README.ja.md` (Japanese)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/guide.md` (Korean)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/guide.en.md` (English)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/guide.ja.md` (Japanese)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/slides/main.md` (Korean)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/slides/main.en.md` (English)
- `/Users/dohyunjung/Workspace/roboco-io/vibe-coding-recommendations/docs/slides/main.ja.md` (Japanese)
