# Custom Components Log

## Purpose

This log tracks key custom components, reused components, and adapted third-party assets within the project. It ensures that the engineering team maintains visibility over visual identity, styling methods, external dependencies, accessibility, and performance across the application.

## When To Log

Log a component when it meets any of the following criteria:
- [ ] **Brand-defining**: The component has high visual impact or shapes the website's unique identity.
- [ ] **Custom animation**: The component integrates advanced CSS transitions, Motion, or GSAP timelines.
- [ ] **3D/WebGL logic**: The component manages Canvas rendering, custom shaders, lights, cameras, or R3F geometry.
- [ ] **Reused across sections**: The component is utilized in multiple pages or sections.
- [ ] **External source**: The component was sourced or adapted from shadcn/ui, Radix, Drei, 21st.dev, or other repositories.
- [ ] **Adds a dependency**: The component requires importing a new package or library.
- [ ] **Affects accessibility or performance**: The component interacts with user inputs, keyboard focus, focus traps, or introduces potential rendering bottlenecks.

## When Not To Log

Do not log the following:
- [ ] **Tiny wrappers**: Simple layout components (e.g., standard flex column containers, margins).
- [ ] **Trivial layout divs**: Basic HTML wrappers that add no behavior or unique styling.
- [ ] **Local-only components**: Standard local helper components with no reuse potential.
- [ ] **Temporary experiments**: Code written for temporary testing that will be deleted before merging.

## Component Entry Template

Use this template to add new components to the log:

```markdown
### [Component Name]

* **Type**: [e.g., Custom / Adapted / 3D Canvas]
* **Source**: [e.g., shadcn/ui / 21st.dev / Custom]
* **Created/reused**: [Date created or first reused]
* **Purpose**: [Brief explanation of what the component does]
* **Files**: [Link to files, e.g., `src/components/MyComponent.tsx`]
* **Dependencies**: [e.g., lucide-react, framer-motion]
* **Styling method**: [e.g., Tailwind CSS / CSS Modules]
* **Animation method**: [e.g., Framer Motion / GSAP ScrollTrigger / R3F useFrame]
* **Accessibility notes**: [e.g., Aria labels, keyboard focus trapping, screen reader testing status]
* **Performance risk**: [e.g., Low / Medium (canvas re-renders) / High (needs optimization)]
* **Reuse potential**: [High / Medium / Low]
* **Keep/remove decision**: [Keep / Refactor / Deprecate]
* **Notes**: [Additional details, constraints, or outstanding issues]
```

## Source Types

Categorize every logged component under one of the following source types:
- **custom**: Built from scratch for this project.
- **shadcn/ui**: Sourced from the shadcn component library.
- **Radix**: Built on top of Radix UI primitives.
- **21st.dev**: Sourced from or inspired by the 21st.dev component ecosystem.
- **Drei**: Uses helper functions and objects from `@react-three/drei`.
- **R3F helper**: Custom hook or utility for React Three Fiber.
- **official docs example**: Sourced directly from library documentation (e.g., Three.js examples).
- **adapted community component**: Sourced from CodePen, GitHub, or developer blogs and edited to fit this project.

## Final Rule

If a component affects visual identity, application performance, keyboard accessibility, or project architecture, it must be logged in this document.
