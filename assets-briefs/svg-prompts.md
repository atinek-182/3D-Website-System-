# SVG Prompt System

## Purpose

SVGs must be clean, scalable, lightweight, and directly usable within React applications. They should be built with clear structure, minimal paths, and semantic markup to allow easy manipulation via CSS, Motion, or GSAP.

## SVG Types

- [ ] **Icon**: Small UI actions, navigation elements, or status indicators.
- [ ] **Logo mark**: Brand identifiers and custom lettering.
- [ ] **Line-art illustration**: Minimalist wireframe-style visuals and outlines.
- [ ] **Technical diagram**: Concept diagrams, flowcharts, or system architectures.
- [ ] **Animated path**: SVGs designed for path drawing (dasharray/dashoffset animations).
- [ ] **Grid pattern**: Background structures, grids, and alignment markers.
- [ ] **Section divider**: Dynamic or static curves, angles, or transitions between page sections.
- [ ] **Cursor element**: Custom pointers, hover indicators, or tracker graphics.
- [ ] **Data/telemetry visual**: Dynamic charts, gauges, or terminal UI simulations.

## SVG Spec Template

Use this template when requesting or designing a new SVG asset:

* **SVG name**: [e.g., system-node-icon]
* **Type**: [e.g., Icon / Animated Path / Technical Grid]
* **Purpose**: [What does this SVG represent or do?]
* **Where used**: [e.g., Hero Section Sidebar / Service Cards]
* **Stroke or fill**: [e.g., Stroke-only / Fill-only / Mixed]
* **Color behavior**: [e.g., Inherited / Fixed / Theme-responsive]
* **Should use currentColor**: [Yes / No]
* **Animation needed**: [Yes / No - describe animation behavior if Yes]
* **Accessibility label needed**: [Yes / No - provide description if Yes]
* **Responsive behavior**: [e.g., ViewBox scales, fixed size, repeating background]
* **Export restrictions**: [e.g., No empty `<g>` tags, no transforms on root, keep path indices constant]

## Icon Prompt Template

When generating or drafting icons, follow these constraints:
- **Simple silhouette**: Ensure the concept is readable at small sizes. Avoid complex structures.
- **No text**: Never include actual text characters within paths; use icons purely as symbols.
- **No gradients unless justified**: Prefer flat colors to keep code simple and allow easy coloring.
- **Clean paths**: Single, unified paths are preferred over overlapping disjointed segments.
- **Consistent stroke width**: If using strokes, use a single uniform stroke width (e.g., `strokeWidth={2}`).
- **Scalable**: Must render perfectly from 16px to 64px without losing detail or appearing blurry.

## Diagram Prompt Template

For schematic or technical diagrams:
- **Clear hierarchy**: Use varying line weights or subtle opacity to denote structure.
- **Labels optional**: Ensure lines and shapes convey the flow even without text. Use HTML text overlay for actual words when accessibility matters.
- **Technical layout**: Keep angles exact (e.g., 45, 90 degrees) and layouts mathematically aligned.
- **Simple line system**: Rely primarily on clean, straight strokes and circles. Avoid complex curves.
- **No visual clutter**: Strip out background boxes, shadows, and borders that code can handle.
- **Theme compatibility**: Make paths adaptive so they remain visible in both dark and light modes.

## Animated Path Prompt Template

For SVGs that will be animated using path-drawing techniques:
- **Stroke path**: Ensure paths use `stroke` and `stroke-width`. Avoid outlines converted to fills.
- **Draw-on animation compatibility**: Verify paths have clean start and end points without gaps.
- **GSAP-compatible path**: Avoid nested transforms on the target `<path>` elements, which can offset GSAP's positioning calculations.
- **No unnecessary groups**: Group `<path>` elements only when animating them as a single unit. Avoid empty or redundant `<g>` tags.
- **Reduced motion fallback**: Plan a static fallback state where the full path is immediately visible if the user prefers reduced motion.

## Technical Grid Prompt Template

For repeating background grids:
- **Hairline grid**: Use very fine strokes (`strokeWidth={0.5}` or `1`).
- **Subtle opacity**: Keep grids subtle (e.g., opacity `0.05` to `0.15`).
- **No visual noise**: Avoid heavy gradients, crosshatches, or offsets unless they are dynamic.
- **Dark-mode safe**: Ensure colors look excellent on deep slate or charcoal backgrounds.
- **Responsive scaling**: Define grid paths within a `<pattern>` tag for seamless infinite scaling.

## SVG Cleanup Checklist

Before importing any SVG into the React codebase, perform the following cleanup steps:
- [ ] **Remove metadata**: Delete `<metadata>`, editor tags (e.g., Illustrator, Figma attributes), creator comments, and XML declarations.
- [ ] **Remove editor junk**: Strip out `id` tags from paths (unless needed for scripts), `enable-background`, and editor-specific attributes.
- [ ] **Remove hidden layers**: Delete elements with `display="none"` or `opacity="0"`.
- [ ] **Remove unused defs**: Clean up `<defs>` tags, removing gradients, filters, or clips that are not referenced.
- [ ] **Simplify paths**: Run path simplification tools (e.g., SVGOMG, SVGO) to merge paths and reduce node count.
- [ ] **Use viewBox**: Always specify `viewBox="0 0 W H"` and remove hardcoded `width` and `height` properties from the root `<svg>` tag (unless a fixed default scale is required).
- [ ] **Avoid fixed width/height**: Let the CSS parent layout determine the width and height of the component.
- [ ] **Use currentColor**: Replace hardcoded hex colors with `currentColor` on `stroke` or `fill` to allow Tailwind or CSS color classes to target the SVG directly.
- [ ] **Check dark/light contrast**: Ensure the SVG is clearly visible on its intended background theme.

## SVG Animation Rules

- **CSS animations**: Use for simple hover states, continuous rotation, basic fill transitions, or opacity changes.
- **Motion (Framer Motion)**: Use for state-based SVG animation (e.g., path morphing, path drawing on mount, hover gesture responses).
- **GSAP**: Use for complex path drawing, compound masks, multi-step timelines, and scroll-synchronized animations.
- **Avoid heavy SVG filters**: Do not use complex SVG filters (e.g., turbulences, color matrices) unless the performance impact is carefully measured and justified.

## Final Rule

Every SVG in the codebase must be clean, scalable, accessible, and free of proprietary editor export junk.
