---
description: 'Last updated: 2.0.0 (22/01/2024)'
---

# 🎠 Valence Carousel

{% hint style="info" %}
This package is a Plugin package, meaning that it provides additional functionality that may not be needed by all projects. It should be used alongside `@valence-ui/core` and `@valence-ui/utils`. [Don't know what this means?](../../overview/getting-started.md)
{% endhint %}

The Valence Carousel is a custom horizontal carousel component designed for maximum usability in desktop and mobile environments. It allows a user to interact with it via the browser's native horizontal scroll, by clicking and dragging, and with the controls on either side. This component is based closely on the image carousel in the Instagram Threads app.

## Installation & usage

```bash
npm install @valence-ui/carousel
```

```tsx
import { Carousel, CarouselChildProps } from "@valence-ui/carousel";

function Demo() { 
  return (
    <Carousel>
      <CarouselChild 
        key={i}
      />
    </Carousel>
  )
}

function CarouselChild(props: CarouselChildProps) { 
  return ( 
    <div
      style={{
        backgroundColor: props.isActive ? "red" : undefined,
        outline: props.isNearest ? "1px solid red" : undefined,
      }}
    >
      Carousel Child
    </div>
  )
}
```

This example is an uncontrolled carousel. The Carousel package does not include a default child component, instead relying on a custom component that uses the `CarouselChildProps`. `CarouselChildProps` gives the `isActive` and `isNearest` props to the child, which can be used to influence style or behaviour.

The Carousel can also be used in a controlled manner, allowing higher-level components to know and/or control the active child:

```tsx
import { Carousel, CarouselChildProps } from "@valence-ui/carousel";
import { useState } from "react";

function Demo() { 

  const [activeChild, setActiveChild] = useState(0);

  return (
    <Carousel
      activeChild={activeChild}
      setActiveChild={setActiveChild}
    >
      <CarouselChild 
        key={i}
      />
    </Carousel>
  )
}

// etc.
```

***

## Props

_Extends_ [_`FlexProps`_](../../valence-core/components/layout/flex/#props)_._

<table data-full-width="true"><thead><tr><th width="212">Property</th><th width="278">Type</th><th>Description</th></tr></thead><tbody><tr><td>children (required)</td><td><code>ReactNode[]</code></td><td></td></tr><tr><td>allowDrag</td><td><code>boolean</code></td><td>Whether to allow the carousel content to be dragged on desktop. <code>true</code> on desktop devices by default.</td></tr><tr><td>showScrollbar</td><td><code>boolean</code></td><td>Whether to show the horizontal scrollbar. <code>false</code> by default.</td></tr><tr><td>snapToChildren</td><td><code>boolean</code></td><td>Whether to snap to the nearest child when no longer scrolling. <code>true</code> by default.</td></tr><tr><td>changeActiveOnScroll</td><td><code>boolean</code></td><td>Whether the active child should be changed during scroll. <code>true</code> by default.</td></tr><tr><td>contentProps</td><td><code>FlexProps</code></td><td>Optional props to pass to the content flex component.</td></tr><tr><td>activeChild</td><td><code>number</code></td><td>The active child of this carousel. For use when controlled.</td></tr><tr><td>setActiveChild</td><td><code>(index: number) => void</code></td><td>Sets the active child of this carousel. For use when controlled.</td></tr><tr><td>showControls</td><td><code>boolean</code></td><td>Whether to the carousel controls. <code>true</code> by default.</td></tr><tr><td>controlIcons</td><td><code>{ prev: ReactNode, next: ReactNode }</code></td><td>Optional overrides for the icons to use for the controls.</td></tr><tr><td>controlButtonProps</td><td><a href="../../valence-core/components/buttons/icon-button.md#props"><code>IconButtonProps</code></a></td><td>Optional props to pass to the control buttons.</td></tr></tbody></table>
