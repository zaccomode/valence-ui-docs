---
description: 'Last updated: 4.0.0'
---

# Materials

Materials are how Valence components decide what they look like. A material is an object that knows how to turn the current theme and color scheme into a set of CSS rules — background, foreground, border, shadow, blur, hover and focus states, and scrollbar styling.

Materials replaced the `variant` prop in 4.0.0. Where you previously wrote `variant="light"`, you now pass a material instance.

{% hint style="info" %}
Coming from 3.x? See the [4.0.0 update notes](../../update-notes/4.0.0.md) for a variant-to-material mapping table.
{% endhint %}

## Usage

Import a material and construct it:

```tsx
import { Button, GlassMaterial } from "@valence-ui/core";

function MyComponent() {
  return (
    <Button material={new GlassMaterial({ color: "blue" })}>
      Save changes
    </Button>
  );
}
```

Most of the time you will not pass one at all — components fall back to the theme defaults:

```tsx
// Uses theme.materials.button
<Button>Save changes</Button>
```

## Available materials

* **[Air](air-material.md)** — fully transparent, with a tinted background on hover. Best for tertiary actions and dropdown items.
* **[Glass](glass-material.md)** — a translucent tint of its color, optionally blurred. The default for buttons and inputs.
* **[Paper](paper-material.md)** — an opaque surface with a border and optional elevation shadow. The default for cards.
* **[Solid](solid-material.md)** — a filled block of its color with a contrasting foreground. Best for primary actions.

## Shared properties

Every material accepts these, and each one is optional.

<table data-full-width="true"><thead><tr><th width="190">Property</th><th width="180">Type</th><th>Description</th></tr></thead><tbody><tr><td>color</td><td><code>string</code></td><td>The color of the material. Different materials use this differently — as a foreground, a tint, or a fill. Accepts any theme color key or a hex code. Defaults to the theme's <code>primaryColor</code> (Paper defaults to <code>"black"</code>).</td></tr><tr><td>interactive</td><td><code>boolean</code></td><td>Whether the material emits hover, focus and disabled rules. Defaults to <code>false</code>. Components that are inherently interactive set this themselves.</td></tr><tr><td>overrides</td><td><code>CSSObject</code></td><td>Styles applied last, after everything else the material produces. Use this to tweak a material without writing a new one.</td></tr><tr><td>childrenOverrides</td><td><code>CSSObject</code></td><td>Styles applied last to the material's descendants.</td></tr></tbody></table>

## Materials are immutable

Every setter returns a **copy** rather than mutating in place, so a material can be shared safely between components and stored in the theme:

```tsx
const base = new GlassMaterial({ color: "blue" });
const strong = base.setBlur("strong");

// base is untouched
```

Available on every material:

<table data-full-width="true"><thead><tr><th width="300">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>setColor(color: string)</code></td><td>Returns a copy with a new color.</td></tr><tr><td><code>setInteractive(interactive: boolean)</code></td><td>Returns a copy with hover/focus rules enabled or disabled.</td></tr><tr><td><code>setOverrides(overrides: CSSObject)</code></td><td>Returns a copy with new overrides.</td></tr><tr><td><code>setChildrenOverrides(overrides: CSSObject)</code></td><td>Returns a copy with new children overrides.</td></tr><tr><td><code>copy()</code></td><td>Returns a copy of the material, preserving its concrete type.</td></tr></tbody></table>

## Setting theme defaults

The `ValenceProvider` holds a default material for buttons, inputs and cards. Set them once and every component picks them up:

```tsx
import {
  ValenceProvider,
  GlassMaterial,
  PaperMaterial,
  SolidMaterial,
} from "@valence-ui/core";

function App() {
  return (
    <ValenceProvider
      materials={{
        button: new SolidMaterial(),
        input: new GlassMaterial({ color: "black" }),
        card: new PaperMaterial({ elevation: 2 }),
      }}
    >
      {/* Your app here */}
    </ValenceProvider>
  );
}
```

The defaults, if you do not set them:

```tsx
{
  button: new GlassMaterial(),
  input: new GlassMaterial({ color: "black" }),
  card: new PaperMaterial(),
}
```

## Which components accept a material

`material` is available on buttons, inputs, cards, `Flex`, `Image`, `Avatar`, `Tooltip.Content` and the sheet components. Some components take several — `Switch` accepts a `materials` object with a material for each of its four states, and `PillSelector` accepts one for regular pills, selected pills, its input and its buttons.

## Writing your own material

Materials are classes extending the abstract `Material` base. Implement `copy()`, `getStyles()`, `getChildrenStyles()` and `getScrollbarStyles()`:

```tsx
import { Material, MaterialProps, IValenceContext, UseColorsReturn } from "@valence-ui/core";
import { CSSObject } from "@emotion/react";

export class DashedMaterial extends Material {
  constructor(props?: MaterialProps) {
    super(props ?? {});
  }

  copy(): DashedMaterial {
    return new DashedMaterial({
      interactive: this.interactive,
      color: this.color,
      overrides: this.overrides,
      childrenOverrides: this.childrenOverrides,
    });
  }

  getStyles(valence: IValenceContext, colors: UseColorsReturn): CSSObject {
    const color = this.color ?? valence.primaryColor;

    return {
      backgroundColor: "transparent",
      color: colors.getHex(color),
      border: `2px dashed ${colors.getHex(color, "medium")}`,

      ...(this.interactive && {
        "&:hover": { borderColor: colors.getHex(color) },
      }),

      "& *": { ...this.getChildrenStyles(valence, colors) },
      ...this.getScrollbarStyles(valence, colors),
      ...this.overrides,
    };
  }

  getChildrenStyles(valence: IValenceContext, colors: UseColorsReturn): CSSObject {
    return {
      color: colors.getHex(this.color ?? valence.primaryColor),
      ...this.childrenOverrides,
    };
  }

  getScrollbarStyles(valence: IValenceContext, colors: UseColorsReturn): CSSObject {
    return {
      "&::-webkit-scrollbar-thumb": {
        backgroundColor: colors.getHex(this.color ?? valence.primaryColor, "medium"),
      },
    };
  }
}
```

Both `getStyles` methods receive the theme context and the [colors helper](../color/README.md), so resolve colors through `colors.getHex()` rather than hard-coding hex values — that is what keeps a material responsive to the active color scheme.

## Changelog

* **4.0.0:** Introduced. Replaces the `variant` prop and the `FillVariant` type.
