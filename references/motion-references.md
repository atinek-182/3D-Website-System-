# Motion References

## Purpose

This file stores animation, scroll, transition, cursor, and interaction references.

## Main Rule

Motion must support hierarchy, story, feedback, or atmosphere. If it does not, remove it.

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

## Animation Tool Decision

* CSS = simple hover/focus/transitions
* Motion = React UI transitions, gestures, layout animations, AnimatePresence
* GSAP = scroll-triggered timelines, SVG, canvas/WebGL sync, pinned sections
* Theatre.js = cinematic 3D keyframed timelines
* R3F useFrame = lightweight continuous 3D motion

## Motion Types To Track

* hero entrance
* text reveal
* image reveal
* SVG path draw
* cursor interaction
* hover interaction
* scroll-triggered section
* pinned scroll scene
* camera movement
* page transition
* loading animation
* video transition
* menu animation

## Motion Reference Entry Template

### Motion Reference Name

* URL:
* Video/screenshot:
* Date reviewed:
* Motion type:
* Useful for:

#### What I Like

* Timing:
* Easing:
* Stagger:
* Scroll behavior:
* Interaction:
* Camera movement:
* Text reveal:
* Transition style:

#### What I Do Not Like

* Too slow:
* Too flashy:
* Too heavy:
* Too distracting:
* Poor mobile behavior:

#### Reusable Motion Principle

* ...

#### Implementation Guess

* CSS / Motion / GSAP / Theatre.js / R3F:
* Notes:

#### QA Warning

* ...

## Good Motion Checklist

* guides attention
* feels intentional
* does not block reading
* has rhythm
* works on mobile
* can be reduced
* does not feel like template animation

## Bad Motion Checklist

* random movement
* endless floating everything
* overused fade-up
* overdone magnetic cursor
* scroll hijacking
* slow loaders
* motion that hides weak layout
