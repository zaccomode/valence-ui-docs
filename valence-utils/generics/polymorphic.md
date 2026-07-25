---
description: 'Last updated: 4.0.0'
---

# Polymorphic

## PolymorphicElementType

```tsx
type PolymorphicElementType = React.ElementType | "link";
```

## PolymorphicElementProps

<table data-full-width="true"><thead><tr><th width="132">Property</th><th width="269">Type</th><th>Description</th></tr></thead><tbody><tr><td>component</td><td><a href="polymorphic.md#polymorphicelementtype"><code>PolymorphicElementType</code></a></td><td>Sets the component type to render.</td></tr><tr><td>layout</td><td><code>boolean | "size" | "position" | "preserve-aspect"</code></td><td>Automatically animate the component to its new position when its layout changes. See <a href="../../core-concepts/animations.md">Animations</a> and <a href="https://motion.dev/docs/react-motion-component#layout">Motion's documentation</a>.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Added the `layout` prop for Motion layout animations.
