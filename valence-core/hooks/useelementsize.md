---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# UseElementSize

`useElementSize` is a hook that provides the current width and height of an element. It automatically updates when the window is resized.

## Usage

```tsx
import { useElementSize, Flex, Text } from "@valence-ui/core";

function MyComponent() { 
    const { ref, width, height } = useElementSize();
    
    return ( 
        <Flex ref={ref}>
            <Text>
                Width: {width}px, Height: {height}px
            </Text>
        </Flex>
    )
}
```

The `ref` returned by this hook should be attached to the element you want to measure. The `width` and `height` values will update automatically when the window is resized.

## Return type

<table data-full-width="true"><thead><tr><th width="130">Attribute</th><th width="220">Type</th><th>Description</th></tr></thead><tbody><tr><td>ref</td><td><code>RefObject&lt;HTMLElement&gt;</code></td><td>A ref object that should be attached to the element you want to measure.</td></tr><tr><td>width</td><td><code>number</code></td><td>The current width of the element.</td></tr><tr><td>height</td><td><code>number</code></td><td>The current height of the element.</td></tr></tbody></table>
