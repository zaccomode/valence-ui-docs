---
description: 'Last updated: 4.0.0'
---

# Flex

The Flex component is one of the most used components of the Valence library, and provides a direct interface to the CSS `flex` attributes via the component's props.

Since 4.0.0 it also accepts a `material` and a `radius`, which is what replaced the old `StyledFlex` component:

```tsx
import { Flex, PaperMaterial } from "@valence-ui/core";

<Flex material={new PaperMaterial({ elevation: 2 })} radius="md" padding={20}>
  {/* children */}
</Flex>
```

## Usage

```tsx
import { Flex } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Flex
            direction="row"
            align="center"
            justify="center"
            alignSelf="flex-start"
            gap={5}
            grow
            width={200}
            height={200}
            padding={20}
            margin={10}
        >
            // Flex children...
        </Flex>
    )
}
```

## Props

Extends `GenericLayoutProps` and `PolymorphicLayoutProps`.

<table data-full-width="true"><thead><tr><th width="171">Property</th><th width="341">Type</th><th>Description</th></tr></thead><tbody><tr><td>direction</td><td><code>CSSProperties["flexDirection"]</code></td><td>Sets <code>flex-direction</code> css property.</td></tr><tr><td>align</td><td><code>CSSProperties["alignItems"]</code></td><td>Sets <code>align-items</code> css property.</td></tr><tr><td>justify</td><td><code>CSSProperties["justifyContent"]</code></td><td>Sets <code>justify-content</code> css property.</td></tr><tr><td>alignSelf</td><td><code>CSSProperties["alignSelf"]</code></td><td>Sets <code>align-self</code> css property.</td></tr><tr><td>gap</td><td><code>CSSProperties["gap"]</code></td><td>Sets <code>gap</code> css property.</td></tr><tr><td>wrap</td><td><code>CSSProperties["flexWrap"]</code></td><td>Sets the <code>flex-wrap</code> property.</td></tr><tr><td>grow</td><td><code>boolean</code></td><td>Shorthand for <code>flex-grow = 1</code>.</td></tr><tr><td>center</td><td><code>boolean</code></td><td>A shorthand property that sets both <code>align</code> and <code>justify</code> to <code>center</code>.</td></tr><tr><td>material</td><td><a href="../../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>Optionally apply a material to this component. No material by default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>Optionally apply a border radius size class to this component.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Added `material` and `radius`, absorbing the removed `StyledFlex` component.
