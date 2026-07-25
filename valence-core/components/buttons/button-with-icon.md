---
description: 'Last updated: 4.0.0'
---

# Button with icon

A button used to display both an icon and text. If the button is loading, the icon will be replaced with a `Loader`. Like the [text button](text-button.md), this button also uses the `Text` component to render text.

## Usage

```tsx
import { ButtonWithIcon, GlassMaterial } from "@valence-ui/core";
import { IconPlus } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <ButtonWithIcon
            size="md"
            radius="sm"
            material={new GlassMaterial()}
            icon={<IconPlus />}
        >
            Text and an icon!
        </ButtonWithIcon>
    )
}
```

## Props

Extends [`TextButtonProps`](text-button.md#props).

<table data-full-width="true"><thead><tr><th width="159">Property</th><th width="198">Type</th><th>Description</th></tr></thead><tbody><tr><td>icon (required)</td><td><code>ReactNode</code></td><td>The icon to include with this button.</td></tr><tr><td>iconPosition</td><td><code>"left" | "right"</code></td><td>The position of the icon relative to the text. Defaults to <code>"left"</code>.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`.
