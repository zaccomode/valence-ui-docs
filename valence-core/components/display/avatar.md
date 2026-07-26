---
description: 'Last update: 2.1.0 (30/01/2024)'
---

# Avatar

The Avatar component builds upon the [Image](image.md) component, appearing as a round image with a custom icon placeholder.

## Usage

```tsx
import { Avatar } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Avatar
            src="https://images.unsplash.com/photo-1419242902214-272b3f66ee7a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=720&q=80"
            alt="A nice avatar!"
        />
    )
}
```

### Overriding default props

```tsx
import { Avatar } from "@valence-ui/core";
import { IconUserCircle } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <Avatar
            src="https://images.unsplash.com/photo-1419242902214-272b3f66ee7a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=720&q=80"
            alt="A nice avatar!"
            
            square={false}
            radius="sm"
            placeholder={<IconUserCircle />}
        />
    )
}
```

### Setting a material

```tsx
import { Avatar } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Avatar
            src="https://images.unsplash.com/photo-1419242902214-272b3f66ee7a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=720&q=80"
            alt="A nice avatar!"
            
            material={new SolidMaterial()}   // Defaults to theme input material
        />
    )
}
```

### Customizing the placeholder

```tsx
import { Avatar } from "@valence-ui/core";

function MyComponent() { 
    return ( 
        <Avatar
            src="https://images.unsplash.com/photo-1419242902214-272b3f66ee7a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=720&q=80"
            alt="A nice avatar!"
            
            placeholderColor="blue"
        />
    )
}
```

***

## Props

_Extends_ [_`ImageProps`_](image.md#props)_._

<table data-full-width="true"><thead><tr><th width="201.8571428571429">Property</th><th width="179">Type</th><th>Description</th></tr></thead><tbody><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material of this avatar, used to style the placeholder. Defaults to <code>theme.materials.input</code>.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>Defines the size of this avatar. Defaults to theme default.</td></tr><tr><td>secondaryIcon</td><td><code>ReactNode</code></td><td>An optional secondary icon to display near the avatar.</td></tr><tr><td>secondaryIconProps</td><td><a href="icon.md#props"><code>IconProps</code></a></td><td>Props to apply to the secondary icon, if it exists.</td></tr><tr><td>spanStyle</td><td><code>CSSProperties</code></td><td>Optional styles to pass to the containing span component.</td></tr></tbody></table>

***

## Changelog

* **4.0.0:** Replaced `variant` with `material`. Removed `outline`.

* **2.1.0:**&#x20;
  * Removed `placeholderColor` prop; use `color` instead.
  * Added `size`, `outline`, `spanStyle`, `secondaryIcon` and `secondaryIconProps` props.
