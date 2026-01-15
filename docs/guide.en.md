# Vibe Coding Guide

## Introduction
This guide has been compiled based on the author's vibe coding experiments and project records accumulated from November 2024 to January 2026. It is structured to serve as a roadmap for developers who are just beginning to try vibe coding, rather than for experts who already have their own established processes, and is grounded in the trial-and-error experiences and learning outcomes of the [author](https://github.com/serithemage), who has been working as a developer for nearly 30 years since 1995.

## 1. Purpose of This Document
The reason for this document's existence is to help development teams maintain consistent quality and productivity in the rapidly evolving AI coding tool environment. The guide is treated not merely as reference material but as a living standard that accumulates insights learned repeatedly from projects. Major changes are version-controlled with Git tags so that all team members look at the same guidelines, and it is regularly validated and improved by reflecting actual project feedback.

## 2. Definition of Vibe Coding
Vibe coding is not limited solely to the technology of generating code in natural language. It is a comprehensive methodology that accelerates all software activities including design, implementation, verification, documentation, and operations by utilizing AI tools across the board, and enables developers to invest more energy in problem definition and decision-making. The core goal lies not in code writing speed but in shortening the loop of problem definition and hypothesis verification.

## 3. Core Principles
Vibe coding sits on a continuum with existing software engineering. Familiar methodologies such as SOLID, TDD, design patterns, agile, and DevOps remain valid, and AI serves as a catalyst that enables these practices to be repeated more frequently at lower cost. Taking the modern software engineering activities proposed by Dave Farley (https://www.davefarley.net/?p=352) as an example, AI supports performing those activities at high speed through experimentation and automation. Above all, as the message "Don't trust AI, and don't trust people either" suggests, we must first design processes that can verify results. Automated tests, reviews, and backup routines play that role. When looking at productivity, remember the formula `Vibe Coding Productivity = Developer Competency × AI Tools & Process Productivity`. If problem-solving ability, domain understanding, and architecture·process·security competencies are weak, the productivity AI provides will also be limited, and the higher the competency, the more AI produces a multiplier effect. Ultimately, we must hurry to construct competencies centered on problem definition and systems thinking in preparation for an era when we no longer directly handle programming languages. Speed is paramount. Fast feedback loops help maintain focus and enable more experimentation. Aggressively use caching to minimize bottlenecks and wait times across all pipeline stages.

## 4. Tools
Claude and Claude Code currently provide the most balanced performance and update speed, and are evaluated to be about six months ahead of competing products. However, since tool superiority is not a fixed fact, we operate an evaluation routine that compares model quality, editing experience, collaboration features, security options, and cost quarterly, and adopt YOLO mode as the default to secure trust through automated testing·review·backup routines rather than manual human review. Through tight integration with DevOps toolchains (CI/CD, IaC, monitoring, etc.), we arrange the environment so that changes proposed by AI can be quickly deployed and observed. The team prefers CLI to make automation through scripts easy and reduce token usage, and uses MCP minimally only with Perplexity MCP for research purposes and Context7 MCP for referencing the latest documentation. In terms of language and stack, we have Go as the mainstay for backend and TypeScript/React for frontend, and have concluded that Go is particularly suitable for vibe coding thanks to its fast compilation, static typing, and concise syntax. For multiplatform development, we use the Flutter/Dart combination, and template project structure·test scaffolding·linter configuration with Makefile to provide the same guidelines to AI. When introducing new languages or frameworks, we follow the PoC→pilot→diffusion stages while updating prompts and code review checklists together. Containers support stable development and deployment, and databases should be chosen to fit the purpose, though SQLite is recommended for rapid prototyping.

## 5. Prompting
Good prompts convey not just requests but also hidden intentions. Like the XY problem, if we don't share the real need, the model will only present superficial solutions. Therefore, provide purpose as context, such as "trying to show the latest items first," and explain the constraints at hand and success criteria together. If you explicitly state to ask questions if anything is unclear before starting work, you can create a loop where AI checks requirements on its own, as suggested by Anthropic engineers' methodology (https://x.com/trq212/status/2005315275026260309). Turn repeatedly used prompts into assets using Claude Code's agents, commands, hooks, skills, and plugin features, version-control them in repositories so all team members invoke the same guidelines. Collecting metrics like the number of turns it took to resolve and the number of prompt rewrites also helps improve prompt quality.

## 6. Workflow
The overall workflow consists of requirements analysis, tech stack and architecture design, planning, and an implementation·verification·deployment loop, with a cycle that periodically undergoes overall review and performs major refactoring. In the requirements stage, document user scenarios, constraints, and success criteria and provide them to AI as well. In the architecture stage, brainstorm candidate design proposals with AI and leave key decisions in a Decision Log. During planning, divide work into verifiable units and define input·output·verification methods for each unit. In the execution loop, repeat the sequence of prompt, code generation, test, review, and deployment in short cycles, minimize wait time between each step through automation, and review the entire system every few loop iterations to readjust direction. When transitioning from a non-vibe coding project to vibe coding, documentation, introduction of automated testing, and CI/CD pipeline construction must precede the transition.

## 7. Quality Management
By breaking features into the smallest possible units and proceeding with implementation and testing simultaneously, you can verify results produced by AI in real time. Include at least one automated test in each unit, and combine layers like unit tests·snapshot tests·contract tests to increase reliability. Configure automated tests and CI/CD pipelines using Git or Claude Code's hook features, and maintain trustworthy guardrails even in YOLO mode by densely deploying UT, lint, security scans, etc. All changes must pass through this pipeline, and when they fail, record the prompt and log together to use as data for improving AI responses in the next iteration. In code review, check not only security vulnerabilities, data flow, and exception handling, but also whether prompts and automation assets are left in reusable form.

## 8. Security
When using AI tools, ZDR (Zero Data Retention) mode must be set as the essential default, and organizational data labeling·masking policies must be complied with. Integrate SAST/DAST tools and AI-based code scanners into CI to include automated security review in the pipeline, and configure rules so that code violating policy is automatically flagged by also specifying security policies in model prompts. When sharing sensitive data or non-public architecture information, design prompt templates to provide only minimal context.

## 9. Collaboration
In the vibe coding era, since prompts, processes, and automation are major assets, establish a team-level management system instead of individual ownership concepts. As the area one developer can cover has widened, redefine ownership, and share prompts and processes through repositories or Claude plugins so all team members use the same settings. Create an in-house vibe coding community to quickly disseminate best practices and failure cases, utilize pair programming or mob programming sessions to jointly conduct prompt design and review, and store session logs in a knowledge base to help new members onboard quickly.

## 10. Tips & Useful Resources

### Official Materials
- [Anthropic Research](https://www.anthropic.com/research) - Technical research on AI safety, interpretability, and alignment
- [Claude Code Official Documentation](https://code.claude.com/docs/en/overview) - Installation and usage guide
- [Anthropic News](https://www.anthropic.com/news) - Latest announcements and technical blog

### Community
- [Reddit r/Anthropic](https://www.reddit.com/r/Anthropic/) - User experience sharing and problem solving
- [GeekNews](https://news.hada.io/) - Korean AI/tech news

### Key Figures
- **Armin Ronacher** (Flask creator)
  - [Blog](https://lucumr.pocoo.org/) - Software development insights
  - [Mastodon](https://hachyderm.io/@mitsuhiko) - Technical discussions
  - [Bluesky](https://bsky.app/profile/mitsuhiko.at) - Latest updates

Organizing these resources in a team wiki and sharing learning notes helps new team members quickly adapt to vibe coding culture.
