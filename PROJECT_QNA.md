# PROJECT_QNA.md

## Purpose

Before building any new 3D website, the agent must interview the user.

Do not start coding until the answers are clear enough to create a project brief.

If the user says "skip questions", ask only the critical questions and proceed with assumptions.

---

# Required Q&A Session

## 1. Basic Identity

Ask:

1. What is the website name?
2. What is the website for?
3. Is it personal, brand, product, portfolio, agency, startup, event, game, course, or experiment?
4. Who is the target audience?
5. What should the visitor feel in the first 5 seconds?

---

## 2. Website Goal

Ask:

1. What is the main action visitors should take?
2. Is the site for selling, impressing, explaining, collecting leads, storytelling, or showcasing work?
3. What is the single most important message?
4. What should the user remember after leaving?

---

## 3. Style Direction

Ask:

1. Dark, light, or both?
2. Minimal, cinematic, editorial, futuristic, brutalist, luxury, playful, technical, or experimental?
3. Should it feel calm, intense, premium, mysterious, bold, soft, or energetic?
4. Any colors you want?
5. Any colors you hate?
6. Any fonts you like?
7. Any fonts you hate?
8. Should it feel more like a studio website, product launch, portfolio, game menu, documentary, or magazine?

---

## 4. References

Ask:

1. Give 3 to 5 websites you like.
2. What exactly do you like in each reference?
3. What do you dislike in each reference?
4. Are there any websites you do not want it to look like?
5. Should we copy the mood, animation style, layout structure, typography, or 3D behavior?

Important:
Never copy references directly.
Extract principles.

---

## 5. Content

Ask:

1. What sections do you want?
2. Do you already have text?
3. Should the agent write placeholder copy?
4. Should the tone be premium, simple, bold, technical, friendly, or dramatic?
5. Do you need CTA buttons?
6. Do you need contact form, pricing, testimonials, gallery, case studies, or resources?

---

## 6. 3D Direction

Ask:

1. Do you want a full 3D scene or subtle 3D elements?
2. Should the 3D object be abstract, product-based, environment-based, character-based, typography-based, or particle-based?
3. Should the 3D react to cursor movement?
4. Should it react to scroll?
5. Should it react to sound?
6. Should camera movement be calm, cinematic, locked, orbiting, or scroll-driven?
7. Should the 3D be realistic, stylized, wireframe, metallic, clay, glass, liquid, holographic, or minimal?

---

## 7. Motion Direction

Ask:

1. Should animations be smooth and minimal or bold and cinematic?
2. Should the site use scroll-triggered storytelling?
3. Should sections snap or flow normally?
4. Should text animate word-by-word, line-by-line, or as full blocks?
5. Should mouse interactions be subtle or strong?
6. Should the website have page transitions?
7. Should the loading screen be simple or cinematic?

---

## 8. Asset Direction

Ask:

1. Do you need generated images?
2. Do you need SVG illustrations?
3. Do you need video backgrounds?
4. Do you need 3D models?
5. Do you already have assets?
6. Should assets be abstract, realistic, editorial, futuristic, hand-drawn, technical, or cinematic?
7. Should the agent create prompts for assets first before implementation?

---

## 9. Technical Constraints

Ask:

1. Should the project use React + Vite?
2. Should it use TypeScript?
3. Should it use Tailwind?
4. Should it use shadcn/ui?
5. Is this for desktop-first, mobile-first, or responsive?
6. What device should performance target?
7. Is SEO important?
8. Is accessibility important?
9. Should the site be deployable on Vercel?
10. Are there storage or package-size limits?

---

## 10. Personal Preferences

Ask:

1. What do you always want in your websites?
2. What do you never want?
3. Do you prefer clean code or fastest possible output?
4. Do you prefer original custom components or library-based components?
5. Do you want the agent to be strict and criticize bad choices?
6. Do you want the agent to explain changes after each step?

---

## 11. Assets, Components, and Design Files

Ask:

1. Do you have a Figma file or UI design link?
2. Do you have a Spline scene link or export code?
3. Do you want a fully custom R3F scene or a Spline React embed?
4. Do you want generated images (Vite-ready WebP)?
5. Do you want custom SVG assets and animations?
6. Do you want video background loops or cinematic overlays?
7. Do you need external 3D models (.gltf / .glb)?
8. Should we use CC0/free model sources (like Poly Haven, ambientCG, Quaternius)?
9. Are there any assets, themes, or colors that must be strictly avoided (copyrighted brands, rips)?
10. Should we use shadcn/21st.dev components where suitable, or start from scratch?
11. Which parts of the website must be fully custom (e.g., Hero, transitions, shader effects)?

---

# Output After Q&A

After collecting answers, create this brief:

## Project Brief

- Website name:
- Type:
- Target audience:
- Primary goal:
- Desired feeling:
- Visual style:
- Color direction:
- Typography direction:
- Reference principles:
- Sections:
- Design Files / Links (Figma/Spline):
- 3D concept (Custom R3F vs Spline):
- Motion style:
- Asset needs (Models, images, videos, SVGs):
- Asset license & source policy:
- Tech stack:
- Component Reuse plan (shadcn vs custom):
- Performance target:
- Things to avoid:
- First milestone:

---

# If User Gives Weak Answers

If the user gives vague answers like "make it premium", ask follow-up questions.

Bad answer:
"Make it like Awwwards."

Good follow-up:
"Which part of Awwwards-style do you want: typography, animation, 3D, scroll storytelling, transitions, layout, or overall mood?"

---

# Default Assumptions If User Skips

If user refuses detailed Q&A, assume:

- React + Vite
- TypeScript
- Tailwind
- R3F + Drei
- GSAP for scroll and complex animation
- Motion for UI animation
- Lenis for smooth scroll
- shadcn/ui for standard components
- Desktop-first but responsive
- Premium editorial dark mode
- 3D should support the hero concept
- Performance should be safe for mid-range laptop

---

## Open Design Questions

Ask these when visual quality matters:

1. Do you want Open Design exploration before coding?
2. Should Open Design generate 2 or 3 design directions?
3. Should Open Design output be artifact preview only or code handoff?
4. What should Open Design explore?
   * hero section
   * landing page
   * typography system
   * layout system
   * motion direction
   * design system
   * visual identity
5. Do you already have references to guide Open Design?
6. Should Open Design use dark, light, or mixed direction?
7. What visual patterns must Open Design avoid?
8. Should generated code be treated as inspiration only?
9. Do you want approval before implementing any Open Design output?
10. Should Open Design use a specific skill or design system?

Default:
For premium hero sections, landing pages, and visual redesigns, use Open Design unless the user says to skip it.