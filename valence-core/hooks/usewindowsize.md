---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# UseWindowSize

`useWindowSize` is a hook that provides the current width and height of the browser window. It automatically updates when the window is resized.

## Usage

```tsx
import { useWindowSize, Text } from "@valence-ui/core";

function MyComponent() { 
    const { width, height } = useWindowSize();
    
    return ( 
        <Text>
            Window size: {width}px × {height}px
        </Text>
    )
}
```

### Responsive layouts

This hook is useful for creating responsive layouts that need to respond to the exact window dimensions:

```tsx
import { useWindowSize, Flex, Text } from "@valence-ui/core";

function MyComponent() { 
    const { width } = useWindowSize();
    
    const columns = width > 1200 ? 4 : width > 800 ? 3 : width > 500 ? 2 : 1;
    
    return ( 
        <Flex>
            <Text>
                Showing {columns} columns
            </Text>
        </Flex>
    )
}
```

{% hint style="info" %}
For most responsive use cases, consider using the [UseBreakpoint](usebreakpoint.md) hook or the [Responsiveness](../../core-concepts/responsiveness.md) system instead. `useWindowSize` is best used when you need exact pixel values rather than breakpoint-based logic.
{% endhint %}

## Return type

<table data-full-width="true"><thead><tr><th width="130">Attribute</th><th width="120">Type</th><th>Description</th></tr></thead><tbody><tr><td>width</td><td><code>number</code></td><td>The current width of the window.</td></tr><tr><td>height</td><td><code>number</code></td><td>The current height of the window.</td></tr></tbody></table>
