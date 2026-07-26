---
description: 'Last updated: 4.0.0'
---

# 🎬 The ValenceProvider

The ValenceProvider provides every component in your app with the relevant styling and default values that they require to function correctly.

Within the root app file (usually `App.tsx` or `App.jsx`), import and add the `ValenceProvider`:

{% code title="App.tsx" %}
```tsx
import { ValenceProvider } from "@valence-ui/core"

function App() {
  return ( 
    <>
      <ValenceProvider>
        {/* Your app here */}
      </ValenceProvider>
    </>
  )
}

export default App;
```
{% endcode %}

{% hint style="warning" %}
**Changed in 4.0.0**

`defaults.variant`, `defaults.transitionDuration` and `defaults.shadow` were removed. Their job now belongs to [materials](../../core-concepts/materials/README.md), configured through the new `materials` prop.
{% endhint %}

## Modifying default attributes

Every value that the ValenceProvider supplies to your app can be modified by passing in props to the component:

{% code title="App.tsx" fullWidth="false" %}
```tsx
import {
  ValenceProvider,
  GlassMaterial,
  PaperMaterial,
  SolidMaterial,
} from "@valence-ui/core"

function App() {
  return ( 
    <>
      <ValenceProvider
        primaryColor="blue"
        defaults={{ size: "md", radius: "md" }}
        materials={{
          button: new SolidMaterial(),
          input: new GlassMaterial({ color: "black" }),
          card: new PaperMaterial({ elevation: 2 }),
        }}
        breakpoints={{
          mobileWidth: 480,
          tabletWidth: 768,
          desktopLargeWidth: 1024,
          tvWidth: 1440,
        }}
      >
        {/* Your app here */}
      </ValenceProvider>
    </>
  )
}

export default App;
```
{% endcode %}

## Props

<details>

<summary>colors</summary>

**Type:**

`Color[]`

**Default value:**

`DEFAULT_PALETTE`

**Description:**

A list of all colors to use.

{% hint style="danger" %}
In 4.0.2 this **replaces** the default palette rather than extending it, which removes built-in keys such as `black` and `white` that materials depend on. Until that is fixed, spread the default palette yourself:

```tsx
import { ValenceProvider, DEFAULT_PALETTE } from "@valence-ui/core";

<ValenceProvider colors={[...DEFAULT_PALETTE, myBrandColor]} />
```
{% endhint %}

</details>

<details>

<summary>primaryColor</summary>

**Type:**

`string`

**Default value:**

`"pink"`

**Description:**

The primary color to default upon.

</details>

<details>

<summary>preferredColorScheme</summary>

**Type:**

`PreferrableColorScheme` (`"light" | "dark" | "system"`)

**Default value:**

`"system"`

**Description:**

The user's preferred color scheme.

</details>

<details>

<summary>defaults</summary>

**Type:**

```tsx
type defaults = { 
    /** The default component size */
    size: ComponentSize;
    /** The default component radius size */
    radius: ComponentSize;
}
```

**Default value:**

```json
{ 
    size: "sm",
    radius: "sm",
}
```

**Description:**

Default sizes for common attributes.

</details>

<details>

<summary>materials</summary>

**Type:**

```tsx
type materials = { 
    /** The default material to use for buttons */
    button: Material;
    /** The default material to use for inputs */
    input: Material;
    /** The default material to use for cards */
    card: Material;
}
```

**Default value:**

```tsx
{
    button: new GlassMaterial(),
    input: new GlassMaterial({ color: "black" }),
    card: new PaperMaterial(),
}
```

**Description:**

The default [materials](../../core-concepts/materials/README.md) applied to objects of each type. Any component that accepts a `material` prop falls back to the relevant entry here.

</details>

<details>

<summary>fontFamily</summary>

**Type:**

```tsx
type fontFamily = { 
    /** The default font family to use */
    default: string;
    /** The font family to use for headings. If not provided, the default will be used */
    heading?: string;
    /** The font family to use for monospace text. If not provided, the default will be used */
    monospace?: string;
}
```

**Default value:**

```json
{
    default: "Inter, sans-serif",
    heading: undefined,
    monospace: "monospace",
}
```

**Description:**

The default font families to use in specific contexts.

</details>

<details>

<summary>getFont()</summary>

**Type:**

```tsx
function getFont: (property: "default" | "heading" | "monospace") => string;
```

**Description:**

Finds a font family within the theme context.

</details>

<details>

<summary>sizeClasses</summary>

**Type:**

```tsx
type SizeClasses = { 
    /** The padding to use for components */
    padding: SizeClasses<CSSProperties["padding"]>;
    /** The height to use for components */
    height: SizeClasses<CSSProperties["height"]>;
    /** The radius to use for components */
    radius: SizeClasses<CSSProperties["borderRadius"]>;
    /** The font size to use for components */
    fontSize: SizeClasses<CSSProperties["fontSize"]>;
    /** The icon size to use for components */
    iconSize: SizeClasses<CSSProperties["fontSize"]>;
}
```

**Default value:**

```json
{
    padding: { xs: 10, sm: 15, md: 20, lg: 25, xl: 30 },
    height: { xs: 30, sm: 35, md: 40, lg: 50, xl: 60 },
    radius: { xs: 2, sm: 5, md: 10, lg: 15, xl: 25 },
    fontSize: { xs: 12, sm: 14, md: 16, lg: 18, xl: 20 },
    iconSize: { xs: 18, sm: 20, md: 24, lg: 26, xl: 30 },
}
```

**Description:**

Standardised sizing guide to use for components.

</details>

<details>

<summary>getSize()</summary>

**Type:**

```tsx
function getSize: (property: "padding" | "height" | "radius" | "fontSize" | "iconSize", size?: ComponentSize) => any;
```

**Description:**

Finds a size within the theme context.

</details>

<details>

<summary>titles</summary>

**Type:**

```tsx
type titles = { 
    1: TextProps;
    2: TextProps;
    3: TextProps;
    4: TextProps;
    5: TextProps;
    6: TextProps;
}
```

**Default value:**

```json
{
    1: { fontSize: 28, bold: true },
    2: { fontSize: 22, bold: true },
    3: { fontSize: 18, bold: true },
    4: { fontSize: 16, bold: true },
    5: { fontSize: 14, bold: true },
    6: { fontSize: 12, bold: true },
}
```

**Description:**

Props to refer to for titles.

</details>

<details>

<summary>breakpoints</summary>

**Type:**

```tsx
type breakpoints = { 
    mobileWidth: number;
    tabletWidth: number;
    desktopLargeWidth: number;
    tvWidth: number;
}
```

**Default value:**

```json
{
    mobileWidth: 480,
    tabletWidth: 768,
    desktopLargeWidth: 1024,
    tvWidth: 1440,
}
```

**Description:**

Breakpoints to use for determining breakpoint-sensitive props.

</details>

## Changelog

* **4.0.0:** Added `materials`. Removed `defaults.variant`, `defaults.transitionDuration` and `defaults.shadow`.
