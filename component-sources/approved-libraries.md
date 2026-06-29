# Approved Libraries & Tooling

This document lists all libraries and sources approved for building premium 3D websites. Do not install packages that are not registered here without prior review and approval.

---

## A. Core 3D
- **`three`**: Core WebGL engine.
- **`@react-three/fiber`**: React wrapper for Three.js.
- **`@react-three/drei`**: High-quality helpers, controls, and loaders.

---

## B. R3F Ecosystem Helpers
- **`@react-three/postprocessing`**: Post-processing effects (bloom, depth of field, Vignette). *Use with restraint.*
- **`leva`**: GUI controllers for debugging 3D meshes, light vectors, and camera angles during development. *Exclude from production.*
- **`maath`**: Fast math utilities for colors, vectors, and float quaternions.
- **`@react-three/rapier`**: Physics engine for R3F. *Use only when collisions or rigid-body math are needed.*
- **`gltfjsx`**: CLI tool to parse `.glb` / `.gltf` files into clean React components.

---

## C. Animation
- **`gsap`**: Complex scroll timelines, SVG drawings, canvas updates, section pinning.
- **`@gsap/react`**: GSAP hook wrapper for clean React scoping.
- **`motion`**: Smooth UI layout transitions, hovers, exits, and standard React states (imported from `motion/react`).
- **`lenis`**: Smooth scroll mechanism for desktop storytelling.
- **`@theatre/core`, `@theatre/studio`, `@theatre/r3f`**: Complex cinematic camera choreography keyframing.

---

## D. UI & Icons
- **`shadcn/ui`**: Standard clean UI components (Buttons, Dialogs, Sheets, Tabs). Customize styles for a premium editorial look.
- **`@radix-ui/react-*`**: Unstyled, accessible React primitives.
- **`lucide-react`**: Vector icon library.
- **21st.dev Magic**: Search directory for refined React component variants. Do not import blindly; custom review is mandatory.

---

## E. Spline Integration
- **`@splinetool/react-spline`**: React wrapper for loading Spline exports.
- **`@splinetool/runtime`**: Vanilla runtime for low-level Spline controls.
- *Rule*: Avoid unverified Spline MCPs; use official Spline exports only.

---

## F. Approved 3D Asset Sources
- **Poly Haven**: CC0 textures, models, HDRIs.
- **ambientCG**: CC0 PBR textures and basic shapes.
- **Quaternius**: CC0 optimized low-poly meshes.
- **Kenney**: Game asset packs for prototyping.
- **Khronos Group Samples**: Reference glTF assets.
- **Sketchfab**: Hand-selected models; check license metadata and attribution rules.
