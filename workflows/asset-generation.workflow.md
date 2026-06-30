---
title: Asset Generation Workflow
description: Creates structured briefs and checks for image, SVG, video, and 3D model assets.
---

# Asset Generation Workflow

This workflow guides the process of planning, sourcing, generating, optimizing, and registering visual assets before importing them into the project workspace.

## Step 1 — Choose Asset Type

Identify the classification of the visual asset to apply the correct design and build parameters:
- [ ] **Image**: Hero visual, photo background, texture backdrop.
- [ ] **SVG**: Custom vector icon, line art illustration, technical diagram, background grid.
- [ ] **Video**: Ambient looped background, UI walk-through loop, cinematic transition clip.
- [ ] **3D model**: Procedural mesh geometry, downloaded glTF/GLB object, custom Blender asset.
- [ ] **Texture**: Noise texture, normal map, roughness map, light leak background.
- [ ] **HDRI**: Environment reflection map for 3D materials.
- [ ] **Icon**: Small UI utility symbol or navigation indicator.

## Step 2 — Define Asset Role

Create a concise asset specification:
* **Section**: [e.g., Hero Background / Feature Grid Card 2]
* **Purpose**: [What does this asset communicate or do?]
* **Mood**: [e.g., Dark editorial, technical, high contrast]
* **Format**: [e.g., WebP, SVG, WebM, GLB]
* **Size**: [Define maximum target file size, e.g., <150KB for images, <2MB for models]
* **Fallback**: [Define fallback state for unsupported devices or loading phases]
* **Optimization**: [Define compression tools and resizing rules]
* **License**: [Confirm legal eligibility and source URL]

## Step 3 — Use Correct Brief

Review and apply the specific prompt constraints and templates:
- [ ] For raster images, use [image-prompts.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/assets-briefs/image-prompts.md).
- [ ] For icons, vector line art, and diagrams, use [svg-prompts.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/assets-briefs/svg-prompts.md).
- [ ] For looping background animations, use [video-prompts.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/assets-briefs/video-prompts.md).
- [ ] For 3D geometries, meshes, and materials, use [model-prompts.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/assets-briefs/model-prompts.md).

## Step 4 — Generate or Source

Sourcing and generating visual files must adhere to the following rules:
- **No unclear licenses**: Only download assets with explicit CC0, MIT, or compatible commercial-use terms.
- **No copyrighted/ripped assets**: Do not use assets extracted from commercial games, films, or stock platforms without licensing.
- **No unnecessarily heavy files**: Block assets that exceed the performance budget.
- **No generic AI slop**: Refine generative prompts to avoid standard glossy plastic rendering styles or deformed geometries.
- **No decorative assets without purpose**: Every asset must support a functional layout or copy narrative.

## Step 5 — Optimize

Reduce asset file sizes to ensure fast page load speeds:
- [ ] **Compress**: Run compression tools (e.g., Squoosh, Sharp, SVGOMG, gltf-pipeline, Handbrake).
- [ ] **Resize**: Scale files to the exact dimensions required for display.
- [ ] **Convert**: Convert assets to web-native formats (e.g., WebP/AVIF for images, WebM for video, GLB with Draco for 3D).
- [ ] **Simplify**: Reduce vector nodes, delete unused SVG markup, bake materials, and decimate mesh polygon counts.
- [ ] **Remove unused data**: Strip metadata, editor tags, hidden geometry, and testing channels.
- [ ] **Create fallback**: Provide static image or CSS-based fallbacks for dynamic/heavy assets.
- [ ] **Test in browser**: Verify loading behaviors under simulated network throttling.

## Step 6 — Log

Every external asset committed to the project must be documented:
- [ ] Open [asset-license-log.md](file:///C:/Users/HP/Documents/3D%20System/3D-Website-System-/assets-briefs/asset-license-log.md).
- [ ] Document the asset name, source URL, license type, attribution requirements, and local path.

## Step 7 — QA

Run a final visual and functional check:
- [ ] **Visual fit**: Does the asset match the styling, colors, and premium mood of the site?
- [ ] **Performance**: Does it load without layout shift or frame rate drops?
- [ ] **License**: Is it logged and compliant?
- [ ] **Accessibility**: Are alt text, aria labels, and color contrast ratios verified?
- [ ] **Responsive behavior**: Does the asset scale down correctly on mobile viewport profiles?

## Final Rule

Always create the asset brief and verify its optimization plan before generating or importing the asset.
