---
description: 'Last updated: 4.0.0'
---

# Alert

## Usage

```tsx
import { Alert } from "@valence-ui/core";
import { IconAlertCircle } from "@tabler/icons-react";

function MyComponent() { 
    const [show, setShow] = React.useState(true);

    return ( 
        <Alert
            alert={{
                title: "Alert title",
                message: "Alert message",
                icon: <IconAlertCircle />,
            }}
            show={show}
        />
    )
}
```

### Controlled alert content

```tsx
import { Alert, AlertContent } from "@valence-ui/core";
import { IconAlertCircle } from "@tabler/icons-react";

function MyComponent() { 
    const [alert, setAlert] = React.useState<AlertContent | null>({
        title: "Alert title",
        message: "Alert message",
        icon: <IconAlertCircle />,
    });

    return ( 
        <Alert
            alert={alert}
            show={alert !== null}
        />
    )
}
```

### Actions on click

```tsx
import { Alert } from "@valence-ui/core";
import { IconAlertCircle } from "@tabler/icons-react";

function MyComponent() { 
    
    function handleClick() { 
        console.log("Alert was clicked!");
    }

    return ( 
        <Alert
            alert={{
                title: "Alert title",
                message: "Alert message",
                icon: <IconAlertCircle />,
            }}
            show={true}
            onClick={handleClick}
        />
    )
}
```

{% hint style="info" %}
Other button attributes and behaviors can be passed to the Alert as well.
{% endhint %}

### Alert levels

The `material` prop can be used to display the alert with a different appearance. Note that the alert's *colour* comes from its `type` (`info` is cyan, `warning` is orange, `error` is red and `success` is green) — the material controls how that colour is rendered.

1. `"filled"` makes the alert very visible, which is useful for displaying major errors.\
   E.g. input validation error, save failure, etc.
2. `"light"` draws attention to the alert, but with a softness that is more suitable for positive updates or minor errors.\
   E.g. successful save, non-breaking error, etc.
3. `"subtle"` is the least attention-grabbing of the three, and is best used for very minor alerts.\
   E.g. additional information about an action, ideal input content, etc.

***

## Props

_Extends `GenericClickableProps`, `GenericClickableEventProps`, `PolymorphicButtonProps` and `GenericLayoutProps`._

<table data-full-width="true"><thead><tr><th width="164">Property</th><th width="237">Type</th><th>Description</th></tr></thead><tbody><tr><td>alert (required)</td><td><code>AlertContent</code></td><td>The content of this alert.</td></tr><tr><td>show</td><td><code>boolean</code></td><td>Whether to mount and show this alert.</td></tr><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material of this alert. Defaults to the theme's button material.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>The size of this alert. Defaults to the theme default size.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>The border size of this alert. Defaults to the theme default radius size.</td></tr><tr><td>animation</td><td><a href="../../../core-concepts/animations.md"><code>AnimationProps</code></a></td><td>Enter, hover and tap animations for this alert. Automatically disabled if the user has reduced motion enabled on their device.</td></tr></tbody></table>

## AlertContent

<table data-full-width="true"><thead><tr><th width="158">Property</th><th width="133">Type</th><th>Description</th></tr></thead><tbody><tr><td>title (required)</td><td><code>string</code></td><td>The title of this alert.</td></tr><tr><td>message</td><td><code>string</code></td><td>The message of this alert.</td></tr><tr><td>icon</td><td><code>ReactNode</code></td><td>The icon of this alert.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material` and `motion` with `animation`. Removed `shadow` — use a material's `elevation`.
