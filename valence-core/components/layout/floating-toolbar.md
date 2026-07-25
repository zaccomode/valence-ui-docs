---
description: 'Last updated: 4.0.0'
---

# Floating Toolbar

The Floating Toolbar is the replacement to the `OutlineContainer` from Valence 2. It is largely similar, but uses the new `useFloating` hook to create a simpler mechanism for floating.

## Usage

```tsx
import { FloatingToolbar, Button } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <FloatingToolbar
            label="Toolbar label!"
            positionVertical="top"
            positionHorizontal="left"
            offset={5}
        >
            <Button>Button text</Button>
        </FloatingToolbar>
    )
}
```

## Floating

The Floating Toolbar will use a `fixed` position by default, but this can be changed using the `position` prop. It can also be moved using the `positionVertical`, `positionHorizontal` and `offset` parameters.

The toolbar will also accept `top`, `left`, `right`, and `bottom` parameters for further customization.&#x20;

The toolbar will automatically avoid unsafe areas (such as the notch and navigation unsafe areas on new iPhone models).

***

## Props&#x20;

_Extends_ [_`GenericFloatingLayoutProps`_](../../../valence-utils/generics/layout.md#genericfloatinglayoutprops) _&_ [_`FlexProps`_](flex/#props)_._

<table><thead><tr><th width="192">Property</th><th width="218">Type</th><th>Description</th></tr></thead><tbody><tr><td>positionVertical</td><td><code>PositionVertical</code></td><td>The vertical position of this toolbar. Defaults to <code>"top"</code>.</td></tr><tr><td>positionHorizontal</td><td><code>PositionHorizontal</code></td><td>The horizontal position of this toolbar. Defaults to <code>"left"</code>.</td></tr><tr><td>offset</td><td><code>number</code></td><td>The offset of the toolbar from the edge of the screen. Defaults to <code>5</code>.</td></tr><tr><td>label</td><td><code>string</code></td><td>A label to display below the toolbar.</td></tr><tr><td>labelProps</td><td><code>TextProps</code></td><td>Optional props to pass to the label component.</td></tr><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material of the toolbar. A <code>PaperMaterial</code> by default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>The size class of the component's radius. Defaults to theme default.</td></tr><tr><td>shadow</td><td><code>boolean</code></td><td>Whether to render a shadow underneath the component. Defaults to <code>false</code>.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`.
