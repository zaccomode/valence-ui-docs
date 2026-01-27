---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# UseLockScroll

`useLockScroll` is a hook that locks or unlocks scrolling on a specified element. This is particularly useful for modal dialogs, side sheets, or any overlay that should prevent background scrolling.

## Usage

```tsx
import { useLockScroll, useDisclosure, Modal, Button } from "@valence-ui/core";

function MyComponent() { 
    const disclosure = useDisclosure();
    
    // Lock scroll when modal is open
    useLockScroll(disclosure.opened);
    
    return ( 
        <>
            <Button onClick={() => disclosure.open()}>
                Open Modal
            </Button>
            
            <Modal disclosure={disclosure} title="My Modal">
                Scroll is locked while this modal is open!
            </Modal>
        </>
    )
}
```

### Custom element

By default, `useLockScroll` will lock scrolling on the element with the ID `"root"`. You can specify a different element by passing a second parameter:

```tsx
import { useLockScroll } from "@valence-ui/core";

function MyComponent() { 
    // Lock scroll on a custom element
    useLockScroll(true, "my-scrollable-container");
    
    // ...
}
```

## Parameters

<table data-full-width="true"><thead><tr><th width="160">Parameter</th><th width="120">Type</th><th>Description</th></tr></thead><tbody><tr><td>lock (required)</td><td><code>boolean</code></td><td>Whether to lock scrolling on the element.</td></tr><tr><td>elementId</td><td><code>string</code></td><td>The ID of the element to lock scrolling on. Defaults to <code>"root"</code>.</td></tr></tbody></table>
