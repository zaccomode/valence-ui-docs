---
description: 'Last updated: 4.0.0'
---

# UseColors

{% hint style="info" %}
This hook forms part of the [Color utility system](../../core-concepts/color/). For more information about how this system works, see [Color](../../core-concepts/color/).
{% endhint %}

`useColors` is a hook that allows the usage of Valence colors in any component. All components must be a child of the `ValenceProvider` to function correctly.

## Usage

```tsx
import { useColors, Button } from "@valence-ui/core";
import { CSSProperties } from "react";

function MyComponent() { 
    const { getHex } = useColors();

    const buttonStyle: CSSProperties = { 
        color: getHex("blue", "weak"),
    }
    
    return ( 
        <Button
            style={buttonStyle}
        >
            I'm a button!
        </Button>
    )
}
```

{% hint style="warning" %}
`getBgHex`, `getBorderHex` and `getFgHex` were removed in 4.0.0. They existed to resolve a `FillVariant` into a concrete color, and that job now belongs to [materials](../../core-concepts/materials/README.md).
{% endhint %}

## Return type

<table data-full-width="true"><thead><tr><th width="135">Attribute</th><th width="405">Type</th><th>Description</th></tr></thead><tbody><tr><td>getSwatch</td><td><code>(key: string | undefined):</code> <a href="../../core-concepts/color/color-types.md#swatchopacity"><code>Swatch</code></a> <code>| undefined</code></td><td>Gets the swatch for the given color key. If the color does not exist, this will return <code>undefined</code>.</td></tr><tr><td>getHex</td><td><code>(key: string | undefined, opacity?:</code> <a href="../../core-concepts/color/color-types.md#swatchopacity"><code>SwatchOpacity</code></a><code>): string | undefined</code></td><td>Gets the hex code for the given color key. If the color does not exist, this will return the key as-is.</td></tr></tbody></table>

### Changelog

* **4.0.0:** removed `getBgHex`, `getBorderHex` and `getFgHex`. Use a [material](../../core-concepts/materials/README.md) instead.

* **2.7.0:** added the `getBorderHex` method.
