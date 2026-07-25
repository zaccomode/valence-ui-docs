---
description: 'Last updated: 4.0.0'
---

# Glass Material

A translucent tint of its color, optionally blurred. This is the default material for buttons and inputs, and the one to reach for when a control should read as part of the surface behind it rather than sitting on top of it.

## Usage

```tsx
import { Button, GlassMaterial } from "@valence-ui/core";

<Button material={new GlassMaterial({ color: "blue", blur: "weak" })}>
  Save changes
</Button>
```

## Props

_Extends [`MaterialProps`](README.md#shared-properties)._

<table data-full-width="true"><thead><tr><th width="190">Property</th><th width="220">Type</th><th>Description</th></tr></thead><tbody><tr><td>backgroundColor</td><td><code>string</code></td><td>The color used for the tinted background. Defaults to <code>color</code>, letting the background and foreground diverge when you need them to.</td></tr><tr><td>blur</td><td><code>"weak" | "strong" | number</code></td><td>The backdrop blur behind the material. <code>"weak"</code> is 5px, <code>"strong"</code> is 15px, and a number is used directly as pixels. No blur by default.</td></tr></tbody></table>

## Behaviour

* The background is `color` at **weak** opacity; the foreground is `color` at full opacity.
* When `interactive`, the background moves to **medium** opacity on hover, and a 1px solid border in `color` appears on focus.
* Placeholders in descendants are rendered in `color` at **strong** opacity.

## Setters

In addition to the [shared setters](README.md#materials-are-immutable):

<table data-full-width="true"><thead><tr><th width="330">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>setBackgroundColor(color: string)</code></td><td>Returns a copy with a new background color.</td></tr><tr><td><code>setBlur(blur: GlassMaterialBlur)</code></td><td>Returns a copy with a new blur strength.</td></tr></tbody></table>

## Examples

A button whose text and tint differ:

```tsx
<Button material={new GlassMaterial({ color: "red", backgroundColor: "black" })}>
  Delete
</Button>
```

A strongly blurred surface, useful over imagery:

```tsx
<Flex material={new GlassMaterial({ blur: "strong" })} padding={20}>
  <Text>Sits over the background</Text>
</Flex>
```

## Changelog

* **4.0.0:** Introduced. Closest equivalent to the 3.x `light` variant.
