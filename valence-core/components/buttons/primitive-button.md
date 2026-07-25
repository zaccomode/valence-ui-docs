---
description: 'Last updated: 4.0.0'
---

# Primitive button

{% hint style="danger" %}
This is a foundational component and should not be used by itself. Only use this component if you intend to make your own buttons.
{% endhint %}

## Usage

```tsx
import { PrimitiveButton, GlassMaterial } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <PrimitiveButton
            size="md"
            radius="sm"
            material={new GlassMaterial()}
        >
            My first button!
        </PrimitiveButton>
    )
}
```

## Props

_Extends_ [_`GenericButtonProps`_](../../generics/generic-button-props.md)_._

<table data-full-width="false"><thead><tr><th width="131.01472995090015">Property</th><th width="238">Type</th><th>Description</th></tr></thead><tbody><tr><td>animation</td><td><a href="../../../core-concepts/animations.md"><code>AnimationProps</code></a></td><td>Enter, hover and tap animations for this button. Automatically disabled if the user has reduced motion enabled on their device. Defaults to <code>{ hoverAnimation: "raise", tapAnimation: "bounce" }</code>.</td></tr><tr><td>float</td><td><a href="../../hooks/usefloating.md#props"><code>UseFloatingProps</code></a></td><td>Defines floating behavior for this button.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`, and `motion` with `animation`.

* **3.0.0:** Added the `float` property, allowing all buttons to float like a FAB.
