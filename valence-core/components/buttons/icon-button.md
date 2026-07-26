---
description: 'Last updated: 4.0.0'
---

# Icon button

A simple button component designed to render icons. Uses the `Icon` component to apply styles to Tabler icons. `IconButton` components will be square by default.

## Usage

```tsx
import { IconButton, GlassMaterial } from "@valence-ui/core";
import { IconPlus } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <IconButton
            size="md"
            radius="sm"
            material={new GlassMaterial()}
        >
            <IconPlus />
        </IconButton>
    )
}
```

## Adding a tooltip

Use the `tooltip` prop to pass any text to be used as a tooltip around this button. The tooltip will inherit the button's color, regardless of its material.

This is effectively the same as wrapping the button in an uncontrolled `Tooltip` component. Additional props can be applied using the `tooltipProps` and `tooltipContentProps` props.

## Props

_Extends_ [_`PrimitiveButtonProps`_](primitive-button.md#props)_._

<table data-full-width="true"><thead><tr><th width="197">Property</th><th width="228">Type</th><th>Description</th></tr></thead><tbody><tr><td>tooltip</td><td><code>string</code></td><td>An optional tooltip to include. The tooltip will inherit the button's color.</td></tr><tr><td>tooltipProps</td><td><code>TooltipProps</code></td><td>Optional props to pass to the tooltip.</td></tr><tr><td>tooltipContentProps</td><td><code>TooltipContentProps</code></td><td>Additional props to pass to the content sub-component of the tooltip.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`.
