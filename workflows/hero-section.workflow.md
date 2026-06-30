---
title: Premium 3D Hero Section
description: Builds one focused, premium, performant 3D hero section before expanding the site.
---

# Hero Section Workflow

Building a premium website requires focusing intensely on the hero section first. This workflow guides the creation of a visually stunning, highly performant hero section that sets the tone for the entire project.

## Step 1 — Hero Q&A

Establish the core requirements for the hero section by aligning on these questions:
* **Website name**: What is the name of the product or project?
* **Audience**: Who are the primary users?
* **Feeling**: What emotional response should the hero section trigger immediately?
* **Core message**: What is the primary heading/statement?
* **CTA**: What is the primary action we want the user to take?
* **Theme**: Is the page dark mode, light mode, or dynamic?
* **References**: Are there specific visual references? *(Note: Refer to user-provided reference files if available; do not invent fake ones).*
* **What to avoid**: What patterns, layouts, or visual tropes must be avoided?
* **3D role**: How does the 3D element support the headline or product?
* **Motion intensity**: How fast or reactive should the transitions and hover effects be?
* **Asset needs**: Which specific assets (models, videos, images, SVGs) are required?

## Step 2 — Hero Concept

Define the design direction:
- [ ] **One-line concept**: A concise description of the hero's visual theme.
- [ ] **Visual metaphor**: The connection between the core message and the visual assets.
- [ ] **3D purpose**: Why a 3D component is being used instead of a static image.
- [ ] **Typography direction**: Font choices, font sizes, tracking, and letter spacing.
- [ ] **Interaction idea**: What happens when the user moves their mouse, clicks, or scrolls.
- [ ] **Performance target**: Target size limits (e.g., total load under 3MB, steady 60 FPS on mid-range devices).

## Step 3 — Layer Plan

Organize the layout structure:
- [ ] **Background layer**: Static gradients, subtle video loops, grid meshes, or ambient noise.
- [ ] **Canvas/3D layer**: R3F canvas, lighting setup, interactive meshes, and postprocessing.
- [ ] **UI layer**: Navigation menus, logo, status bars, side indicators, and structural frame elements.
- [ ] **Typography layer**: Main headline (`<h1>`), subheading, taglines, and description.
- [ ] **CTA layer**: Primary and secondary buttons, form inputs, or arrow indicators.
- [ ] **Interaction layer**: Invisible pointer tracking containers and scroll hooks.

## Step 4 — Styling Rule

- **Tailwind CSS by default**: Use Tailwind classes for all structural grids, typography sizing, colors, standard flexbox layouts, padding, and basic transitions.
- **Custom CSS / CSS Modules**: Use *only* when implementing:
  - Complex Canvas parent container calculations.
  - Advanced background masking (e.g., SVG mask-image clipping paths).
  - Complicated pseudo-element visuals (e.g., noise overlay filters, glassmorphic backdrop filters).
  - Custom keyframe animations that are impractical to write with Tailwind classes.

## Step 5 — Implementation Milestones

Execute development in these logical stages:
1. **Layout and tokens**: Create the structural container grids and define CSS theme variables.
2. **Hero UI**: Code the static typography, navigation bar, side widgets, and buttons.
3. **3D scene**: Initialize the WebGL Canvas, configure camera coordinates, lights, materials, and test geometries.
4. **Motion**: Connect scroll listeners, mouse hover interactions, and entry animations using Motion or GSAP.
5. **Responsive pass**: Test and adjust container scaling, font sizes, and canvas viewport properties on mobile layouts.
6. **Playwright QA**: Run automated visual screenshots and console audits.

## Step 6 — QA Gate

Stop here. Do not build other sections of the website until the hero section is validated:
- [ ] **Build passes**: Verify `npm run build` completes successfully.
- [ ] **Browser QA passes**: Verify visual rendering on desktop and mobile.
- [ ] **Text readability**: Confirm heading contrast meets WCAG accessibility standards.
- [ ] **3D has a purpose**: Ensure the 3D element works and responds to interaction.
- [ ] **Responsive layout**: Confirm layout remains unbroken at 375px, 768px, 1024px, and 1440px widths.
- [ ] **Weak points**: Document any outstanding bugs or optimization opportunities.

> [!IMPORTANT]
> Always build and polish one excellent hero section before expanding to the rest of the website.
