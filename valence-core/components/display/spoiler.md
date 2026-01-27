---
description: 'Last updated: 2.0.0 (21/01/2024)'
---

# Spoiler

## Usage

```tsx
import { Button, Spoiler, Text } from "@valence-ui/core";

function MyComponent() { 
    const [show, setShow] = React.useState(false);

    return ( 
        <>
            <Button
                onClick={() => setShow(!show)}
            >
                Toggle spoiler
            </Button>
            
            <Spoiler
                show={show}
            >
                <Text>
                    Spoiled content!
                </Text>
            </Spoiler>
        </>
    )
}
```

## Props

_Extends `GenericProps`._

<table data-full-width="true"><thead><tr><th width="123">Property</th><th width="115">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>show</code></td><td><code>boolean</code></td><td>Whether to show or hide the spoiler content. Defaults to <code>true</code>.</td></tr></tbody></table>
