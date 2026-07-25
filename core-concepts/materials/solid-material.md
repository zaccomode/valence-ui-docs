---
description: 'Last updated: 4.0.0'
---

# Solid Material

A filled block of its color, with a foreground picked to contrast against it. Use it for primary actions and anything that should carry the most visual weight on the screen.

## Usage

```tsx
import { Button, SolidMaterial } from "@valence-ui/core";

<Button material={new SolidMaterial({ color: "blue", elevation: 2 })}>
  Save changes
</Button>
```

## Props

_Extends [`MaterialProps`](README.md#shared-properties)._

<table data-full-width="true"><thead><tr><th width="190">Property</th><th width="220">Type</th><th>Description</th></tr></thead><tbody><tr><td>elevation</td><td><code>1 | 2 | 3 | 4 | 5</code></td><td>How far the material sits off the surface, expressed as a drop shadow. No shadow by default.</td></tr></tbody></table>

## Behaviour

* The background is `color` at full opacity.
* The foreground is chosen automatically: `black` on `white`/`brighterWhite`, `permaBlack` on `permaWhite`, `permaWhite` on `permaBlack`, and `white` on everything else.
* When `interactive`, the background darkens by 12% on hover and the elevation increases by one step (capped at 5).

## Setters

In addition to the [shared setters](README.md#materials-are-immutable):

<table data-full-width="true"><thead><tr><th width="330">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>setElevation(elevation: SolidMaterialElevation)</code></td><td>Returns a copy at a new elevation.</td></tr></tbody></table>

## Examples

A primary/secondary pair:

```tsx
<Flex gap={10}>
  <Button material={new SolidMaterial()}>Confirm</Button>
  <Button material={new AirMaterial({ color: "black" })}>Cancel</Button>
</Flex>
```

A destructive action:

```tsx
<Button material={new SolidMaterial({ color: "red" })}>
  Delete account
</Button>
```

## Changelog

* **4.0.0:** Introduced. Closest equivalent to the 3.x `filled` variant.
