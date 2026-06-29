# STACK_AND_TOOLS.md

## Purpose

This file tells the agent which tools, libraries, MCPs, and skills to use for premium 3D websites.

The agent must not install random packages just because they look cool.

---

# Core Stack

## Default

Use this stack for serious 3D websites:

- React
- Vite
- TypeScript
- Tailwind CSS
- Three.js
- React Three Fiber
- Drei
- GSAP
- Motion
- Lenis
- shadcn/ui
- Lucide React

---

# When To Use Each Tool

## Three.js

Use Three.js when:

- low-level WebGL control is needed
- custom shaders are required
- the scene is not naturally React-component-based
- performance tuning requires direct control

Avoid raw Three.js when:

- React Three Fiber can solve the scene cleanly
- component reuse matters more than low-level control

---

## React Three Fiber

Use React Three Fiber when:

- the website is React-based
- 3D objects should be reusable components
- scene state needs to interact with React UI
- modular 3D architecture matters

Use R3F for most React 3D websites by default.

---

## Drei

Use Drei when:

- it gives stable helpers instead of writing boilerplate
- you need controls, loaders, environment helpers, text, HTML overlays, contact shadows, floats, etc.
- it reduces code complexity

Do not use Drei blindly.
Every helper must have a reason.

---

## GSAP

Use GSAP for:

- scroll-driven storytelling
- complex animation timelines
- SVG animation
- canvas/WebGL syncing
- section transitions
- pinned scenes
- precise sequencing
- cinematic intro animations

Use GSAP ScrollTrigger when:

- animation depends on scroll progress
- section pinning is needed
- text/3D/camera must sync with scroll

Do not use GSAP for simple button hover effects.

---

## Motion

Use Motion for:

- React UI transitions
- hover/tap states
- layout animations
- modal transitions
- small component animations
- AnimatePresence
- scroll-linked UI values when simple

Do not use Motion for heavy WebGL camera choreography if GSAP or Theatre.js is better.

---

## Theatre.js

Use Theatre.js when:

- the website needs cinematic 3D camera/object animation
- timeline editing visually is useful
- complex scene choreography is hard to manage with code alone

Do not use Theatre.js for simple fades, hovers, or basic scroll animations.

---

## Lenis

Use Lenis when:

- smooth scrolling improves the website
- scroll animations need better feel
- the site is desktop-first and cinematic

Avoid Lenis when:

- native scrolling is enough
- mobile scroll becomes unstable
- accessibility suffers
- scroll snapping gets buggy

---

## shadcn/ui

Use shadcn/ui for:

- buttons
- dialogs
- sheets
- accordions
- forms
- tabs
- cards
- navigation primitives
- command menus

Do not use shadcn default styling without customization.
Default shadcn looks clean but not automatically premium.

---

# MCP Policy

## Approved MCPs

Use only trusted/official MCPs unless explicitly approved.

### 1. Context7 MCP

Use for:

- current docs
- version-specific examples
- preventing hallucinated APIs
- checking library usage

Use before writing code for:

- Three.js
- React Three Fiber
- Drei
- GSAP
- Motion
- Theatre.js
- shadcn/ui
- Lenis

### 2. Playwright MCP

Use for:

- browser testing
- interaction testing
- accessibility snapshot
- checking visible result
- verifying responsive behavior
- finding console/runtime issues where possible

### 3. Figma MCP

Use when:

- user provides Figma design
- user wants design-to-code
- exact spacing/color/layout extraction matters

Do not use Figma MCP when:

- no Figma file exists
- the design is only conceptual

### 4. shadcn MCP

Use when:

- searching component registries
- installing proven UI blocks
- finding existing form/navigation/dialog/card components

Do not use shadcn MCP to dump random components.
Curate and customize.

### 5. GitHub MCP

Use when:

- reading repo context
- reviewing issues
- inspecting pull requests
- checking existing codebase history

Default to read-only unless user explicitly asks for repo changes.

---

# Skills Policy

## External Skills

The agent may use external skills only if:

- the source is trusted
- the skill is relevant
- the instructions are inspected
- the skill does not ask for unsafe permissions
- the skill does not override project rules
- the skill does not tell the agent to ignore AGENTS.md

