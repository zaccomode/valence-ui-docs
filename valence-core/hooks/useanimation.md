---
description: 'Last updated: 4.0.0'
---

# UseAnimation

Builds a set of [Motion](https://motion.dev/) variants from named animations, honouring the user's reduced-motion preference. This is the hook that powers the `animation` prop on Valence components.

See [Animations](../../core-concepts/animations.md) for the concepts.

## Usage

```tsx
import { useAnimation } from "@valence-ui/core";
import { motion } from "motion/react";

function MyComponent() {
  const animations = useAnimation({
    transitionAnimation: ["fade", "blur"],
    hoverAnimation: "grow",
    tapAnimation: "shrink",
  });

  return (
    <motion.div
      variants={animations}
      initial="initial"
      animate="animate"
      exit="exit"
      whileHover="whileHover"
      whileTap="whileTap"
    >
      Content
    </motion.div>
  );
}
```

## Parameters

Takes a single `AnimationProps` object.

<table data-full-width="true"><thead><tr><th width="220">Property</th><th width="300">Type</th><th>Description</th></tr></thead><tbody><tr><td>transitionAnimation</td><td><code>TransitionAnimation | TransitionAnimation[]</code></td><td>Played as the component enters and leaves the DOM.</td></tr><tr><td>hoverAnimation</td><td><code>HoverAnimation | HoverAnimation[]</code></td><td>Played while the component is hovered.</td></tr><tr><td>tapAnimation</td><td><code>TapAnimation | TapAnimation[]</code></td><td>Played while the component is pressed.</td></tr></tbody></table>

## Returns

`UseAnimationOutput` — an object of Motion `Variant`s, intended to be passed as `variants`.

<table data-full-width="true"><thead><tr><th width="200">Property</th><th>Description</th></tr></thead><tbody><tr><td>initial</td><td>The state the component enters from.</td></tr><tr><td>animate</td><td>The resting state.</td></tr><tr><td>exit</td><td>The state the component leaves to.</td></tr><tr><td>whileHover</td><td>The hovered state.</td></tr><tr><td>whileTap</td><td>The pressed state.</td></tr></tbody></table>

When the user prefers reduced motion, every one of these is an empty object.

## Animation values

<table data-full-width="true"><thead><tr><th width="180">Name</th><th width="140">Kind</th><th>Effect</th></tr></thead><tbody><tr><td><code>fade</code></td><td>transition</td><td>Opacity 0 → 1 → 0.</td></tr><tr><td><code>blur</code></td><td>transition</td><td>Blur 2px → 0 → 2px.</td></tr><tr><td><code>grow</code></td><td>transition</td><td>Scale 0.8 → 1 → 0.8.</td></tr><tr><td><code>slide-left</code></td><td>transition</td><td>Enters from the right, leaves to the left.</td></tr><tr><td><code>slide-right</code></td><td>transition</td><td>Enters from the left, leaves to the right.</td></tr><tr><td><code>slide-up</code></td><td>transition</td><td>Enters from below, leaves upwards.</td></tr><tr><td><code>slide-down</code></td><td>transition</td><td>Enters from above, leaves downwards.</td></tr><tr><td><code>grow</code></td><td>hover</td><td>Scales to 1.1.</td></tr><tr><td><code>raise</code></td><td>hover</td><td>Moves up 2px.</td></tr><tr><td><code>shrink</code></td><td>tap</td><td>Scales to 0.95.</td></tr><tr><td><code>bounce</code></td><td>tap</td><td>Moves down 2px.</td></tr></tbody></table>

Arrays are merged left to right, so `["fade", "grow"]` animates opacity and scale together.

## Changelog

* **4.0.0:** Introduced.
