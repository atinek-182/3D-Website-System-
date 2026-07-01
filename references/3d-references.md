# 3D And WebGL References

## Purpose

This file stores 3D, WebGL, R3F, shader, Spline, camera, lighting, and interaction references.

## Main Rule

Do not use 3D unless it supports concept, story, product, atmosphere, or interaction.

## Global Reference Rules

1. References are for extracting principles, not copying designs.
2. Do not copy layouts directly.
3. Do not copy brand identity.
4. Do not copy text, assets, or visuals.
5. Extract:
   * layout principle
   * typography principle
   * motion principle
   * interaction principle
   * 3D/canvas principle
   * color/lighting principle
   * performance lesson
6. Every reference must include:
   * what I like
   * what I dislike
   * what to adapt
   * what to avoid
7. If a reference is not analyzed, do not use it as a design rule.
8. If a reference is old or changed, mark it for re-review.

## 3D Types To Track

* abstract procedural geometry
* product model
* environmental scene
* particles
* shader surface
* 3D typography
* orbit/camera scene
* scroll-driven 3D
* cursor-reactive 3D
* Spline scene
* GLB/GLTF model scene

## 3D Reference Entry Template

### 3D Reference Name

* URL:
* Date reviewed:
* 3D type:
* Useful for:
* Performance impression:

#### What I Like

* Scene concept:
* Object design:
* Camera:
* Lighting:
* Materials:
* Interaction:
* Scroll behavior:
* Performance:
* Fallback/mobile:

#### What I Do Not Like

* Too heavy:
* Too decorative:
* Hard to read:
* Annoying camera:
* Weak mobile:
* Generic object:
* Overdone postprocessing:

#### Reusable 3D Principle

* ...

#### Implementation Direction

* R3F:
* Drei:
* Raw Three:
* Spline:
* Shader:
* GLB/GLTF:
* GSAP/Theatre.js:
* Notes:

## Camera Checklist

* Is the camera calm or cinematic?
* Does camera movement support the story?
* Does it avoid motion sickness?
* Does it keep UI readable?
* Does it work on mobile?

## Lighting Checklist

* Is there a clear light direction?
* Does lighting create depth?
* Are materials visible?
* Is bloom controlled?
* Does it feel premium or cheap?

## Performance Checklist

* low geometry cost
* optimized textures
* DPR cap
* no unnecessary postprocessing
* no huge model
* fallback
* mobile strategy

## Spline vs R3F Rule

Use Spline when:

* the scene is designed visually in Spline
* quick prototype is more important than deep control
* exported scene is light enough

Use R3F when:

* performance matters
* interaction needs code control
* camera/timeline needs precision
* scene must be reusable and maintainable
