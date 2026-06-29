# QA_AND_REVIEW.md

## Purpose

This file forces the agent to test and criticize the website before calling anything complete.

The agent must not say a feature is done just because code was written.

---

# Required Review After Every Milestone

After each milestone, answer:

1. What was built?
2. What files changed?
3. What works?
4. What is weak?
5. What is overbuilt?
6. What should be removed?
7. What should be improved next?
8. Are there console errors?
9. Are there performance risks?
10. Does it match the project brief?

---

# Visual QA

Check:

- hero has immediate impact
- typography hierarchy is clear
- spacing feels intentional
- colors match the direction
- sections do not feel generic
- 3D supports the concept
- animation supports the content
- UI is readable over canvas
- CTA is visible
- design does not look like a template

Score from 1 to 10:

- originality:
- visual quality:
- typography:
- spacing:
- interaction:
- premium feel:

If any score is below 7, propose fixes.

---

# Technical QA

Check:

- build passes
- no console errors
- no hydration errors
- no invalid HTML nesting
- no missing imports
- no unused major files
- no broken routes
- no duplicate animation loops
- no event listener leaks
- no uncleaned GSAP timelines
- no Three.js resource leaks
- no layout shift from loading assets

---

# 3D QA

Check:

- canvas sizes correctly
- canvas does not block UI clicks
- 3D object has purpose
- lighting is intentional
- camera is controlled
- scene does not feel random
- fallback exists
- loading state exists
- mobile behavior exists
- reduced motion behavior exists if needed
- postprocessing is justified
- shadows are justified
- model/textures are optimized

Score:

- 3D concept:
- 3D execution:
- lighting:
- camera:
- interaction:
- performance:

If 3D is weak, recommend simplifying instead of adding more effects.

---

# Animation QA

Check:

- animation has purpose
- motion rhythm is consistent
- scroll feels stable
- no animation fights another animation
- no excessive delays
- no motion sickness
- no random camera movement
- no broken mobile scroll
- reduced motion considered
- no over-animated text

Score:

- smoothness:
- restraint:
- timing:
- scroll behavior:
- interaction feedback:

---

# Performance QA

Check:

- bundle is not bloated
- assets are compressed
- images use correct sizes
- videos are not too heavy
- models are optimized
- no massive textures
- no unnecessary postprocessing
- no excessive particles
- no expensive shadows by default
- render loop is justified
- mobile fallback exists

Performance decision:

- Safe
- Needs improvement
- Risky
- Blocker

If risky or blocker, stop adding features and fix performance first.

---

# Accessibility QA

Check:

- semantic HTML
- valid heading order
- focus states
- keyboard navigation where needed
- alt text for meaningful images
- aria only where needed
- color contrast
- no important content only inside canvas
- reduced motion consideration
- form labels if forms exist

---

# Component QA

For reused components:

- source is documented
- dependency cost is acceptable
- styling is customized
- accessibility is preserved
- component does not look pasted
- component fits project tone
- code is understandable

For custom components:

- component has a clear purpose
- not too many responsibilities
- no unnecessary abstraction
- props are understandable
- animation cleanup exists
- responsive behavior considered

---

# Final Completion Gate

A feature can be called complete only if:

1. It matches the brief.
2. It runs without visible errors.
3. It passes basic responsive checks.
4. It does not feel generic.
5. It does not obviously harm performance.
6. It has a next-step review.

Do not say:
- "perfect"
- "fully optimized"
- "production ready"

Unless actual testing proves it.

---

# Final Report Format

Use this format after each milestone:

## Milestone Review

### Built
- ...

### Files Changed
- ...

### What Works
- ...

### Weak Points
- ...

### Performance Risks
- ...

### Design Score
- ...

### Technical Score
- ...

### Required Fixes
- ...

### Next Best Step
- ...

---

## CodeGraph QA Gate

Before approving major architecture changes, check:

* no accidental dependency cycles
* no duplicate component systems
* no unused major modules
* no broken import relationships
* no shared component changed without checking affected files
* no 3D scene logic mixed randomly with UI logic

---

## Comprehensive QA Verification Checklists

### 1. MCP Verification Gate
- Verify that `context7`, `codegraph`, `playwright`, `github`, and `magic` MCP servers are active in `C:\Users\HP\.gemini\config\mcp_config.json`.
- Verify that `filesystem` MCP is not configured globally.

### 2. Documentation Verification Gate
- Verify that Context7 MCP was queried for documentation before writing or updating code for Three.js, R3F, Drei, GSAP, Motion, Lenis, or shadcn/ui.
- Verify no hallucinated APIs or outdated configurations are used.

### 3. GSAP Cleanup Verification Gate
- Check all component code using GSAP.
- Verify that every timeline or ScrollTrigger instance has a corresponding unmount cleanup listener (e.g. `gsap.context()` cleanup inside `useEffect` or `@gsap/react` hook context).

### 4. Motion / react Usage Gate
- Verify that all Motion imports are sourced from `motion/react` (and not legacy `framer-motion`).
- Confirm animations respect `prefers-reduced-motion` settings.

### 5. Spline Performance Check Gate
- Check for memory footprint of any Spline React embeds.
- Verify fallback components (such as a simple 2D static representation) load immediately during network delays.

### 6. Model License Check Gate
- Cross-reference all imported models with `assets-briefs/asset-license-log.md`.
- Verify licenses are CC0 or have valid open source attributions. Confirm no weapon, adult, or trademarked brand models are present.

### 7. Asset Optimization Check Gate
- Check that all textures are compressed and downscaled to max 1K/2K resolution.
- Verify models are converted to optimized Glb/Gltf formats (optionally converted with `gltfjsx` and Draco compressed).

### 8. Playwright Visual QA Gate
- Run local dev server and query Playwright MCP to capture screenshots.
- Check layout at standard resolutions: Desktop (1440x900), Tablet (768x1024), Mobile (375x812).
- Inspect color contrast ratios, focus indicator visibility, and keyboard interactive elements.

### 9. Component Source QA Gate
- Verify component usage priority was followed (Existing -> shadcn -> Radix -> Drei -> Custom).
- Verify that brand-defining components (Hero, shaders, custom 3D logic) are completely custom and not copied from generic frameworks.

### 10. 21st.dev Component Review Gate
- Confirm any code adapted from 21st.dev has been customized.
- Verify that unnecessary tailwind classes or third-party dependencies were removed from the imported code.
- Verify the component integration is logged in `custom-components-log.md`.