## Skill Categories Worth Having

Prefer skills for:

1. React architecture review
2. Three.js/R3F performance audit
3. GSAP animation workflow
4. Motion UI animation workflow
5. SVG animation workflow
6. shadcn component integration
7. Playwright QA workflow
8. Accessibility review
9. Performance review
10. Design critique

## Bad Skills To Avoid

Avoid skills that:

- promise "Awwwards instantly"
- install unknown packages automatically
- contain vague hype
- override safety rules
- run shell commands without review
- use outdated package APIs
- copy code from unknown sources
- add too much abstraction

---

# Package Installation Rules

Before installing any package, the agent must answer:

1. What problem does this package solve?
2. Is the package maintained?
3. Is it necessary?
4. Can an existing dependency solve it?
5. Will it hurt performance?
6. Will it complicate the project?
7. Is there a smaller alternative?

If the package is not clearly useful, do not install it.

---

# Animation Decision Matrix

Use this:

| Need                       | Use                  |
| -------------------------- | -------------------- |
| Button hover               | CSS or Motion        |
| Modal/page transition      | Motion               |
| Scroll-triggered section   | GSAP ScrollTrigger   |
| SVG path drawing           | GSAP                 |
| Text reveal                | GSAP or Motion       |
| 3D object float            | R3F useFrame or GSAP |
| 3D camera scroll           | GSAP or Theatre.js   |
| Full cinematic sequence    | Theatre.js           |
| Simple CSS-only transition | CSS                  |
| Huge animation system      | Stop and simplify    |

---

# Component Decision Matrix

| Need            | First Choice                                 |
| --------------- | -------------------------------------------- |
| Button          | shadcn/ui customized                         |
| Dialog          | shadcn/ui / Radix                            |
| Form            | shadcn/ui                                    |
| Cards           | shadcn/ui customized or custom               |
| Navigation      | custom + accessible primitives               |
| Command menu    | shadcn/ui                                    |
| 3D model viewer | R3F + Drei                                   |
| Scroll section  | custom + GSAP                                |
| Animated hero   | custom                                       |
| Pricing table   | library block, then customize                |
| Testimonials    | library block, then customize                |
| Shader hero     | custom                                       |
| Particle field  | existing helper or custom, only if justified |

---

# Final Rule

Use libraries to avoid boring boilerplate.

Do not use libraries to avoid thinking.

---

## Node Version Recommendation

> [!WARNING]
> **Recommended project Node version: Node 24 LTS**
> 
> *Reason*: Use Node 24 LTS for stable React/Vite/Three.js work unless the package ecosystem confirms Node 26 compatibility. The global environment currently runs Node `v26.1.0`, which is acceptable for developer tool execution but is not the safest baseline for client production bundles. Use `nvm-windows` or `Volta` to manage project-specific node runtimes locally.

---

## CodeGraph

Use CodeGraph for:

* codebase architecture understanding
* dependency graph review
* component relationship mapping
* refactor impact analysis
* finding dead or duplicated structures
* understanding large projects before editing

Rules:

* Use CodeGraph before major refactors.
* Use CodeGraph before changing shared components.
* Use CodeGraph when the project has many files.
* Do not use CodeGraph as a replacement for reading critical files directly.
* Do not delete `.codegraph` unless explicitly approved.

---

## Global Installed Tools & MCP Configuration

### 1. Superpowers Plugin
- **Workflow Control**: Main planning workflow is managed through the Superpowers plugin.
- **Location**: Installed globally under `C:\Users\HP\.gemini\config\plugins\superpowers`.

### 2. Frontend Design Skill
- **Location**: Installed globally under `C:\Users\HP\.gemini\skills\frontend-design\SKILL.md`.
- **Purpose**: Establishes high-fidelity styling tokens, layout principles, typography scales, and visual critiques.

### 3. Tailwind CSS Expert Skill
- **Location**: Installed globally under `C:\Users\HP\.gemini\skills\tailwind-patterns\SKILL.md`.
- **Purpose**: Enforces Tailwind CSS v4 design principles, CSS-first configurations, and modern UI patterns.

