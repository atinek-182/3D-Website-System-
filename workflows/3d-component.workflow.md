---
title: 3D Component Workflow
description: Plans, builds, optimizes, and reviews a 3D component or scene.
---

# 3D Component Workflow

This workflow guides the design, modular structure, optimization, and testing of any 3D WebGL element, shader, or canvas scene within the project.

## Step 1 — Define Purpose

Before writing any R3F code, answer the following questions:
* **What does the 3D communicate?** [e.g., The physical casing of the device, data flow complexity]
* **Why is 3D better than 2D here?** [e.g., It allows the user to rotate the object to view different aspects, it reacts in real-time to mouse movements]
* **What should the user feel?** [e.g., Precision, technical depth, smooth responsive control]
* **What happens if it is removed?** [Does the site lose its core concept, or is it just a visual extra?]
* **Does it support content or brand?** [Explain how it directly references the headline or product branding]

> [!WARNING]
> If you cannot provide strong, clear answers to these questions, do not build the 3D component.

## Step 2 — Choose Method

Select the implementation path based on requirements:
- **procedural R3F**: Construct meshes in code using built-in geometries (spheres, boxes, planes) and custom math. (Best for performance and programmatic animations).
- **downloaded GLB/GLTF**: Import high-quality, pre-made CC0 assets.
- **generated model**: Sourced from generative 3D models.
- **Spline export**: Import assets created in Spline. Note the potential CPU/bundle footprint.
- **raw Three.js**: Write pure WebGL logic when working outside React or inside custom shader loops.
- **shader-only effect**: Use custom fragment shaders (e.g., raymarching, noise displacements) on a simple flat plane to create high-performance backgrounds.

## Step 3 — Scene Structure

To maintain clean and readable code, separate the Canvas component into modular files. Do not write the entire 3D scene in a single file.

### Recommended Scene Architecture:
* `SceneCanvas.tsx`: Initializes the `<Canvas>` wrapper, configures DPR, antialiasing, resizing, and shadow maps.
* `CameraRig.tsx`: Controls camera positioning, field of view, orbit controls, or smooth lerping toward mouse pointer coordinates.
* `Lighting.tsx`: Contains ambient, directional, spot, or environment maps. Keep light counts low.
* `Objects.tsx`: Contains the actual mesh, custom materials, group transforms, and model loader references.
* `Effects.tsx`: Configures postprocessing passes (bloom, ambient occlusion, depth of field) if strictly justified.
* `SceneFallback.tsx`: A lightweight 2D React component (e.g., CSS loading indicator or static image) that displays if WebGL initialization fails or is loading.

## Step 4 — Camera / Lighting / Materials

- [ ] **Camera purpose**: Choose Orthographic for technical/flat isometric grids, and Perspective for product depth and spatial movement.
- [ ] **Camera movement**: Smoothly interpolate (lerp) camera movements. Avoid raw jump cuts.
- [ ] **Lighting mood**: Set lights to match the website theme. Use an HDR environment map (via `<Environment>` from Drei) for realistic metallic reflections instead of adding multiple performance-heavy directional lights.
- [ ] **Material direction**: Use custom shaders for abstract art, and MeshPhysicalMaterial for premium glass/metal effects.
- [ ] **Shadows justified**: Turn off dynamic shadows (`castShadow={false}`) unless they are critical for grounding the model on a floor surface.
- [ ] **Postprocessing justified**: Ensure postprocessing is turned off by default on mobile devices to prevent thermal throttling.

## Step 5 — Performance Budget

Keep WebGL rendering light and fast:
- [ ] **Geometry**: Simplify mesh topology. Keep total vertex counts below 30k for mobile.
- [ ] **Textures**: Keep texture sizes to 1024x1024 or smaller, compressed as WebP or KTX2.
- [ ] **DPR cap**: Limit Device Pixel Ratio to `[1, 2]` to prevent high-DPI displays (like 4K monitors or Retina phones) from lagging during rendering loops: `<Canvas dpr={[1, 2]}>`.
- [ ] **Shadow cost**: Limit shadow map resolutions (e.g., `512` or `1024`) and update shadows only when objects move.
- [ ] **Postprocessing cost**: Keep postprocessing passes to a minimum. Avoid stacking multiple heavy passes like depth-of-field, bloom, and chromatic aberration.
- [ ] **Mobile fallback**: Disable heavy shaders or animations on mobile screens, or replace the canvas entirely with a static image fallback.
- [ ] **Reduced motion fallback**: Freeze frame rendering or pause loop rotations if the user has `prefers-reduced-motion` enabled.

## Step 6 — QA

Verify the 3D scene:
- [ ] **No console errors**: Check for Three.js warnings, duplicate render warnings, or lost WebGL context errors.
- [ ] **Canvas sizing**: Verify that the canvas fits its parent container correctly without causing scrollbars on resize.
- [ ] **Pointer events**: Ensure pointer clicks and raycasting intersect only with interactive 3D elements and do not block standard HTML scroll gestures.
- [ ] **Readability**: Ensure 3D meshes do not overlap or obscure text headings.
- [ ] **FPS feel**: Confirm a steady 60 FPS on test devices.
- [ ] **Memory leaks**: Verify that meshes, geometries, and materials are disposed of properly when the component unmounts.
- [ ] **Fallback**: Test that the page remains usable with WebGL disabled in browser settings.
- [ ] **Mobile behavior**: Test touch controls and check device thermals/battery usage during extended viewing.

## Final Rule

No random 3D decoration. Every 3D element must serve the visual narrative, run at 60 FPS, and gracefully degrade on low-end devices.
