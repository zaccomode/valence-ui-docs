---
description: 'Last updated: 4.0.0'
---

# Input container

{% hint style="danger" %}
This is a foundational component and is not designed to be used by itself. Only use this if you intend to make your own inputs.
{% endhint %}

The Input container provides the wrapper styling around the [Text](text-input.md), [Text area](text-area.md), [Number](number-input.md) and [Select](select-input.md) inputs.&#x20;

## Usage

```tsx
import { InputContainer } from "@valence-ui/core";

function MyComponent() { 

    return ( 
        <InputContainer 
            // For brevity, the suggested props
            // are not included.
        >
            // Your sub-component here.
            // It should have little to no styling,
            // as this is handled by the InputContainer.
        </InputContainer>
    )
}
```

## Props

Extends `GenericLayoutProps`, `MouseClickEvents`, `MouseEvents` and `PointerEvents`.

<table data-full-width="true"><thead><tr><th width="211">Property</th><th width="170">Type</th><th>Description</th></tr></thead><tbody><tr><td>icon</td><td><code>ReactNode</code></td><td>An icon to display at the left side of this input.</td></tr><tr><td>button</td><td><code>ReactNode</code></td><td>A button to display to the right of this input.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>Sets the size class. Defaults to theme default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>Sets the radius size class. Defaults to theme default.</td></tr><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material of this input. Defaults to <code>theme.materials.input</code>.</td></tr><tr><td>grow</td><td><code>boolean</code></td><td>Shorthand for <code>flex-grow = 1</code>.</td></tr><tr><td>disabled</td><td><code>boolean</code></td><td>Whether this input is disabled.</td></tr><tr><td>required</td><td><code>boolean</code></td><td>Whether this input is required.</td></tr><tr><td>loading</td><td><code>boolean</code></td><td>Whether this input is loading.</td></tr><tr><td>inputRef</td><td><code>any</code></td><td>A <code>ref</code> of the input component.</td></tr><tr><td>iconContainerStyle</td><td><code>CSSProperties</code></td><td>Optional styles for the icon container component.</td></tr><tr><td>requireIndicatorStyle</td><td><code>CSSProperties</code></td><td>Optional styles for the require indicator component.</td></tr><tr><td>buttonContainerStyle</td><td><code>CSSProperties</code></td><td>Optional styles for the button container component.</td></tr><tr><td>iconProps</td><td><a href="../display/icon.md#props"><code>IconProps</code></a></td><td>Optional props to apply to the icon component, if one is rendered.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`. Added `iconProps`.
