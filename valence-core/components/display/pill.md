---
description: 'Last updated: 4.0.0'
---

# Pill

## Usage

```tsx
import { Pill } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Pill>
            I'm a pill!
        </Pill>
    )
}
```

### With remove button

```tsx
import { Pill } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Pill
            withRemoveButton
            onRemove={() => console.log("Oh no!")}
        >
            I'm a pill!
        </Pill>
    )
}
```

The appearance, behavior and icon of this button can be modified by passing in `removeButtonProps` or `removeButtonIcon` props.

***

## Props

_Extends `GenericLayoutProps` and_ [_`UnstyledButtonProps`_](../buttons/un-styled-button.md#props)_._

<table data-full-width="true"><thead><tr><th width="195">Property</th><th width="359">Type</th><th>Description</th></tr></thead><tbody><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material of this pill. Defaults to <code>theme.materials.button</code>.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>Size class of this pill. Defaults to theme default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>Border radius of this pill. Defaults to theme default.</td></tr><tr><td>withRemoveButton</td><td><code>boolean</code></td><td>Whether to include a remove button. <code>false</code> by default.</td></tr><tr><td>removeButtonIcon</td><td><code>ReactNode</code></td><td>Icon to use for the remove button. Defaults to <code>IconX</code>.</td></tr><tr><td>removeButtonProps</td><td><code>Omit&#x3C;</code><a href="../buttons/icon-button.md#props"><code>IconButtonProps</code></a><code>, "children"></code></td><td>Optional props to pass to the remove button.</td></tr><tr><td>onRemove</td><td><code>() => void</code></td><td>Callback to be called when the remove button is clicked.</td></tr><tr><td>textProps</td><td><code>Omit&#x3C;TextProps, "children"></code></td><td>Optional props to pass to the <code>Text</code> component.</td></tr><tr><td>children</td><td><code>string</code></td><td></td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`.
