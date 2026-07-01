# WORKFLOWS.md

## Purpose

This file defines repeatable workflows for building premium 3D websites.

The agent must follow the relevant workflow instead of improvising randomly.

---

# Workflow 1: New 3D Website Project

## Step 1 — Ask Q&A

Read PROJECT_QNA.md and ask the required questions.

Do not start coding yet.

## Step 2 — Create Project Brief

Summarize:
- website name
- goal
- audience
- feeling
- visual direction
- sections
- 3D concept
- motion concept
- asset needs
- stack
- constraints
- things to avoid

## Step 3 — Choose Stack

Read STACK_AND_TOOLS.md.

Select:
- base framework
- 3D library
- animation libraries
- UI component strategy
- MCP usage
- asset workflow

## Step 4 — Create Design System

Define:
- colors (defining Tailwind v4 `@theme` colors/design tokens)
- typography
- spacing
- border radius
- motion duration
- easing
- layout grid
- canvas layering
- section rhythm

## Step 5 — Create Milestones

Use:

1. Project setup
2. Design tokens
3. Hero section
4. 3D hero scene
5. Motion pass
6. Supporting sections
7. Asset pass
8. Responsive pass
9. Performance pass
10. Final QA

---

# Workflow 2: Image Generation Pipeline

Use this when the website needs generated images.

## Step 1 — Define Image Role

Ask:
- Is the image decorative, storytelling, product-based, background, hero, or texture?
- Is it needed for layout or just mood?
- Where will it appear?
- What size/aspect ratio is needed?

## Step 2 — Create Prompt

Create a prompt with:
- subject
- style
- mood
- lighting
- composition
- background
- color palette
- camera angle
- texture
- negative instructions

## Step 3 — Generate / Source Externally

The agent may prepare prompts and asset specs.
The user or approved image tool generates the asset.

Do not hardcode random image URLs.

## Step 4 — Optimize

Before using:
- compress
- resize
- convert to WebP/AVIF if suitable
- create mobile variant if needed
- add alt text if meaningful
- lazy-load if below fold

## Step 5 — Implement

Use:
- `<picture>` when multiple formats/sizes are needed
- CSS background only for decorative images
- normal image element for meaningful content

## Step 6 — QA

Check:
- image loading
- cropping
- mobile behavior
- text contrast
- performance cost
- visual consistency

---

# Workflow 3: SVG Generation Pipeline

Use this when the website needs icons, line art, animated marks, diagrams, or abstract graphics.

## Step 1 — Define SVG Type

Choose:
- icon
- logo mark
- technical diagram
- abstract shape
- path animation
- background pattern
- section divider

## Step 2 — Decide Source

Use:
- Lucide React for standard icons
- custom SVG for brand-specific visuals
- Figma export for designed assets
- generated SVG only when simple and clean

## Step 3 — SVG Quality Rules

The SVG must:
- be readable
- have clean paths
- not contain huge unnecessary metadata
- use currentColor where possible
- scale cleanly
- not include random IDs/classes
- not include inline junk from export tools

## Step 4 — Animation Choice

Use:
- CSS for simple hover/fill/stroke changes
- Motion for React-controlled UI SVG
- GSAP for path drawing, masks, complex timing, scroll sync

## Step 5 — Implementation

Create SVG components when reused.

Example structure:
- components/svg/BrandMark.tsx
- components/svg/GridPattern.tsx
- components/svg/AnimatedPath.tsx

## Step 6 — QA

Check:
- scaling
- accessibility
- dark/light contrast
- animation performance
- reduced motion fallback

---

# Workflow 4: Video Asset Pipeline

Use this when the website needs video backgrounds, cinematic loops, or product motion.

## Step 1 — Question The Need

Before using video, ask:
- Does video improve the site?
- Can SVG, CSS, or 3D do it lighter?
- Will video distract from content?
- Is the file size acceptable?

## Step 2 — Define Video Role

Choose:
- hero background
- section transition
- product demo
- ambient texture
- loading intro
- case study preview

## Step 3 — Video Specs

Default specs:
- short loop
- muted
- no audio by default
- compressed
- WebM + MP4 fallback if needed
- poster image
- lazy-loaded if below fold
- avoid huge 4K assets unless required

