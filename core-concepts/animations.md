---
description: 'Last updated: 4.0.0'
---

# Animations

Valence 4.0.0 introduced a declarative animation system built on [Motion](https://motion.dev/). Rather than writing variants by hand, you name the effect you want and the library assembles the Motion variants for you — and silently drops them if the user has asked their operating system for reduced motion.

## The three kinds of animation

<table data-full-width="true"><thead><tr><th width="230">Type</th><th width="240">Values</th><th>When it plays</th></tr></thead><tbody><tr><td><code>TransitionAnimation</code></td><td><code>fade</code>, <code>blur</code>, <code>grow</code>, <code>slide-left</code>, <code>slide-right</code>, <code>slide-up</code>, <code>slide-down</code></td><td>As the component enters and leaves the DOM.</td></tr><tr><td><code>HoverAnimation</code></td><td><code>grow</code>, <code>raise</code></td><td>While the pointer is over the component.</td></tr><tr><td><code>TapAnimation</code></td><td><code>shrink</code>, <code>bounce</code></td><td>While the component is being pressed.</td></tr></tbody></table>

Each accepts a single value or an array, and arrays are merged:

```tsx
<Text animation={["fade", "blur", "slide-up"]}>Fades, blurs and slides in</Text>
```

## On display components

`Text`, `Icon` and `Loader` take an `animation` prop that is a `TransitionAnimation` (or an array of them):

```tsx
import { Text, Icon, Loader } from "@valence-ui/core";
import { IconHeart } from "@tabler/icons-react";

<Text animation={["fade", "blur"]}>{message}</Text>

<Icon animation="grow">
  <IconHeart />
</Icon>

<Loader animation={["blur", "fade", "grow"]} />
```

## On buttons

Buttons take an `animation` prop that is an **object**, because a button can animate on all three axes at once:

```tsx
import { Button } from "@valence-ui/core";

<Button
  animation={{
    transitionAnimation: ["fade", "blur", "grow"],
    hoverAnimation: "grow",
    tapAnimation: "bounce",
  }}
>
  Save changes
</Button>
```

Buttons default to `hoverAnimation: "raise"` and `tapAnimation: "bounce"`. Anything you pass is merged over those defaults, so you only need to name what you want to change.

## Reduced motion

`useAnimation` reads the user's `prefers-reduced-motion` setting through Motion's `useReducedMotion`. When reduced motion is requested, every variant it produces is empty — components still mount and unmount correctly, they just do so without movement. You do not need to check for it yourself.

## Layout animations

Polymorphic components accept Motion's `layout` prop, which animates a component to its new position whenever its layout changes:

```tsx
<Button layout>
  <motion.div layout>{label}</motion.div>
</Button>
```

Valid values are `true`, `"position"`, `"size"` and `"preserve-aspect"`. See [Motion's documentation](https://motion.dev/docs/react-motion-component#layout) for the trade-offs — layout animations work by animating scale, which can distort children, `boxShadow` and `borderRadius`.

## Using the hook directly

For your own components, call [`useAnimation`](../valence-core/hooks/useanimation.md) and spread the result into a Motion component:

```tsx
import { useAnimation } from "@valence-ui/core";
import { motion } from "motion/react";

function Card({ children }) {
  const animations = useAnimation({
    transitionAnimation: ["fade", "grow"],
    hoverAnimation: "raise",
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
      {children}
    </motion.div>
  );
}
```

To animate a component out, it must be inside Motion's `AnimatePresence`.

## Changelog

* **4.0.0:** Introduced. Replaces the `motion` prop and the `MotionBehaviourProps` type on most components.
