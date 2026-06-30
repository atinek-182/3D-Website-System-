---
title: Animation Workflow
description: Chooses and reviews animation systems for premium 3D websites.
---

# Animation Workflow

Animations on premium 3D websites must be smooth, intentional, and performant. This workflow guides developers in choosing the right animation tool, structuring animation code cleanly, and maintaining high motion quality.

## Step 1 — Define Purpose

Every animation must serve at least one of these primary purposes:
- [ ] **Guide attention**: Drawing the eye to key elements (e.g., CTA buttons, new features).
- [ ] **Reveal hierarchy**: Animating elements sequentially to show how content is structured.
- [ ] **Explain relationship**: Visualizing connections (e.g., card expanding, tabs shifting).
- [ ] **Create atmosphere**: Setting a premium, high-quality mood through subtle continuous motion.
- [ ] **Improve interaction feedback**: Providing tactile responses to hover, click, and drag gestures.
- [ ] **Support storytelling**: Syncing text reveals with background visuals as the user scrolls.

> [!WARNING]
> If an animation does not serve one of these purposes, remove it from the design.

## Step 2 — Choose Tool

Select the lightest, most specialized tool for the task:

| Animation Type | Target | Recommended Tool |
|---|---|---|
| Basic UI state | Hover, focus, opacity, simple color changes | **CSS transitions/animations** |
| React UI transitions | Mount/unmount transitions, layout shifts, gesture states | **Motion (Framer Motion)** |
| Scroll-triggered timelines | Pinned layout sections, multi-element sync, complex SVG paths | **GSAP (with ScrollTrigger)** |
| Cinematic 3D scenes | Precise keyframed 3D timelines, camera-rig choreography | **Theatre.js** |
| Continuous 3D loops | Object rotation, light pulses, simple particle drifts in WebGL | **R3F useFrame loop** |

- **CSS**: The fastest option. Use Tailwind transition utility classes (e.g., `transition-all duration-300 ease-out`) for simple interactive feedback.
- **Motion**: Ideal for React components. Provides declarative animations, gestural tracking (drag/hover), and layout animation support (`layoutId`).
- **GSAP**: The industry standard for complex scroll-driven layouts. Avoid using Motion for scrolling timelines, as GSAP's scroll integration is much more performant.
- **Theatre.js**: Best for complex 3D camera sweeps and object animations that require precise keyframing in an interactive timeline editor.
- **R3F useFrame**: Standard for lightweight Three.js animation loops. Perform simple mathematical displacements directly inside the rendering loop.

## Step 3 — Cleanup Rules

To prevent memory leaks and performance degradation:
- [ ] **Clean event listeners**: Always clean up scroll, resize, or pointer event listeners when components unmount.
- [ ] **Kill GSAP timelines/ScrollTriggers**: Always run `ctx.revert()` or explicitly call `.kill()` on GSAP ScrollTriggers and timelines inside the cleanup function of a React `useEffect` or `useLayoutEffect`.
- [ ] **Avoid React state in animation loops**: Never update React state variables inside a `useFrame` loop or GSAP animation tick, as this triggers React re-renders at 60 FPS. Use React `useRef` to modify DOM or Three.js properties directly.
- [ ] **Avoid duplicated RAF loops**: Do not spawn multiple concurrent RequestAnimationFrame loops. Combine animation logic under a single central loop wherever possible.
- [ ] **Respect reduced motion**: Check the system preference and disable animations or simplify transitions if the user prefers reduced motion.

## Step 4 — Motion Quality Checklist

Ensure all animations meet premium design standards:
- [ ] **Rhythm**: Pacing must feel natural. Fast starts with gradual decrescendo are generally preferred.
- [ ] **Easing**: Never use linear easing (`linear`) for movements; use smooth bezier curves (e.g., custom easing functions or spring configurations).
- [ ] **Stagger**: Apply a small staggered delay (e.g., `0.05s` increments) when animating grids or list items to make the layout feel organic.
- [ ] **No random movement**: Avoid arbitrary drift or jitter. Every movement should start from a logical origin and end at a clear destination.
- [ ] **No excessive delay**: Ensure entry animations complete quickly (usually under `0.8s`) so users are not left waiting to view content.
- [ ] **No motion sickness**: Avoid full-screen spinning, rapid scaling, or high-velocity camera pans.
- [ ] **No readability damage**: Ensure text is static and fully legible before the user needs to read it. Do not animate text continuously.

## Step 5 — QA

Validate motion implementation:
- [ ] **Browser test**: Verify that animations do not drop frames (stutter) on Chrome, Safari, and Firefox.
- [ ] **Responsive test**: Ensure scroll pinning and GSAP timelines recalculate correctly when changing between screen sizes and device orientations.
- [ ] **Reduced motion check**: Toggle standard system reduced-motion preferences to confirm that animations gracefully pause or transition to static states.
- [ ] **Performance check**: Monitor performance tab in DevTools to confirm GPU usage remains low and garbage collection does not spike.
- [ ] **Console check**: Verify that there are no console errors related to unmounted GSAP targets or missing Framer Motion context.

## Final Rule

Use the smallest, most performant animation tool that solves the problem. Keep transitions smooth, respect user preferences, and clean up all loops on unmount.
