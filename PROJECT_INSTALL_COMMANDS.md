# Project Installation Commands

This document contains standard commands for bootstrapping a premium 3D React website using Vite, TypeScript, and Tailwind CSS.

## 1. Node Version Warning

> [!WARNING]
> **Recommended project Node version: Node 24 LTS**
> 
> *Reason*: Use Node 24 LTS for stable React/Vite/Three.js work unless the package ecosystem confirms Node 26 compatibility. The global environment currently runs Node `v26.1.0`. We recommend configuring a local Node version manager (e.g. `nvm use 24` or `nvm install 24`).

---

## 2. Bootstrapping a New React + TS Project

```bash
# Create project using Vite template
npm create vite@latest my-3d-site -- --template react-ts
cd my-3d-site
npm install
```

---

## 3. Installing Core Libraries

Install the baseline libraries required for premium 3D animations, styling, and icons:

```bash
# Core 3D and Animation Packages
npm install three @react-three/fiber @react-three/drei gsap @gsap/react motion lenis lucide-react clsx tailwind-merge
```

---

## 4. Optional / Specialized Packages

Only install these if specifically requested in the approved project brief:

### Rapier (Physics Engine) & Postprocessing
```bash
npm install @react-three/postprocessing leva maath @react-three/rapier
```

### Cinematic Timelines (Theatre.js)
```bash
npm install @theatre/core@latest @theatre/studio@latest @theatre/r3f@latest
```

### Spline Integration
```bash
npm install @splinetool/react-spline @splinetool/runtime
```

### glTF Model Optimization Utilities
```bash
# Run model to component parser locally
npx gltfjsx public/models/model.glb
```

---

## 5. UI Component Primitives (shadcn/ui)

Use `shadcn` for generic structural primitives, and style them to match the project aesthetics:

```bash
# Initialize shadcn in the project directory
npx shadcn@latest init

# Add approved UI primitives
npx shadcn@latest add button card dialog sheet tabs accordion tooltip input label textarea badge separator navigation-menu command
```

---

## 6. Integration Rules

- **Use Context7 First**: Before using R3F hooks, Drei loaders, GSAP scroll triggers, or Motion spring configurations, query documentation to ensure exact syntax is followed.
- **Tidy Imports**: Standardize UI animation imports from `motion/react` rather than the old `framer-motion` namespace.
- **CodeGraph Check**: Immediately after creating the directory, initialize indexing by running `codegraph init` so CodeGraph can start tracking codebase connections.
- **Log Reused Code**: Log any customized templates from 21st.dev in `custom-components-log.md`.
- **Log External Assets**: For every downloaded 3D model, image, or video loop, log attributes in `assets-briefs/asset-license-log.md`.
