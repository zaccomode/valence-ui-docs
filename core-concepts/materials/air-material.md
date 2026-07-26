---
description: 'Last updated: 4.0.0'
---

# Air Material

Fully transparent, with no border and no background until you interact with it. Use it for tertiary actions, icon buttons in toolbars, and list or dropdown items that should only reveal themselves on hover.

## Usage

```tsx
import { IconButton, AirMaterial } from "@valence-ui/core";
import { IconX } from "@tabler/icons-react";

<IconButton material={new AirMaterial({ color: "black" })}>
  <IconX />
</IconButton>
```

## Props

_Extends [`MaterialProps`](README.md#shared-properties)._

<table data-full-width="true"><thead><tr><th width="190">Property</th><th width="220">Type</th><th>Description</th></tr></thead><tbody><tr><td>backgroundColor</td><td><code>string</code></td><td>The color used for the hover and focus tint. Defaults to <code>color</code>.</td></tr></tbody></table>

## Behaviour

* The background is `transparent` and there is no border at rest.
* The foreground is `color` at full opacity.
* When `interactive`, a `backgroundColor` tint at **weak** opacity appears on hover and focus, and focus adds a 1px solid border in `color`.

## Setters

In addition to the [shared setters](README.md#materials-are-immutable):

<table data-full-width="true"><thead><tr><th width="330">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>setBackgroundColor(color: string)</code></td><td>Returns a copy with a new hover tint.</td></tr></tbody></table>

## Examples

A close button that stays out of the way:

```tsx
<IconButton
  onClick={disclosure.close}
  material={new AirMaterial({ color: "black" })}
>
  <IconX />
</IconButton>
```

A row of list items that light up individually:

```tsx
{options.map((option) => (
  <ButtonWithIcon
    key={option.value}
    icon={option.icon}
    material={new AirMaterial({ color: "black" })}
    width="100%"
  >
    {option.label}
  </ButtonWithIcon>
))}
```

## Changelog

* **4.0.0:** Introduced. Closest equivalent to the 3.x `subtle` variant.
