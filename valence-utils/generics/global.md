---
description: 'Last updated: 4.0.0'
---

# Global

## ComponentSize

```tsx
type ComponentSize = "xs" | "sm" | "md" | "lg" | "xl";
```

## SizeClasses

```tsx
type SizeClasses<C> = {
  xs: C;
  sm: C;
  md: C;
  lg: C;
  xl: C
};
```

## GenericProps

<table data-full-width="true"><thead><tr><th width="128">Property</th><th width="166">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td><code>string</code></td><td>Used to specify a unique identifier for an element.</td></tr><tr><td>style</td><td><code>CSSObject</code></td><td>Used to specify custom styling for an element. Unlike the native HTML <code>style</code> attribute, this is passed into an Emotion <code>css</code> constructor before being added to the DOM, so it also accepts nested selectors such as <code>"&#x26;:hover"</code>.</td></tr><tr><td>tabIndex</td><td><code>number</code></td><td>Used to allow or prevent elements from being sequentially focusable. <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex">See more</a>.</td></tr><tr><td>children</td><td><code>ReactNode</code></td><td>Children nodes.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Removed `FillVariant`; see [Materials](../../core-concepts/materials/README.md). `GenericProps.style` is now an Emotion `CSSObject` rather than `CSSProperties`.
