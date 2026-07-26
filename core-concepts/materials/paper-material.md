---
description: 'Last updated: 4.0.0'
---

# Paper Material

An opaque surface with a hairline border and an optional elevation shadow. This is the default material for cards, and the right choice for anything that should read as a sheet of paper laid on the page — panels, dropdowns, modals.

## Usage

```tsx
import { Card, PaperMaterial } from "@valence-ui/core";

<Card material={new PaperMaterial({ elevation: 3 })}>
  <Card.Section>Contents</Card.Section>
</Card>
```

## Props

_Extends [`MaterialProps`](README.md#shared-properties)._

<table data-full-width="true"><thead><tr><th width="190">Property</th><th width="220">Type</th><th>Description</th></tr></thead><tbody><tr><td>backgroundColor</td><td><code>string</code></td><td>The surface color. Defaults to <code>"brighterWhite"</code>, which flips to <code>"darkerBlack"</code> in dark mode.</td></tr><tr><td>elevation</td><td><code>1 | 2 | 3 | 4 | 5</code></td><td>How far the surface sits off the page, expressed as a drop shadow. No shadow by default.</td></tr><tr><td>blur</td><td><code>"weak" | "strong" | number</code></td><td>The backdrop blur behind the surface. Setting this also drops the background to ~63% opacity so the blur is visible. <code>"weak"</code> is 5px, <code>"strong"</code> is 15px, and a number is used directly as pixels.</td></tr></tbody></table>

{% hint style="info" %}
Unlike the other materials, `color` here defaults to `"black"` rather than the theme's primary color, because on Paper `color` is the **text and border** color rather than a fill.
{% endhint %}

## Behaviour

* The border is `color` at **weak** opacity, or **medium** at elevation 3 and above.
* When `interactive`, the elevation increases by one step on hover (capped at 5) and the border moves to **strong** opacity.
* On focus, the border becomes `color` at full opacity.

## Setters

In addition to the [shared setters](README.md#materials-are-immutable):

<table data-full-width="true"><thead><tr><th width="330">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>setBackgroundColor(color: string)</code></td><td>Returns a copy with a new surface color.</td></tr><tr><td><code>setElevation(elevation: PaperMaterialElevation)</code></td><td>Returns a copy at a new elevation.</td></tr></tbody></table>

## Examples

A floating panel over content:

```tsx
<Flex
  material={new PaperMaterial({ blur: "strong", elevation: 4 })}
  direction="column"
  padding={15}
  radius="md"
>
  <Text>Floats above the page</Text>
</Flex>
```

A flat, bordered container:

```tsx
<Flex material={new PaperMaterial()} padding={15} radius="sm">
  <Text>No shadow, just a border</Text>
</Flex>
```

## Changelog

* **4.0.0:** Introduced. Closest equivalent to the 3.x `paper` variant.
