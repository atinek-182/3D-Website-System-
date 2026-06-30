# Local Skills Policy

## Purpose

This folder is designated for project-specific Antigravity agent skills. These skills define custom, localized behaviors, automated tasks, and specialized workflows that are unique to the repository.

## Default Rule

Prefer global skills for reusable capabilities and workflows that apply across multiple projects. Use local skills only when the capabilities are specific to this repository or when they cannot be safely installed globally.

## Current Recommended Global Skills / Tools

Ensure your agent configuration has access to these global tools and skills:
* **Superpowers**: Standard framework for planning, brainstorming, and code execution.
* **frontend-design**: Design system guidelines for typography, spacing, and styling quality.
* **Tailwind CSS Expert** (if installed): Best practices for utility class hierarchies and grid architectures.
* **Context7 MCP**: Fetching updated documentation for React, R3F, Drei, GSAP, and Tailwind.
* **Playwright MCP**: Running visual checks, responsive layout validation, and console audits.
* **CodeGraph MCP**: Indexing and analyzing symbol usage, call paths, and file dependencies.
* **21st.dev Magic MCP**: Generating component inspiration and refactoring visual interfaces.
* **GitHub MCP (read-only)**: Pulling repository metadata and listing issues or pull requests.

## Rules For Adding Local Skills

Before adding a new skill to this directory, verify it complies with these rules:
- **Inspect SKILL.md**: Read the skill definition file completely before enabling it.
- **No copy-pasting**: Do not blindly copy skill configurations from external templates without reviewing their functionality.
- **No heavy frameworks**: Do not install large javascript or python libraries directly inside the skills folder.
- **No file overrides**: Local skills must not override or contradict rules defined in [AGENTS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/AGENTS.md) or [QA_AND_REVIEW.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/QA_AND_REVIEW.md).
- **No unsafe permissions**: Local skills must not request write permissions outside the project root or perform unverified command executions.
- **No hardcoded secrets**: Secrets, API keys, database credentials, and personal tokens must never be written inside skill source files.
- **Clear purpose**: Every skill must have a defined description, inputs, outputs, and triggers.

## When To Create A Local Skill

Create a local skill only in these situations:
* The workflow repeats frequently within this project's development cycle.
* Standard project markdown guides are not expressive enough to enforce structural coding constraints.
* The skill is highly specific to the project's unique business logic or API layer.
* The skill has clear triggers that fit neatly into development workflows.
* The skill directly improves output quality and prevents developer errors.

## When Not To Create A Local Skill

Do not create local skills for:
* One-time tasks, refactoring tasks, or setup instructions.
* Enforcing vague visual styling tastes that are better communicated in reviews.
* Copying random code snippets or utility classes from GitHub.
* Project-wide settings that are already covered by [AGENTS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/AGENTS.md).
* General engineering routines that are already managed by global tools.

## Final Rule

Skills are not decoration. Only add a local skill when it directly improves repeatable agent behavior.
