---
title: QA Workflow
description: Reviews build quality, visual quality, browser behavior, accessibility, performance, and architecture.
---

# QA Workflow

This workflow ensures the web application is stable, responsive, performant, and visual-design compliant across all target browser engines.

## Step 1 — Build Check

Validate compilation stability:
- [ ] Run the production build command: `npm run build` (or equivalent bundler build command).
- [ ] Fix all TypeScript errors, types, and compiler warnings.
- [ ] Resolve broken import paths, casing discrepancies (Windows paths vs case-sensitive Linux builds), and packaging anomalies.
- [ ] Ensure the generated production bundle contains no unused files or testing routes.

## Step 2 — Browser QA

Execute automated and manual visual reviews using Playwright MCP:
- [ ] **Screenshots**: Take screenshots of key templates to check layout rendering.
- [ ] **Responsive views**: Verify layout at multiple viewports (Mobile: 375px, Tablet: 768px, Laptop: 1024px, Desktop: 1440px).
- [ ] **Click behavior**: Simulate clicks on all interactive widgets (menus, CTAs, expansion panels).
- [ ] **Scroll behavior**: Test smooth scroll interactions and scroll-triggered animation timelines.
- [ ] **Console output**: Review browser developer logs to identify javascript exceptions, failed asset requests, or performance warnings.
- [ ] **Accessibility snapshot**: Generate an accessibility tree dump to verify focus order and label visibility.

## Step 3 — Design QA

Ensure the visual implementation matches the premium aesthetic target:
- [ ] **Typography**: Verify font families, sizing, line-height, tracking, and letter spacing.
- [ ] **Layout**: Check grid alignments, alignment grids, card structures, and page borders.
- [ ] **Spacing**: Confirm consistency of padding, margins, and whitespace distribution.
- [ ] **Color**: Check color usage against the designated palette, ensuring contrast ranges are respected.
- [ ] **Premium feel**: Review subtle hover states, cursor interactions, glassmorphic effects, and fade-in states.
- [ ] **Originality**: Ensure the design avoids generic layouts, repetitive patterns, or standard framework templates.
- [ ] **Weak visual patterns**: Fix misaligned borders, overlapping text bounding boxes, and unpolished button states.

## Step 4 — Docs QA

Refer to official documentation via Context7 MCP to confirm configuration best practices for:
- [ ] **Tailwind setup**: Class optimizations, utility configurations, and component layers.
- [ ] **R3F (React Three Fiber)**: Canvas initialization parameters, context handlers, and mesh definitions.
- [ ] **Drei**: Hooks usage (`useGLTF`, `useHelper`) and canvas viewport bounds helper components.
- [ ] **GSAP**: Correct trigger configurations, cleanup routines, and pinning behaviors.
- [ ] **Motion (Framer Motion)**: State tracking, layout updates, and mount animations.
- [ ] **Lenis**: Smooth scroll configuration, frame rate syncing, and conflict avoidance with GSAP ScrollTrigger.
- [ ] **Theatre.js**: Project instances, sheet bindings, and timeline playback controls.
- [ ] **shadcn**: Primitives custom style integrations.

## Step 5 — CodeGraph QA

When the code volume grows, use CodeGraph to analyze project structure:
- [ ] **Architecture map**: Verify that modules, pages, and components have clear boundaries.
- [ ] **Dependency relationships**: Identify circular dependencies or unwanted heavy imports.
- [ ] **Duplicated systems**: Locate redundant math routines, duplicate canvas wrappers, or styling helpers.
- [ ] **Refactor impact**: Audit target symbols to assess downstream impacts before performing file changes.
- [ ] **Broken structure**: Ensure custom code does not violate layout modularity guidelines.

## Step 6 — Performance QA

Run audits to ensure smooth rendering:
- [ ] **Asset size**: Confirm all visual assets meet size budget constraints.
- [ ] **Model complexity**: Verify vertex count budgets are respected.
- [ ] **Texture size**: Check texture dimensions and confirm WebP or KTX2 compression.
- [ ] **DPR cap**: Ensure the WebGL Canvas Device Pixel Ratio is limited to `[1, 2]`.
- [ ] **Postprocessing cost**: Keep postprocessing filters off on mobile and limit passes on desktop.
- [ ] **Animation loops**: Avoid state updates inside loops and verify RAF cleaning on component unmount.
- [ ] **Memory leaks**: Monitor GPU allocation and confirm active WebGL nodes are disposed of on scene unmount.
- [ ] **Mobile fallback**: Verify that the static layout displays if WebGL fails to initialize.

## Step 7 — Final Report

Document the audit results using the following template:

```markdown
## QA Report

### Build
*Status: [Pass / Fail]*
*Details: [Build command results, compile size details]*

### Browser
*Status: [Pass / Fail / Warnings]*
*Details: [Browser rendering results, responsive layouts]*

### Design
*Status: [Pass / Fail / Refinements Required]*
*Details: [Visual checks, spacing, alignment, colors]*

### Accessibility
*Status: [Pass / Fail / Fixes Required]*
*Details: [Aria labels, contrast scores, keyboard controls]*

### Performance
*Status: [Pass / Fail]*
*Details: [Frame rate results, asset weight audit]*

### Architecture
*Status: [Pass / Fail]*
*Details: [Module separation, component boundary audits]*

### Weak Points
*List any minor rendering glitches, loading flickers, or unpolished transitions*

### Required Fixes
*List critical compilation issues, contrast errors, performance drops, or broken mobile states*

### Next Step
*Define the immediate corrective actions or deployment task*
```

## Final Rule

Do not mark a project or feature branch as production-ready without executing this testing workflow.