## Step 4 — Generation Brief

Create:
- subject
- style
- duration
- aspect ratio
- movement
- camera direction
- lighting
- loop behavior
- negative instructions
- export format

## Step 5 — Implementation Rules

Use:
- `video` element for actual video
- CSS overlay for readability
- poster image
- `playsInline`
- `muted`
- `autoPlay` only if justified
- pause/offload when not visible if heavy

## Step 6 — QA

Check:
- file size
- mobile behavior
- autoplay behavior
- text contrast
- CPU/GPU impact
- fallback poster
- reduced motion option

---

# Workflow 5: 3D Component Pipeline

Use this for any 3D scene, object, shader, or interaction.

## Step 1 — Define 3D Purpose

The agent must answer:
- What does the 3D communicate?
- Why is 3D better than 2D here?
- What should the user feel?
- How does it support the content?
- What happens if 3D is removed?

If there is no strong answer, do not build the 3D.

## Step 2 — Choose 3D Type

Choose:
- abstract object
- product model
- environment
- typography
- particle field
- shader surface
- interactive object
- scroll-driven scene

## Step 3 — Choose Implementation

Use:
- R3F + Drei for most React-based scenes
- raw Three.js for lower-level custom control
- GSAP for scroll/camera sync
- Theatre.js for cinematic keyframed scene
- custom shaders only when the project benefits from them

## Step 4 — Scene Architecture

Create:

- components/scene/SceneCanvas.tsx
- components/scene/Lighting.tsx
- components/scene/CameraRig.tsx
- components/scene/Objects.tsx
- components/scene/Effects.tsx
- components/scene/SceneFallback.tsx

Avoid one massive Scene.tsx file.

## Step 5 — Performance Budget

Before implementation, define:

- max texture size
- approximate geometry complexity
- whether shadows are allowed
- whether postprocessing is allowed
- mobile fallback
- reduced motion fallback
- loading state

## Step 6 — Interaction

Choose only what fits:
- cursor parallax
- scroll camera
- hover response
- click/tap state
- audio response
- drag/orbit
- idle animation

Do not add all interactions at once.

## Step 7 — Implementation

Build:
1. static scene
2. lighting
3. camera
4. object/material polish
5. one interaction
6. animation
7. fallback
8. performance pass

## Step 8 — QA

Check:
- frame feel
- memory leaks
- canvas sizing
- mobile fallback
- pointer events
- UI readability
- loading state
- no console errors

---

# Workflow 6: Animation Pipeline

Use this for all animation systems.

## Step 1 — Decide Animation Purpose

Every animation must do at least one:

- guide attention
- reveal hierarchy
- explain relationship
- create atmosphere
- support storytelling
- improve interaction feedback

If it does none, remove it.

## Step 2 — Choose Tool

Use:

- CSS for simple state changes
- Motion for React UI states
- GSAP for timelines, scroll, SVG, complex sequences
- Theatre.js for cinematic 3D keyframes
- R3F useFrame for lightweight continuous 3D motion

## Step 3 — Define Motion Language

Set:
- default duration
- easing
- stagger rhythm
- scroll speed
- delay rules
- hover response
- reduced motion behavior

## Step 4 — Build Small

Implement one animation group at a time.

Do not animate:
- every paragraph
- every card
- every image
- every background object

## Step 5 — QA

Check:
- does it feel expensive?
- does it delay the user?
- does it hurt readability?
- does it cause layout shift?
- does it work on mobile?
- does reduced motion work?
- does it conflict with another animation system?

---

# Final Workflow Rule

If the website starts feeling messy, remove effects before adding new effects.

---

## CodeGraph Architecture Review Workflow

Use this before large edits:

1. Query CodeGraph for project structure.
2. Identify important components, scenes, hooks, utilities, and shared files.
3. Map dependencies before editing.
4. Find likely impact of the planned change.
5. Read critical files directly.
6. Then implement.
7. Re-run CodeGraph if the architecture changed significantly.

---

## Technical & Integration Workflows

