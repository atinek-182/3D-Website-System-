# Workflow: Start Premium 3D Site

Follow this step-by-step workflow to bootstrap any new premium 3D website.

---

## Phase 0: Project Setup & Init

1. **Verify Environment**:
   - Check CLI state: `agy plugin list` (confirm `superpowers` is active).
   - Check global config: `C:\Users\HP\.gemini\config\mcp_config.json` (ensure `context7`, `codegraph`, `playwright`, `github`, and `magic` are active).
   - Recommended runtime: Node 24 LTS.

2. **Bootstrap Project**:
   ```bash
   npx create-vite@latest my-3d-site -- --template react-ts
   cd my-3d-site
   npm install
   ```

3. **Initialize CodeGraph**:
   - Immediately run `codegraph init` in the project root to start tracking symbols and dependencies.

4. **Install Dependencies**:
   ```bash
   npm install three @react-three/fiber @react-three/drei gsap @gsap/react motion lenis lucide-react clsx tailwind-merge
   ```

---

## Phase 1: Planning & Design Brief

1. **User Interview (Q&A)**:
   - Run the questions from `PROJECT_QNA.md` (basic identity, goals, styling, references, 3D/motion expectations, asset guidelines).
   - *Strict Rule*: Do not write code before collecting responses.

2. **Establish Design Direction**:
   - Use the `frontend-design` skill to draft design tokens.
   - Outline colors (4-6 specific hex values), typography pairings (display, body, utility), spacing grids, and the signature creative element.

3. **Create Implementation Plan**:
   - Document files, component priorities, and milestones. Stop and wait for user approval.

---

## Phase 2: Core Components Foundation

1. **Initialize Styles**:
   - Create `src/styles/theme.css` with HSL tailored variables, typography configurations, and smooth transition utility classes.

2. **Bootstrap Basic UI Primitives**:
   - Initialize shadcn/ui: `npx shadcn@latest init`.
   - Install approved components (Button, Dialog, Card). Customize styles immediately.

3. **Establish Scene Canvas**:
   - Set up the canvas wrapper component: `src/components/scene/SceneCanvas.tsx`.
   - Configure OrbitControls, fallback loading screens, and responsive resize listeners.

---

## Phase 3: Animation & Scroll Integration

1. **GSAP Hook Bindings**:
   - Register plugins: `gsap.registerPlugin(ScrollTrigger)`.
   - Bind animations to components using `@gsap/react` `useGSAP` or React lifecycle hooks. Ensure a robust cleanup trigger exists.

2. **Lenis Integration**:
   - Initialize Lenis smooth scroll on desktop wrappers.
   - Sync GSAP ScrollTrigger updates with Lenis tick listeners:
     ```javascript
     lenis.on('scroll', ScrollTrigger.update);
     ```

---

## Phase 4: Verification & Browser QA

1. **Browser Testing (Playwright)**:
   - Execute Playwright MCP tests to take screenshots at desktop and mobile sizes.
   - Check scroll performance and check the browser console for runtime warnings.

2. **CodeGraph Gate**:
   - Run `codegraph explore` or query symbol connections to verify no dependency cycles or loose modules exist.
