---
name: codrops-scroll-patterns
description: Adapt Codrops-style creative scroll animation recipes into production-ready websites, including image grid scroll effects, on-scroll typography, layout morphs, 3D carousels, Lenis + GSAP ScrollTrigger patterns, and Awwwards-level interaction direction. Use when Codex is asked for inspiration, references, recipes, or implementation patterns for premium scroll animations, especially when the user mentions Codrops, Tympanus, Awwwards, creative portfolios, editorial motion, or experimental frontend effects.
---

# Codrops Scroll Patterns

## Core Approach

Use Codrops demos as pattern references, not copy-paste products. Extract the interaction idea, rebuild it in the target app's framework, and harden it for responsiveness, accessibility, performance, and maintainability.

Primary sources:
- Codrops GitHub: https://github.com/codrops
- ScrollBasedLayoutAnimations: https://github.com/codrops/ScrollBasedLayoutAnimations
- OnScrollTypographyAnimations: https://github.com/codrops/OnScrollTypographyAnimations
- ScrollAnimationsGrid: https://github.com/codrops/ScrollAnimationsGrid
- ElasticGridScroll: https://github.com/codrops/ElasticGridScroll
- 3DCarousel: https://github.com/codrops/3DCarousel

## Pattern Selection

Use this mapping:

- Image gallery or portfolio index: use grid scroll, column drift, parallax depth, and masked reveal patterns.
- Editorial landing page: use typography reveals, line masks, sticky image/text rhythm, and scroll-triggered color shifts.
- Product/brand page: use pinned sections, image-to-layout morphs, and controlled page transitions.
- Experimental visual page: use WebGL image planes, shader distortion, 3D carousel, or DOM/WebGL synchronization.
- Navigation-heavy site: use Barba transitions and title/image handoffs.

## Adaptation Workflow

1. Identify the core illusion: pinning, masking, stagger, perspective, scroll speed mismatch, layout morph, or texture distortion.
2. Decide the engine: GSAP ScrollTrigger for choreography, Lenis for smooth scroll, Motion for React-native light effects, R3F for WebGL/3D.
3. Rebuild the DOM/CSS structure in the target project style.
4. Keep image dimensions stable with aspect ratios and responsive sources.
5. Add reduced-motion and mobile variants before calling the work done.
6. Verify screenshots and scrolling in desktop/mobile viewports.

## Recipes

Grid column drift:
```js
gsap.utils.toArray("[data-column]").forEach((column, index) => {
  gsap.to(column, {
    yPercent: index % 2 ? -12 : 12,
    ease: "none",
    scrollTrigger: {
      trigger: grid,
      start: "top bottom",
      end: "bottom top",
      scrub: true
    }
  })
})
```

Layout morph:
```js
const state = Flip.getState("[data-flip]")
container.classList.toggle("is-expanded")
Flip.from(state, {
  duration: 0.9,
  ease: "power3.inOut",
  absolute: true,
  scrollTrigger: {
    trigger: container,
    start: "top center"
  }
})
```

Typography reveal:
Use SplitType or GSAP SplitText, wrap lines in overflow-hidden containers, then animate y/opacity with stagger. Avoid long char-by-char reveals for body copy.

## Production Hardening

- Replace demo assets with optimized, licensed assets.
- Remove debug UI and markers.
- Avoid one-off global selectors that break when content changes.
- Encapsulate page scenes in setup/cleanup functions.
- Do not ship effects that require the user to scroll huge empty distances without content value.
- Test real mobile touch behavior, not only desktop responsive mode.

## Taste Rules

Premium scroll work should feel intentional, not merely animated. Use fewer stronger moments. Make scroll states serve hierarchy, pacing, and content comprehension.
