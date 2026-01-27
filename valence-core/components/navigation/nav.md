---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# App Nav

{% hint style="warning" %}
As of Valence 3, this component has a new name (App Nav) and now imports from `@valence-ui/core`.
{% endhint %}

The App Nav component is a container component designed to handle movement between high-level pages of the application. It can also be used for application-level actions, such as signing out, changing the color scheme, etc.

The App Nav is displayed as a vertical strip containing [Icon Buttons](../buttons/icon-button.md) down the left-hand side of the screen, and will transform to a horizontal strip on the `mobile` [breakpoint](../../../core-concepts/responsiveness.md). This component is designed to be used within the [App Container](../layout/the-appcontainer.md), but can be used elsewhere.

## Usage

```tsx
import { AppNav } from "@valence-ui/core";
import { IconCategory } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <AppNav
            buttons={[
                {
                    id: "page1",
                    children: <IconCategory />,
                    highlighted: true,
                    to: "/page-1"
                },
                // More buttons...
            ]}
        />
    )
}
```

## Displaying buttons on the bottom

By default, all items in the `buttons` prop will be stacked vertically from the top down. In some circumstances, you may want to display buttons at the bottom of the `Nav`, for which the `bottomButtons` prop becomes useful:

```tsx
import { AppNav } from "@valence-ui/core";
import { IconCategory, IconLogout } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <AppNav
            buttons={[
                {
                    id: "page1",
                    children: <IconCategory />,
                    highlighted: true,
                    to: "/page-1"
                },
                // More buttons...
            ]}
            bottomButtons={[
                {
                    id: "signOut",
                    children: <IconLogout />,
                    onClick: () => alert("Signed out")
                },
                // More buttons...
            ]}
        />
    )
}
```

The `bottomButtons` prop acts effectively the same as the `buttons` prop, but will stack on the bottom instead of top.

On the `mobile` breakpoint, both regular and bottom buttons will be stacked next to one another horizontally from left-to-right, with `bottomButtons` towards the right.

## Hiding specific buttons

Every child of the `buttons` and `bottomButtons` prop accepts a `show` prop, which allows you to control the breakpoints at which this button is visible. This can be useful to hide specific buttons on the `mobile` breakpoint, especially if you have many buttons stacking across the smaller `Nav`.

```tsx
import { AppNav } from "@valence-ui/core";
import { IconCategory } from "@tabler/icons-react";

function MyComponent() { 
    return ( 
        <AppNav
            buttons={[
                {
                    id: "page1",
                    children: <IconCategory />,
                    highlighted: true,
                    to: "/page-1",
                    // Show on everything except mobile
                    show: { 
                        default: true,
                        mobile: false,
                    }
                },
                // More buttons...
            ]}
        />
    )
}
```

## Adding a favicon

The `Nav` component also accepts a `favicon` and `faviconProps`, which can be used to add a custom graphic, logo or icon at the top of the `Nav`. Note that the favicon will not show on `mobile` breakpoints.

```tsx
import { AppNav } from "@valence-ui/core";
import { IconCategory } from "@tabler/icons-react";
import FaviconImg from "./assets/images/favicon.png";

function MyComponent() { 
    return ( 
        <AppNav
            favicon={FaviconImg}
            faviconProps={{
                // Custom props to turn the favicon 
                // into a link button
                component: "link",
                to: "/home",
            }}
            buttons={[
                {
                    id: "page1",
                    children: <IconCategory />,
                    highlighted: true,
                    to: "/page-1",
                    // Show on everything except mobile
                    show: { 
                        default: true,
                        mobile: false,
                    }
                },
                // More buttons...
            ]}
        />
    )
}
```

***

## Props

### AppNavButtonProps

_Extends_ [_`IconButtonProps`_](../buttons/icon-button.md#props)_._

<table><thead><tr><th width="146">Property</th><th width="128">Type</th><th>Description</th></tr></thead><tbody><tr><td>highlighted</td><td><code>boolean</code></td><td>Whether this button is highlighted. <code>false</code> by default.</td></tr><tr><td>show</td><td><code>boolean</code></td><td>Whether this button should be shown. <code>true</code> by default.</td></tr></tbody></table>

### GenericNavProps

_Extends_ [_GenericLayoutProps_](../../../valence-utils/generics/layout.md#genericlayoutprops) _&_ [_`PolymorphicLayoutProps`_](../../../valence-utils/polymorphism/polymorphic-layout.md#polymorphiclayoutprops)_._

<table><thead><tr><th width="160">Property</th><th width="242">Type</th><th>Description</th></tr></thead><tbody><tr><td>buttons</td><td><a href="nav.md#appnavbuttonprops"><code>AppNavButtonProps</code></a><code>[]</code></td><td>Buttons to display on the top of the nav.</td></tr><tr><td>bottomButtons</td><td><code>AppNavButtonProps[]</code></td><td>Buttons to display on the bottom of the nav.</td></tr><tr><td>gap</td><td><code>CSSProperties["gap"]</code></td><td>Sets <code>gap</code> CSS property.</td></tr></tbody></table>

### AppNavProps

_Extends_ [_`GenericNavProps`_](nav.md#genericnavprops)_._

<table><thead><tr><th width="151">Property</th><th width="250">Type</th><th>Description</th></tr></thead><tbody><tr><td>favicon</td><td><code>string</code></td><td>A favicon or app logo to include at the top of the nav on desktop devices.</td></tr><tr><td>faviconProps</td><td><a href="../buttons/primitive-button.md#props"><code>PrimitiveButtonProps</code></a></td><td>Props to pass to the favicon button.</td></tr></tbody></table>

***

## Changelog

* **3.0.0:** now imports from `@valence-ui/core`, renamed to App Nav.
