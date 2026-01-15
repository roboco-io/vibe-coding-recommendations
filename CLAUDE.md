# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains the **Vibe Coding Recommendations** - a comprehensive guide for AI-assisted software development. The project consists of:

1. **Documentation** (`docs/`) - Korean-language guide on vibe coding methodology
2. **Presentation** (`docs/slides/`) - Marp-format slides for sessions
3. **PRD** (`docs/PRD.md`) - Product requirements and project planning

The guide is written from 30 years of development experience (since 1995) and 3 months of intensive vibe coding experimentation (Nov 2024 - Jan 2026). Target audience: developers just starting with vibe coding.

## Document Structure

### Core Documents
- **`docs/guide.md`** - Main vibe coding guide (Korean, narrative style, ~50 lines)
  - Sections: Introduction → Purpose → Definition → Principles → Tools → Prompting → Workflow → Quality → Security → Collaboration → Resources
  - Written in dense, paragraph-based narrative format
  - Includes embedded links to external resources

- **`docs/guide.claude.md`** - Alternative guide version (Korean, detailed narrative style, ~340 lines)
  - Same structure as guide.md but with extensive explanations
  - Includes Mermaid diagrams
  - Contains subsections (e.g., 4.1, 4.2, 4.3)
  - More suitable for thorough reading

- **`docs/slides/main.md`** - Marp presentation slides
  - 30 slides covering guide content
  - Uses monochrome Mermaid diagrams
  - Includes Q&A and reference sections

- **`docs/PRD.md`** - Product Requirements Document
  - Project structure, milestones, technical stack
  - Defines guide.md structure and content outline

## Content Guidelines

### Language & Style
- **Primary language**: Korean
- **Technical terms**: Keep in English (e.g., Claude Code, hooks, skills, agents, SOLID, TDD, CI/CD, ZDR, YOLO mode)
- **Translation principle**: Natural Korean expression while preserving technical accuracy
- **Narrative style**: Dense paragraphs, not bullet lists (for guide.md and guide.claude.md)
- **No praise/compliments**: Focus on facts and improvements only

### Key Concepts to Maintain
1. **Vibe Coding Productivity Formula**: `개발자 역량 × AI 도구와 프로세스의 생산성`
2. **Core Principle**: "AI를 믿지 말라! 사람도 믿지 말라! 신뢰할 수 있는 프로세스를 만들어라!"
3. **YOLO Mode**: Fast execution backed by automated testing, not manual review
4. **Tool Stack**: Claude/Claude Code (current best), Go (backend), TypeScript/React (frontend)
5. **MCP Philosophy**: Prefer CLI over MCP; minimal MCP usage (Perplexity, Context7 only)

### Diagram Standards
- Use **Mermaid** syntax only
- **Monochrome** (black and white) diagrams only
- Keep diagrams simple and focused

## Version Management

- Version format: `YYYY.N` (e.g., 2026.1)
- Track versions via Git tags
- Update version in document headers when making significant changes

## Multi-language Plan

The guide will be maintained in three languages:
- Korean (original): `docs/guide.md`
- English: `docs/guide.en.md` (planned)
- Japanese: `docs/guide.ja.md` (planned)

When updating content, consider which versions need synchronization.

## Working with This Repository

### Making Documentation Changes
1. For PRD updates, check if guide.md and guide.claude.md need corresponding updates
2. For guide changes, update slides (docs/slides/main.md) if the content is presentation-worthy
3. Keep narrative style consistent - avoid converting to bullet lists
4. When adding external links, verify they're active and relevant

### Using Research Tools
- Use **Perplexity MCP** for research on Korean/Korean-language topics (query in Korean)
- Use Perplexity MCP for non-Korean topics (query in English)
- Always include source URLs in research findings

## Related Resources

Key external references mentioned in the guide:
- [Dave Farley's Modern Software Engineering](https://www.davefarley.net/?p=352)
- [XY Problem explanation](https://xyproblem.info/)
- [Anthropic Research](https://www.anthropic.com/research)
- [Claude Code Documentation](https://code.claude.com/docs/en/overview)
- [Reddit r/Anthropic](https://www.reddit.com/r/Anthropic/)
