---
title: New 3D Website Project
description: Starts a new premium 3D website project using the local system files and global tools.
---

# New Project Workflow

Follow this systematic guide when starting any new premium 3D website project. This ensures that the design requirements are aligned and stack choices are validated before any development begins.

## Step 1 — Load System Files

Before writing code, read and understand the core system guidelines to align with project standards:
- [ ] Read [AGENTS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/AGENTS.md) to understand agent roles and boundaries.
- [ ] Read [PROJECT_QNA.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/PROJECT_QNA.md) for project-specific Q&A patterns.
- [ ] Read [STACK_AND_TOOLS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/STACK_AND_TOOLS.md) to review approved packages and configurations.
- [ ] Read [COMPONENT_LIBRARY_POLICY.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/COMPONENT_LIBRARY_POLICY.md) to understand dependencies.
- [ ] Read [WORKFLOWS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/WORKFLOWS.md) to review operational loops.
- [ ] Read [QA_AND_REVIEW.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/QA_AND_REVIEW.md) to understand testing criteria.
- [ ] Read [GLOBAL_SETUP.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/GLOBAL_SETUP.md) for global execution setup.
- [ ] Read [PROJECT_INSTALL_COMMANDS.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/PROJECT_INSTALL_COMMANDS.md) for direct installation instructions.

## Step 2 — Run Q&A

Establish alignment with the user:
- [ ] Open [PROJECT_QNA.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/PROJECT_QNA.md).
- [ ] Ask the questions defined in the Q&A file in small, bite-sized batches.
- [ ] Do not write any codebase implementation code during this step. Focus purely on gathering context.

## Step 3 — Create Brief

Draft a project brief in the workspace that defines:
- [ ] **Project goal**: The primary objective of the site.
- [ ] **Audience**: Who will visit the site and their device capabilities.
- [ ] **Visual direction**: Theme, typography, color palette, and mood.
- [ ] **3D direction**: Role of WebGL, types of objects, and fallback plans.
- [ ] **Motion direction**: Transition styles, scroll pacing, and intensity limits.
- [ ] **Asset needs**: Which images, SVGs, videos, and models are required.
- [ ] **Stack**: The selected packages and configurations.
- [ ] **Risks**: Potential performance bottlenecks or accessibility challenges.
- [ ] **First milestone**: The specific deliverable to verify first (typically a performant hero section).

## Step 4 — Use Tools

Incorporate global agent tools throughout the project:
- **Superpowers**: Use for planning and checklist execution.
- **frontend-design**: Use to establish premium typography, colors, and layouts.
- **Tailwind CSS Expert** (if installed): Use to structure styles cleanly.
- **Context7 MCP**: Use to search official documentation for libraries.
- **CodeGraph**: Use to explore code symbols and files after the codebase is initialized.
- **Playwright MCP**: Use to run visual QA and responsive testing.

## Step 5 — Choose Stack

Construct the application using the following recommended technologies:
- **Core**: React + Vite + TypeScript.
- **Styling**: Tailwind CSS by default to ensure uniform utility classes.
- **3D Render**: React Three Fiber (R3F) and `@react-three/drei` if 3D logic is needed.
- **Micro-interactions**: Motion (Framer Motion) for standard UI transitions and gestures.
- **Timelines/Scroll**: GSAP for advanced scroll triggers, SVG drawing, and canvas sync.
- **Primitives**: shadcn/ui and Radix UI for basic structural components.

## Step 6 — Stop Gate

- [ ] Stop execution before writing code.
- [ ] Present the project brief and stack decisions to the user.
- [ ] Wait for the user's explicit approval before initializing the repository.
