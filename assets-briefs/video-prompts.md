# Video Prompt System

## Purpose

Video assets must only be used when they contribute meaningful atmosphere, layout depth, technical explanation, or product clarity. Because videos carry high bandwidth costs, each video must be strictly optimized and justified.

## When To Use Video

Consider using video for the following scenarios:
- [ ] **Ambient hero loop**: Providing high-quality ambient movement in the hero background when 3D scenes are loading or are too heavy for low-end devices.
- [ ] **Product demo**: Showing user interfaces, physical objects in motion, or software walk-throughs.
- [ ] **Case study preview**: Displaying high-fidelity mockups or rapid animations of past work.
- [ ] **Cinematic transition**: Serving as a rich visual wipe or morph during full-screen page transitions.
- [ ] **Background texture**: Adding ultra-subtle movement (e.g., light leaks, particles, or micro-noise loops) behind text layout.
- [ ] **Launch teaser**: Presenting high-impact motion graphic reveals for products or events.

## When Not To Use Video

Avoid using video in the following scenarios:
- [ ] **When it is only decoration**: If a static image or solid color works just as well.
- [ ] **When file size becomes too large**: If the clip exceeds 5MB (aim for < 1-2MB for ambient backgrounds).
- [ ] **When it hurts readability**: If the movement is too distracting or the contrast fluctuates wildly behind text.
- [ ] **When it competes with 3D**: If there is already an active interactive 3D WebGL canvas running in the same section.
- [ ] **When CSS/SVG/3D can do it lighter**: If basic code can recreate the visual effect with a fraction of the network cost.
- [ ] **When mobile autoplay becomes unreliable**: If data-saver modes or low-power modes prevent the video from starting, breaking the layout.

## Video Brief Template

Use this template to define technical specifications for any video asset:

* **Video name**: [e.g., dark-particles-loop]
* **Section**: [e.g., Hero Background / Feature Grid Card 1]
* **Role**: [e.g., Ambient Background / Interactive Feature Reveal]
* **Duration**: [e.g., 5 seconds / 15 seconds]
* **Aspect ratio**: [e.g., 16:9 / 9:16 / 1:1]
* **Loop type**: [e.g., Seamless Ping-Pong / Seamless Linear Loop / One-shot]
* **Movement**: [e.g., Ultra-slow drifting, minimal vertical pan]
* **Camera direction**: [e.g., Stationary, slow dolly forward]
* **Lighting**: [e.g., Low-key side-lit, high-contrast shadow casting]
* **Color palette**: [e.g., Monochromatic slate, muted teal, warm bronze]
* **Mood**: [e.g., Ethereal, technical, calm, high-energy]
* **Must avoid**: [e.g., Sudden flashes, visible noise, harsh shadows]
* **Output formats**: [e.g., WebM, MP4]
* **Poster image needed**: [Yes / No - path to poster image if Yes]
* **Mobile fallback**: [e.g., Static compressed WebP image]
* **Reduced motion fallback**: [e.g., Static frame or CSS animation fade-in]

## Loop Prompt Template

When generating seamless loops using AI video models:
- **Seamless loop**: Instruct the model to make the beginning and ending frames identical.
- **Subtle motion**: Force slow speeds (e.g., "slow-motion", "ultra-slow drift", "time-dilation").
- **No hard cuts**: Ensure there are no transitions, scene wipes, or cuts.
- **No random text**: Explicitly block any characters, text overlays, or credits.
- **No watermark**: Avoid any bottom-right/left logos or marks.
- **Controlled lighting**: Keep lighting levels constant to prevent flickering.
- **Web background optimization**: Structure the layout to remain low-contrast and avoid highly saturated colors.

## Hero Ambient Video Prompt

Use this structure for cinematic, atmospheric video backgrounds:

```
A seamless loop of [subject, e.g., abstract fluid obsidian curves] slowly morphing and shifting, slow-motion.
Camera: [e.g., stationary macro lens, shallow depth of field].
Lighting: [e.g., volumetric soft light leaks, low contrast dark shadows].
Mood: [e.g., premium dark editorial, calm, cosmic].
Colors: [e.g., deep charcoals, minimal bronze highlights].
Style: [e.g., photorealistic, tactile, high-end 3D render].
No hard cuts, no text, no watermarks, seamless loop.
```

## Product Motion Prompt

Use this structure for controlled, product-focused motion:

```
A 3D product showcase loop of [product, e.g., a minimalist sleek matte metal device] rotating slowly on its center axis against a dark background.
Camera: [e.g., clean studio camera, slow zoom-in].
Lighting: [e.g., clean white studio rim lighting, moody shadow definition].
Mood: [e.g., technical, precise, premium, clean].
Colors: [e.g., black, steel, silver, single blue indicator light].
Minimal movement, seamless loop, high-end design visual.
```

## Technical Texture Video Prompt

Use this structure for abstract grids, noise patterns, or light flow loops:

```
Abstract seamless loop of [element, e.g., vertical lines of warm white light leaks] drifting slowly across a dark textured concrete screen.
Camera: [e.g., flat orthographic perspective, soft focus].
Lighting: [e.g., low-intensity glow, soft vignetting].
Mood: [e.g., ambient technical texture, editorial grid structure].
Colors: [e.g., monochrome dark gray, warm white highlights].
Minimal visual noise, highly compressed web-safe texture, seamless loop.
```

## Negative Prompt Template

Always include this negative prompt set during video generation:

```
watermarks, logos, text, subtitle, credits, timestamps, video flicker, fast flashing, high contrast flashes, chaotic motion, camera shake, low-resolution compression artifacts, random object popping, busy background, noisy textures, cartoon style, anime look, low-poly structure.
```

## Export / Compression Checklist

Ensure all videos are processed through this checklist before committing to the repository:
- [ ] **Short duration**: Limit loop videos to between 4 and 10 seconds.
- [ ] **WebM format**: Encode in WebM (`vp9` or `av1` codec) as the primary format for modern browsers due to superior compression.
- [ ] **MP4 fallback**: Provide an MP4 (`h264` codec) fallback for Safari and older browsers.
- [ ] **Poster image**: Generate a matching compressed WebP image of the first frame. Set it as the `poster` attribute on the `<video>` element.
- [ ] **Muted**: Always include the `muted` attribute. Browsers will block autoplay if the video contains audio tracks.
- [ ] **playsInline**: Include the `playsInline` attribute so mobile devices play the video inside the page instead of opening full-screen media players.
- [ ] **Compression limits**: Ensure the final compressed file is under 2MB for desktop backgrounds and under 800KB for mobile devices.
- [ ] **Lazy-load**: Use an Intersection Observer script or dynamic import to load video sources only when the element enters the viewport.
- [ ] **Mobile autoplay check**: Write code to detect low-power mode and disable video autoplay, replacing it with the static poster image to prevent broken video icons.
- [ ] **Fallback display**: Ensure readability is maintained even if the video fails to load entirely.

## Final Rule

Never use massive video assets for decorative purposes. Every video must be compressed, muted, looped, and have a clear static image fallback.
