# Rejected Libraries & Tooling

This document catalogs tools, libraries, and asset packages that are strictly rejected for use in premium 3D websites.

---

## 1. Unverified Spline MCPs
- **Reason**: Vague community-contributed Spline MCPs are unstable, unmaintained, and do not utilize stable public REST APIs for dynamic scenes.
- **Alternative**: Use official Spline packages (`@splinetool/react-spline` or `@splinetool/runtime`) or export scenes as optimized glTF/glb assets.

---

## 2. Bloated Animations / Pre-packaged Effects Libraries
- **Reason**: Libraries that bundle dozens of non-customizable Awwwards effects or complex layout scroll wrappers often load hundreds of lines of unused JavaScript, conflict with GSAP/Motion, block event handlers, and break accessibility.
- **Alternative**: GSAP, Motion (`motion/react`), and custom CSS transitions.

---

## 3. Direct DOM-Manipulating Packages
- **Reason**: Packages that directly hook into browser DOM trees without React awareness (such as old jQuery plugins, vanilla sliders, or un-encapsulated parallax utilities) create memory leaks, crash on hot reloads, and break React hydration.
- **Alternative**: Standard React hooks (`useEffect`, `useRef`) combined with GSAP or Motion scoping.

---

## 4. Heavy, Non-optimized Model Libraries
- **Reason**: Pre-built model loaders that query external, un-cached servers or serve uncompressed multi-megabyte glTF/OBJ models degrade page load performance and increase mobile bounce rates.
- **Alternative**: Downscaled, Draco-compressed GLB models served from local directories (e.g. `/public/models/`).

---

## 5. Proprietary / Unlicensed Asset Registries
- **Reason**: Downloading models from unofficial sources with missing license metadata violates intellectual property rules.
- **Alternative**: CC0 registries (ambientCG, Poly Haven, Quaternius).

---

## 6. Legacy Framer Motion
- **Reason**: Avoid importing `framer-motion` package.
- **Alternative**: Use the modern `motion` package imported from `motion/react` for lighter bundles and modern React compiler compatibility.
