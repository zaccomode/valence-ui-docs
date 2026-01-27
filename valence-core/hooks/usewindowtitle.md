---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# UseWindowTitle

`useWindowTitle` is a hook that sets the browser window/tab title. This is useful for dynamically updating the page title based on the current view or state.

## Usage

```tsx
import { UseWindowTitle, Text } from "@valence-ui/core";

function MyComponent() { 
    UseWindowTitle("My Page Title");
    
    return ( 
        <Text>
            Check the browser tab!
        </Text>
    )
}
```

### Dynamic titles

The title will update whenever the value passed to the hook changes:

```tsx
import { UseWindowTitle, Text } from "@valence-ui/core";
import { useState } from "react";

function MyComponent() { 
    const [count, setCount] = useState(0);
    
    UseWindowTitle(`Count: ${count}`);
    
    return ( 
        <Text>
            The tab title shows the current count!
        </Text>
    )
}
```

### Page-specific titles

This hook is particularly useful when combined with routing to set page-specific titles:

```tsx
import { UseWindowTitle } from "@valence-ui/core";

function HomePage() { 
    UseWindowTitle("Home | My App");
    
    return (
        // Page content...
    )
}

function AboutPage() { 
    UseWindowTitle("About | My App");
    
    return (
        // Page content...
    )
}
```

## Parameters

<table data-full-width="true"><thead><tr><th width="160">Parameter</th><th width="120">Type</th><th>Description</th></tr></thead><tbody><tr><td>title (required)</td><td><code>string</code></td><td>The title to set for the browser window.</td></tr></tbody></table>
