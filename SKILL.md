---
name: awwwards-scroll-skills
description: Build Awwwards-level scroll animation websites using GSAP ScrollTrigger, Lenis, Motion for React, React Three Fiber/WebGL, Barba page transitions, kinetic typography, Scrollama scrollytelling, and Codrops-inspired interaction patterns. Use when creating, improving, debugging, or planning premium scroll-driven websites, landing pages, portfolios, editorial pages, product pages, WebGL scenes, animated navigation, or advanced frontend motion systems.
---

# Awwwards Scroll Skills

## Core Rule

Use this skill when the user wants high-end scroll animation for websites. Treat animation as choreography that supports hierarchy, pacing, content comprehension, and brand feeling. Avoid adding effects just because a library can do them.

## Engine Selection

Choose the smallest engine that can deliver the desired interaction:

- GSAP ScrollTrigger: use for pinned sections, scrubbed timelines, layout morphs, complex choreography, SVG/canvas/WebGL sync, and production-grade scroll scenes.
- Lenis: use as the smooth scroll transport layer when a premium inertial feel is needed. Pair with GSAP, Motion, or WebGL; do not treat Lenis as the animation system.
- Motion for React: use for React/Next.js scroll-linked UI, parallax, viewport reveals, progress bars, sticky header behavior, and composable motion values.
- React Three Fiber and Drei: use when WebGL/3D is part of the primary experience. Prefer one persistent canvas and keep semantic content in the DOM.
- r3f-scroll-rig: use when DOM elements need matching WebGL planes or objects during scroll.
- Barba.js: use for SPA-like page transitions on multi-page sites, including route lifecycle cleanup.
- SplitType, Splitting.js, or GSAP SplitText: use for kinetic typography, line masks, word reveals, and short character effects.
- Scrollama: use for narrative scrollytelling where text steps trigger sticky graphics, charts, maps, or canvas states.
- Codrops/Tympanus references: use for creative recipes, then rebuild them in the target codebase and harden for production.

## Build Workflow

1. Map the page into scenes before coding: trigger, start/end positions, pinned duration, scrub behavior, animated properties, responsive variants, and cleanup.
2. Reserve stable dimensions for images, videos, canvas, grids, and pinned sections.
3. Animate compositor-friendly properties first: transform, opacity, clip-path, filter, SVG attributes, and shader uniforms.
4. Add reduced-motion behavior before finishing. Replace heavy scrubbed/pinned scenes with simple visible states.
5. For React/Next.js, scope animation setup and cleanup to components. Kill ScrollTriggers and revert split text on unmount or route changes.
6. When smooth scrolling is active, run one RAF loop and explicitly sync it with ScrollTrigger or other animation systems.
7. Verify desktop and mobile states with screenshots or browser inspection. Confirm no blank canvas, broken pin, overlapping text, or unreadable scroll state.

## GSAP ScrollTrigger Pattern

Use GSAP for deliberate choreography:

```js
const tl = gsap.timeline({
  scrollTrigger: {
    trigger: section,
    start: "top top",
    end: "+=250%",
    scrub: 1,
    pin: true,
    anticipatePin: 1
  }
})

tl.from(title, { yPercent: 60, opacity: 0 })
  .to(media, { scale: 1.12, clipPath: "inset(0% 0% 0% 0%)" }, 0)
  .from(items, { y: 48, opacity: 0, stagger: 0.08 }, 0.25)
```

Use `gsap.matchMedia()` for responsive variants. Remove `markers: true` before shipping.

## Lenis Integration Pattern

Use one RAF owner:

```js
const lenis = new Lenis({ autoRaf: false, anchors: true })

lenis.on("scroll", ScrollTrigger.update)

gsap.ticker.add((time) => {
  lenis.raf(time * 1000)
})

gsap.ticker.lagSmoothing(0)
```

Stop Lenis for blocking modals and restart it on close. Mark nested scroll areas with the relevant Lenis prevention attributes.

## React Motion Pattern

Keep scroll values as MotionValues. Do not set React state on every scroll tick unless detecting coarse state changes:

```jsx
const ref = useRef(null)
const { scrollYProgress } = useScroll({
  target: ref,
  offset: ["start end", "end start"]
})
const y = useTransform(scrollYProgress, [0, 1], ["-12%", "12%"])

return <motion.section ref={ref} style={{ y }}>...</motion.section>
```

Use `whileInView` for simple one-shot reveals and `useReducedMotion()` for accessibility.

## WebGL and R3F Pattern

Use one persistent canvas for complex pages. Keep DOM for text, links, layout, and accessibility; sync WebGL objects to DOM proxies when needed.

Performance rules:

- Limit postprocessing passes.
- Compress GLB assets and textures.
- Lower DPR and simplify effects on mobile.
- Drive shader uniforms or camera values from one scroll source.
- Verify the canvas is nonblank, correctly framed, and not covering readable content.

## Kinetic Typography Pattern

Split text only when per-line, per-word, or per-character motion is essential. Prefer lines and words for editorial readability; use character splits sparingly.

```js
const split = new SplitType("[data-split]", {
  types: "lines, words",
  lineClass: "line",
  wordClass: "word"
})

gsap.from(split.words, {
  yPercent: 110,
  opacity: 0,
  stagger: 0.035,
  duration: 0.8,
  ease: "power3.out",
  scrollTrigger: {
    trigger: "[data-split]",
    start: "top 75%"
  }
})
```

Revert split text on unmount or route change. Avoid long character-by-character body copy.

## Scrollytelling Pattern

Use native `position: sticky` for the visual and Scrollama or IntersectionObserver for step events. Keep callbacks cheap and deterministic when scrolling upward.

```js
scrollama()
  .setup({ step: ".step", offset: 0.55, progress: true })
  .onStepEnter(({ element, index, direction }) => {
    updateGraphic(element.dataset.step, { index, direction })
  })
  .onStepProgress(({ element, progress }) => {
    updateProgress(element.dataset.step, progress)
  })
```

On mobile, prefer stacked visuals near their text or a simpler overlay pattern.

## Page Transition Pattern

Use Barba for multi-page sites that should feel continuous. Clean up page-local effects before replacing containers:

```js
function cleanupPage() {
  ScrollTrigger.getAll().forEach((trigger) => trigger.kill())
}

function initPage() {
  ScrollTrigger.refresh()
}
```

Restore focus and scroll position intentionally after transitions. Keep content usable if JavaScript fails.

## Production Checklist

Before completing the task, verify:

- The animation has a reason tied to content or brand.
- No scroll scene creates layout shift or unreadable overlap.
- Pinned sections enter and release correctly on desktop and mobile.
- Smooth scroll does not break anchors, modals, iframes, or nested scroll containers.
- Reduced-motion users receive a simpler experience.
- Route changes clean up triggers, RAF loops, split text, observers, and listeners.
- The site remains responsive during fast wheel and touch scrolling.

## References

Use these source projects when implementation details are needed:

- GSAP: https://github.com/greensock/GSAP
- Lenis: https://github.com/darkroomengineering/lenis
- Motion: https://github.com/motiondivision/motion
- React Three Fiber: https://github.com/pmndrs/react-three-fiber
- Drei: https://github.com/pmndrs/drei
- r3f-scroll-rig: https://github.com/14islands/r3f-scroll-rig
- Barba.js: https://github.com/barbajs/barba
- SplitType: https://github.com/lukePeavey/SplitType
- Splitting.js: https://github.com/shshaw/Splitting
- Scrollama: https://github.com/russellsamora/scrollama
- Codrops: https://github.com/codrops