### 1. Global Setup Verification Workflow
1. Check `agy plugin list` to ensure `superpowers` is loaded.
2. Verify global `frontend-design` skill folder contains `SKILL.md`.
3. Check `C:\Users\HP\.gemini\config\mcp_config.json` for Context7, Playwright, CodeGraph, GitHub, and Magic keys.
4. Run verification queries to Context7 and Playwright to check responsiveness.

### 2. New Project Setup Workflow
1. Initialize the project: `npx create-vite@latest my-site -- --template react-ts`.
2. Check `.codegraph` directory; run `codegraph init` in the terminal immediately.
3. Install core dependencies (React Three Fiber, GSAP, Motion, Lenis) and Tailwind CSS setup (tailwindcss, @tailwindcss/vite). Recommend Node 24 LTS.
4. Set up Tailwind CSS v4 in `vite.config.ts` and import it in the main CSS file using CSS-first variables/tokens configuration.
5. Set up local directories: `.agents/skills/` and copy local skills if needed.

### 3. Spline-to-React Workflow
1. Export Spline scene: Select Code Export or GLTF export.
2. If R3F is preferred, export as GLTF, compress, and run `npx gltfjsx model.glb`.
3. If using React Spline, install `@splinetool/react-spline` and wrap with `<Suspense>` loading screens.
4. Ensure mouse/scroll controls do not block UI events or DOM interactions.

### 4. 3D Model Import & glTF Optimization Workflow
1. Download CC0 asset from ambientCG, Poly Haven, or Quaternius.
2. Check license constraints, capture url/author, and log in `asset-license-log.md`.
3. Put the model in `/public/models/`.
4. Run `gltf-pipeline` or `npx gltfjsx` to convert models to React components.
5. Apply mesh compressions (Draco/Meshopt) and downscale texture maps to max 1K/2K resolution.

### 5. GSAP Animation Workflow
1. Import GSAP: `import { gsap } from 'gsap'` and `import { ScrollTrigger } from 'gsap/ScrollTrigger'`.
2. Register plugin: `gsap.registerPlugin(ScrollTrigger)`.
3. Write animation code inside standard React hooks (`useEffect` or `@gsap/react` `useGSAP` hook).
4. **Crucial**: Clean up all ScrollTrigger instances and timelines on unmount using `context` or return cleanup.

### 6. Motion UI Animation Workflow
1. Import components: `import { motion, AnimatePresence } from 'motion/react'`.
2. Define transitions and animations via props: `<motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>`.
3. Use `layout` or `layoutId` for smooth layout transitions.
4. Respect accessibility: Provide fallback classes or check media settings for reduced motion.

### 7. Playwright QA Workflow
1. Fire up the local dev server: `npm run dev`.
2. Access the site via Playwright MCP or test runner.
3. Perform accessibility audit, capture desktop & mobile viewport screenshots.
4. Verify click paths, interaction loops, and check the console logs for leaks, errors, or warnings.

### 8. Asset License Logging Workflow
1. Immediately upon downloading an external model, image, or video, open `asset-license-log.md`.
2. Document Name, Source, URL, License details, Attribution instructions, Optimization methods, and Keep/Remove decision.
3. Never use or check-in models with missing metadata.

### 9. Styling & Tailwind CSS Workflow
1. Ensure Tailwind CSS is used as the default styling system for layouts, spacing, responsiveness, colors, typography, flexbox/grid, and standard component styling.
2. Only write custom CSS or CSS Modules for complex pseudo-elements, WebGL wrappers, special keyframes, shader/canvas-specific styling, or advanced visual animations.
3. Do not force Tailwind into canvas-specific containers if CSS Modules are cleaner.
4. Propose an explanation whenever CSS Modules are chosen instead of Tailwind CSS.

---

## Open Design Workflow Rule

Before visually important implementation, check whether Open Design exploration is needed.

Use workflows/open-design.workflow.md when:
* starting a premium hero
* starting a landing page
* redesigning a major section
* visual direction is not locked
* user references need to become design directions

Do not use Open Design for minor bug fixes or purely technical tasks.

Open Design output must be converted into:
* layout rules
* typography rules
* color tokens
* spacing rules
* motion rules
* 3D scene requirements
* asset requirements
* implementation risks
* QA checklist

Stop before implementation until the user approves the direction.