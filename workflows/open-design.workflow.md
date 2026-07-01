---
title: Open Design Exploration Workflow
description: Uses Open Design to create and critique visual directions before final implementation.
---

# Open Design Exploration Workflow

## Purpose

Use Open Design as a design lab before coding visually important website work.

Open Design creates design options.
The Antigravity system builds the final production implementation.

## Step 1 — Confirm Need

Use Open Design when:
* visual direction is important
* user wants premium design
* hero/landing page needs strong identity
* references need to become design principles
* multiple options would help
* layout/typography/motion needs exploration
* design system exploration is useful

Skip Open Design when:
* task is a bug fix
* task is technical only
* design is already locked
* user asks to skip design exploration
* change is minor

## Step 2 — Confirm Open Design Availability

Check:
* open-design MCP is available
* desktop app is running if active context is needed
* list_skills works
* list_plugins or design systems listing works
* no active project context is acceptable if generating from a fresh brief

If Open Design context is inactive:
* continue only if working from a written brief
* otherwise ask user to open/select the project in Open Design

## Step 3 — Load Local System Context

Read:
* AGENTS.md
* PROJECT_QNA.md
* STACK_AND_TOOLS.md
* COMPONENT_LIBRARY_POLICY.md
* WORKFLOWS.md
* QA_AND_REVIEW.md
* references/ if available
* assets-briefs/ if assets are needed

## Step 4 — Build Open Design Brief

Create a compact design brief:
* website name:
* audience:
* purpose:
* core message:
* desired feeling:
* visual style:
* typography direction:
* motion direction:
* 3D direction:
* illustration/SVG direction:
* color direction:
* references:
* must avoid:
* output type:
* number of options:
* implementation stack:
* asset restrictions:
* performance constraints:

## Step 5 — Select Skill / Design System

Before running Open Design, choose the most suitable available skill or design system.

Selection rules:
* use frontend/landing-page/design-system skills for websites
* use color/layout/typography skills for visual exploration
* do not use random novelty skills unless the project needs them
* do not use unrelated skills just because they exist
* explain why the selected skill/design system fits

## Step 6 — Generate Design Options

Use Open Design to generate 2–3 distinct design directions.

Do not generate 10 random options.

Each option must include:
* concept name
* layout direction
* typography direction
* color direction
* motion direction
* 3D/visual asset direction
* component style
* strengths
* weaknesses
* implementation risk

## Step 7 — Critique The Options

Use frontend-design skill and QA_AND_REVIEW.md.

Score each option:
* originality:
* typography:
* layout:
* motion potential:
* 3D compatibility:
* readability:
* implementation feasibility:
* performance safety:
* premium feel:

Reject options that feel:
* generic AI design
* template-like
* overdecorated
* unreadable
* too heavy
* too close to references
* visually impressive but hard to implement cleanly

## Step 8 — User Selection Gate

Stop and ask user to choose:
* Option A
* Option B
* Option C
* mix of options
* regenerate direction
* skip Open Design output

Do not implement before user approval.

## Step 9 — Extract Principles

From the chosen option, extract:
* layout rules
* type scale
* color tokens
* spacing rules
* motion rules
* 3D scene requirements
* asset requirements
* component requirements
* Tailwind implementation notes
* what to avoid

## Step 10 — Implementation Handoff

Convert chosen design into an implementation plan:
* React/Vite/TypeScript
* Tailwind by default
* CSS Modules only for complex visual/canvas systems
* R3F/Drei if 3D is needed
* Motion for UI transitions
* GSAP for scroll/canvas/SVG/WebGL timelines
* shadcn/Radix for primitives
* Playwright QA after implementation
* CodeGraph review when architecture grows

## Final Rule

Design first.
Code second.
Open Design output is direction, not final production truth.
