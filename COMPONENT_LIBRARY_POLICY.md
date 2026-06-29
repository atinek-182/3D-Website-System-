# COMPONENT_LIBRARY_POLICY.md

## Purpose

The agent should not rebuild basic components from scratch when high-quality existing components already exist.

But the agent must also not paste random component-library garbage.

This file controls component reuse.

---

# Main Rule

Use existing components for common UI.
Create custom components for brand-defining experiences.

---

# Use Existing Components For

- buttons
- inputs
- forms
- dialogs
- sheets
- accordions
- tabs
- dropdowns
- cards
- badges
- tooltips
- nav primitives
- pricing tables
- testimonials
- command menus
- theme toggles
- accessibility primitives

---

# Create Custom Components For

- hero section
- 3D scene
- cinematic transitions
- custom cursor
- WebGL effects
- shader effects
- scroll storytelling
- page-specific layouts
- original interaction systems
- brand-specific cards
- unique visual sections
- animated typography systems

---

# Approved Component Sources

Use these first:

1. shadcn/ui
2. Radix UI primitives
3. React Three Fiber ecosystem examples
4. Drei helpers
5. trusted GSAP examples/tutorials
6. trusted Motion examples
7. official library docs
8. project-owned component registry

---

# Conditional Sources

These can be used only after review:

1. Aceternity-style animated components
2. Magic UI-style animated components
3. community shadcn registries
4. CodePen experiments
5. Codrops tutorials
6. Awwwards-inspired snippets

Rules:
- inspect code first
- remove unnecessary dependencies
- rewrite styling to match project
- remove weak animation
- ensure accessibility
- ensure performance
- do not copy blindly

---

# Rejected Sources

Do not use:

- random GitHub snippets with no explanation
- npm packages with unclear maintenance
- components that require 10 dependencies for one effect
- copied website sections
- components with unreadable code
- components that break accessibility
- components that are only pretty in screenshots
- huge animation components that damage performance
- components that use outdated React patterns
- components that use direct DOM hacks without cleanup

---

# Component Selection Process

Before using an external component, the agent must answer:

1. What component is needed?
2. Can shadcn/ui or Radix solve it?
3. Does an existing project component already solve it?
4. Is this component generic or brand-defining?
5. Does it match the visual direction?
6. What must be customized?
7. What dependencies does it add?
8. What can be removed?
9. How will it be tested?

---

# Customization Rules

Every reused component must be customized for:

- spacing
- typography
- color
- border radius
- motion
- responsive behavior
- dark/light behavior if needed
- accessibility
- project tone

Do not leave default styling if the website is supposed to feel premium.

---

# 3D Component Reuse

Use existing helpers for:

- model loading
- environment lighting
- orbit/presentation controls
- contact shadows
- float motion
- text in 3D
- HTML overlays
- scroll controls
- shader utilities when stable

But create custom logic for:

- main 3D concept
- camera storytelling
- scroll choreography
- brand-specific object behavior
- unique shader direction
- special interaction model

---

# Component Log

Whenever a component is added, log it in:

component-sources/custom-components-log.md

Use this format:

## Component Name

- Source:
- Purpose:
- Files added:
- Dependencies:
- Customizations:
- Performance risk:
- Accessibility notes:
- Keep/remove decision:

---

# Quality Test

A reused component is acceptable only if:

- it fits the design
- it does not look pasted
- it does not add unnecessary dependencies
- it is understandable
- it can be maintained
- it works responsively
- it does not create console errors
- it does not hurt performance badly

---

# Final Rule

Steal principles.
Reuse primitives.
Customize heavily.
Do not paste identity.

---

## Component Source Priority Mapping

When a component is needed, resolve it using this strict priority order:

1. **Existing Custom Components**: Check the project-owned registry first to prevent duplicate logic.
2. **shadcn/ui**: Use for standard clean UI primitives (Buttons, Dialogs, Inputs, Sheets, Accordions, Tabs, Tooltips).
3. **Radix UI Primitives**: Use for custom unstyled components that require robust accessibility.
4. **21st.dev reviewed components**: Search for refined component ideas or variants. Do not import or paste directly without manual security, dependency, performance, and accessibility checks.
5. **Drei Helpers**: For R3F-specific objects (load models, shadows, environment reflections, text).
6. **Official Examples/Tutorials**: Extract math or shader code from trusted GSAP, Motion, or Three.js sources.
7. **Custom Implementation**: Build from scratch if no approved source fits the aesthetic or performance budget.

---

## Strictly Custom Components Requirement

The following elements must never be imported from generic packages and must be custom-developed to preserve brand-defining experiences:

*   **Hero Sections**: Shaders, layout composition, typography reveals, and entrance timelines.
*   **3D Scenes**: Orbit parameters, lighting arrays, interactive controls, and canvas scaling.
*   **Cinematic Transitions**: Scroll-driven section pinning, smooth camera choreographies, and page exits.
*   **Shader Effects**: Fragment/vertex shaders for visual cues, noise generation, and custom glsl effects.
*   **Brand-Defining Interactions**: Signature cards, unique layout grids, custom scroll snapping, and custom cursors.

---

## 21st.dev Magic MCP Usage Rules

*   **Role**: Component inspiration and code layout exploration only.
*   **Verification Checklist**:
    *   Inspect third-party dependencies; strip out bloated or duplicate libraries.
    *   Re-style typography, spacing, border-radii, and color tokens using global CSS.
    *   Verify keyboard navigation, focus indicator states, and screen reader elements.
    *   Register every integrated component in `component-sources/custom-components-log.md`.
*   **First Choice**: Custom styling over shadcn primitives remains the preferred choice for landing page primitives. 21st.dev is a secondary source of ideas.