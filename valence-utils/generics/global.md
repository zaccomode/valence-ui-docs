---
description: 'Last updated: 2.0.0 (22/01/2024)'
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

## FillVariant

```tsx
type FillVariant = "subtle" | "outlined" | "paper" | "light" | "filled";
```

## GenericProps

<table data-full-width="true"><thead><tr><th width="128">Property</th><th width="166">Type</th><th>Description</th></tr></thead><tbody><tr><td>id</td><td><code>string</code></td><td>Used to specify a unique identifier for an element.</td></tr><tr><td>style</td><td><code>CSSProperties</code></td><td>Used to specify custom styling for an element. Unlike the native HTML <code>style</code> attribute, this will be passed into an Emotion <code>css</code> constructor before being added to the DOM.</td></tr><tr><td>tabIndex</td><td><code>number</code></td><td>Used to allow or prevent elements from being sequentially focusable. <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex">See more</a>.</td></tr><tr><td>children</td><td><code>ReactNode</code></td><td>Children nodes.</td></tr></tbody></table>
