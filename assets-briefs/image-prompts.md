# Image Prompt System

## Purpose

Images used in premium 3D websites must have a clear, functional role. They should never be added just for decoration or to fill empty space. Every image must support the core narrative, enhance the atmospheric mood, and align with the visual and performance standards of the project.

## When To Use Images

Use images when they serve one of the following purposes:
- [ ] **Hero background**: Establishing the initial visual atmosphere when 3D assets are loading or where 3D is not practical.
- [ ] **Editorial mood image**: Evoking a specific narrative feeling or emotional response.
- [ ] **Case study visual**: Showing real project context, results, or interfaces.
- [ ] **Texture**: Serving as materials or background patterns (e.g., grain, paper, concrete textures).
- [ ] **Product/supporting visual**: Highlighting details of a physical or digital product.
- [ ] **Social preview**: Defining the OG (Open Graph) image for social sharing.
- [ ] **Section atmosphere**: Enhancing the mood or depth behind content sections.

## When Not To Use Images

Avoid using images in the following scenarios:
- [ ] **When CSS/SVG/3D can do it lighter**: If code can generate the gradient, grid, or pattern with a smaller footprint.
- [ ] **When it distracts from typography**: If the image clashes with the readability of text placed over or near it.
- [ ] **When it creates performance cost without purpose**: If it adds weight to the page load without offering unique value.
- [ ] **When licensing is unclear**: If the source license does not explicitly allow commercial modification and redistribution.
- [ ] **When it looks generic AI-generated**: If it contains typical AI artifacts, generic glossy plastic lighting, or standard stock aesthetics.

## Image Role Checklist

Use this template when planning or importing any new image:

* **Image role**: [e.g., Hero Background / Editorial Narrative / Product Detail]
* **Section**: [e.g., Hero / Case Studies / Footer]
* **Purpose**: [What does this image communicate or do?]
* **Mood**: [e.g., Cinematic, Minimal, Technical, Moody]
* **Must support**: [e.g., Readability of white heading, Dark theme]
* **Must avoid**: [e.g., High-contrast spots behind text, Cluttered center]
* **Aspect ratio**: [e.g., 16:9 / 1:1 / 4:5]
* **Required output formats**: [e.g., WebP, AVIF]
* **Mobile crop needed**: [Yes / No - define mobile visual center]
* **Alt text needed**: [Yes / No - provide descriptive alt text if Yes]
* **Optimization plan**: [e.g., Resize to max 1920px width, compress using Squoosh]

## Master Image Prompt Template

For generated images, use this structural prompt template to guide image generation models:

```
[Subject description] in [Composition/Framing], shot with [Camera Angle/Lens description].
Lighting: [Lighting style, e.g., low-key cinematic, subtle side-light].
Style: [Visual style, e.g., tactile editorial photography, minimalist technical render].
Mood: [Mood, e.g., dark atmospheric, precise, industrial].
Color Palette: [Specific color scheme, e.g., deep charcoal gray, muted silver, neon amber accents].
Background: [Background description, e.g., out-of-focus concrete texture, dark void].
Texture: [Texture details, e.g., visible grain, brushed metal, matte paper feel].
Detail Level: [Detail guidance, e.g., high clarity, soft-focus background, tactile micro-details].

Aspect Ratio: [--ar 16:9 / --ar 4:5]
```

## Negative Prompt Template

Always include this negative prompt block to prevent standard AI-generation artifacts and maintain a premium aesthetic:

```
generic AI look, oversaturated colors, bad anatomy, deformed limbs, floating elements, random text, watermarks, signatures, logos, visual clutter, low-resolution details, overdone glow, fake 3D plastic look, shiny cartoon skin, generic stock photo style, lens flare overload, cheap rendering.
```

## Prompt Examples

### Premium Dark Editorial Background Texture
> "A close-up shot of a dark tactile concrete wall texture with organic cracks and subtle grain. Minimalist, flat composition. Lighting is soft, raking from the left side to highlight the relief. Deep gray and muted charcoal color palette. High clarity, ultra-fine texture details. No bright spots, dark-mode ready. --ar 16:9"

### Abstract Spatial Web Studio Visual
> "An abstract architectural space showing clean concrete steps disappearing into a dark atmosphere. Shot from a low angle, wide lens. Minimalist composition, clean geometric lines. Soft, indirect glow from an unseen source casting long, soft shadows. Muted monochromatic silver and black color scheme. Soft focus in the distance, sharp lines in the foreground. --ar 16:9"

### Technical Blueprint-Style Image
> "A detailed technical blueprint of a precision mechanism, displaying clean white hairline diagrams, grids, and dimensions on a deep slate gray background. Orthographic projection, perfectly flat layout. Style is clean vector line art. Precise, mathematical mood. High contrast but dark-mode safe. No clutter, no text characters, only clean paths and line markers. --ar 4:3"

### Cinematic Product-Lighting Mood Image
> "Minimalist product pedestal made of raw obsidian stone, sitting in a dark, empty void. Cinematic side-lighting casting a clean edge highlight on the pedestal. Sleek, premium, mysterious mood. Color palette is matte black and dark gray. Clean edges, tactile stone texture. Background is a dark, clean gradient. --ar 1:1"

## Optimization Checklist

Ensure every image added to the project meets these criteria:
- [ ] **Resize**: Downscale the image to its maximum required display size (e.g., 1920px for full-screen hero backgrounds, 800px for section images).
- [ ] **Compress**: Compress using lossy/lossless tools (e.g., Squoosh, Sharp) to keep file sizes under 150KB for large backgrounds and under 50KB for smaller images.
- [ ] **Convert**: Provide WebP and AVIF formats as primary assets, with PNG/JPEG fallback if necessary.
- [ ] **Source preservation**: Save the original uncompressed source file in a separate raw assets directory (do not commit huge raw assets to the main web source directory).
- [ ] **Dimensions**: Explicitly define `width` and `height` attributes on HTML `<img>` elements to prevent layout shifts.
- [ ] **Lazy-load**: Add `loading="lazy"` to all images located below the fold.
- [ ] **Alt text**: Provide descriptive, accessible alt text for screen readers unless the image is purely presentational (in which case, use `alt=""`).
- [ ] **Mobile crop**: Verify that the image center of interest remains visible and properly positioned on small screens (use CSS `object-position` or custom media queries).
- [ ] **Readability and contrast**: Check that text overlaid on the image remains legible. Use dark overlays (`rgba(0,0,0,0.5)`) or gradients where necessary to meet WCAG AA contrast standards.

## Final Rule

Do not use generated or sourced images without a clear purpose, proper performance optimization, and rigorous QA verification.
