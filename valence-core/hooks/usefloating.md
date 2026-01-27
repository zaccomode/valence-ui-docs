---
description: 'Last updated: 3.0.0 (04/07/2024) | Added: 2.0.0'
---

# UseFloating

The `useFloating()` hook provides a simple interface for generating CSS styles that respect the safe areas of a given device. It is used in the [Floating Toolbar](../components/layout/floating-toolbar.md) and all button components to provide float functionality.

## Usage

```tsx
import { useFloating, Flex, Text } from "@valence-ui/core";

function MyComponent() { 
    const floating = useFloating({
        positionHorizontal: "left",
        positionVertical: "top",
        offset: 20,
    });
    
    const FlexStyle = { 
        position: "fixed",
        zIndex: 200,
        ...floating.style,    // Generated styles applied
    }
    
    return ( 
        <Flex style={FlexStyle}>
            <Text>Hi there!</Text>
        </Flex>
    )
}
```

The offset can also be customized far more:

```tsx
import { useFloating } from "@valence-ui/core";

function MyComponent() { 
    const floating = useFloating({
        positionHorizontal: "center",
        positionVertical: "top",
        offset: { 
            horizontal: 20,        // Will accept any CSS-in-JS valid property
            vertical: "30%",
        }
    });
    
    // OR
    
    const floating2 = useFloating({
        positionHorizontal: "left",
        positionVertical: "top",
        offset: { 
            // Only the left and top styles will be applied in this case
            top: 20,
            bottom: "30%",
            left: "2rem",
            right: 30,
        }
    });
    
    // etc...
}
```

`useFloating` is also [responsive](../../core-concepts/responsiveness.md), allowing you to define behavior for specific breakpoints:

```tsx
import { useFloating } from "@valence-ui/core";

function MyComponent() { 
    const floating = useFloating({
        positionHorizontal: { default: "left", mobile: "right" },
        positionVertical: "top",
        offset: { default: 20, tablet: 12, mobile: 5 },
    });
}
```

***

## Types

### PositionHorizontal

```typescript
type PositionHorizontal = "left" | "right" | "center";
```

### PositionVertical

```typescript
type PositionVertical = "top" | "bottom" | "center";
```

### FloatingOffset

```typescript
export type FloatingOffset = number | {
  horizontal: CSSProperties["left"];
  vertical: CSSProperties["top"];
} | {
  top: CSSProperties["top"];
  right: CSSProperties["right"];
  bottom: CSSProperties["bottom"];
  left: CSSProperties["left"];
}
```

## Props

<table><thead><tr><th width="182">Property</th><th width="224">Type</th><th width="103">Default</th><th>Description</th></tr></thead><tbody><tr><td>positionHorizontal</td><td><a href="usefloating.md#positionhorizontal"><code>PositionHorizontal</code></a></td><td><code>"left"</code></td><td>The horizontal position of the element.</td></tr><tr><td>positionVertical</td><td><a href="usefloating.md#positionvertical"><code>PositionVertical</code></a></td><td><code>"top"</code></td><td>The vertical position of the element.</td></tr><tr><td>offset</td><td><a href="usefloating.md#floatingoffset"><code>FloatingOffset</code></a></td><td><code>20</code></td><td>How far from the edges this element is positioned.</td></tr><tr><td>calculateOffset</td><td><code>boolean</code></td><td><code>true</code></td><td>Whether to include safe areas (such as the notch and navigation cutouts in new iPhones) when calculating offsets.</td></tr></tbody></table>

***

## Changelog

* **3.0.0:** Added hook.