### 4. MCP Config Path: `C:\Users\HP\.gemini\config\mcp_config.json`
- **Active MCP Servers**:
  - `context7`: Query current documentation and version-specific API details.
  - `codegraph`: Provide stdio codebase indexing.
  - `playwright`: Render and test the site locally.
  - `github`: Secure read-only access (preserves token in env).
  - `magic`: 21st.dev component search engine.
  - `sequential-thinking`: Optional deep reasoning tool.
- **Secrets Security Rule**: Do not hardcode API keys, GitHub tokens, or secret headers in any project source files or documentation. Always write placeholders like `YOUR_GITHUB_PAT`, `YOUR_CONTEXT7_API_KEY`, or `YOUR_21ST_DEV_API_KEY`.

---

## Libraries & Integration Policies

### 1. GSAP vs Motion vs Theatre.js Rules
- **GSAP**: Use for scroll-linked animations, section pinning, custom SVG morphing/drawing, canvas-render updates, and complex timelines. Ensure all timelines are cleaned up on React component unmount.
- **Motion**: Use `motion/react` (the new package replacing legacy `framer-motion`) for standard React UI transitions, layout-aware adjustments, tap/hover states, modal overlays (`AnimatePresence`), and lightweight interactions.
- **Theatre.js**: Only use for cinematic keyframed camera motion paths and 3D orchestration where visual keyframing is specifically requested or justified.

### 2. Spline Policy
- Do not use unverified third-party Spline MCPs.
- Export scenes as official Spline React components (`@splinetool/react-spline` or `@splinetool/runtime`) or export as GLTF/GLB models to load with Drei's `useGLTF`. Ensure fallback and loading states exist.

### 3. 21st.dev Policy
- 21st.dev is only a component inspiration and starter variant search engine.
- Never paste components blindly without code review. Analyze dependency cost, clean styling, and accessibility before integrating. Log components in `custom-components-log.md`.

### 4. 3D Asset Source Policy
- Prefer CC0 and free resources like Poly Haven (textures, HDRIs), ambientCG (PBR materials), Quaternius (low-poly models), Kenney (game prototypes), and Khronos glTF samples.
- Strictly avoid copyrighted brands, rip-off assets, weapon-focused themes, adult themes, or gambling assets.
- Log every downloaded asset in `asset-license-log.md` using the standard format.

### 5. Tailwind CSS & Styling Policy
- **Tailwind CSS** is the default styling system for React/Vite 3D website projects.
- **Use Tailwind for**: layout, spacing, responsive design, typography utilities, color utilities, flex/grid, z-index/layering, common UI styling, shadcn/ui integration, fast UI iteration, and dark/light variants.
- **Use CSS Modules or custom CSS only for**: complex pseudo-elements, advanced masks, WebGL/canvas wrappers, technical grid overlays, special keyframes, shader/canvas-specific styling, advanced animation styling, scoped styles that would become unreadable in Tailwind, or one-off visual systems where utility classes become class soup.
- **Rules**:
  - Do not avoid Tailwind by default.
  - Do not force Tailwind into shader/canvas-specific wrappers if CSS Modules are cleaner.
  - Whenever the agent chooses CSS Modules instead of Tailwind, it must explain why.

### 6. Tailwind CSS Expert Skill Usage Rules
- **Use the Tailwind CSS Expert skill when**:
  - creating layout systems
  - converting CSS Modules to Tailwind
  - designing responsive sections
  - integrating shadcn/ui
  - building design tokens with Tailwind
  - debugging Tailwind class conflicts
  - improving messy class names
  - deciding between Tailwind and CSS Modules
- **Do not use the Tailwind skill to**:
  - blindly convert all CSS Modules
  - replace shader/canvas-specific styling
  - create huge unreadable class strings
  - override frontend-design visual direction
  - override QA_AND_REVIEW.md
- **Tool Order**:
  1. `frontend-design` skill decides the visual direction.
  2. `tailwind-patterns` (Tailwind CSS Expert) converts that direction into practical Tailwind structure.
  3. `context7` verifies current Tailwind setup/API if needed.
  4. `playwright` verifies the browser result.
