---
description: 'Last updated: 4.0.0'
---

# Color

Valence makes use of a powerful yet unconventional color system that uses opacity to mix colors.  This unusual method allows Valence to mix colors more dynamically than other libraries, making it easier to build layered elements (such as a button on a card), without creating an expansive color palette.

## Terminology

* **Swatch:** part of a color, including a six-digit base hex code (#XXXXXX) and three opacity levels, each of which is a two-digit hex code to be appended to the base code.
* **Color:** a complete Valence color, which includes a key, a default Swatch and an optional dark Swatch.

## The `useColors` hook

{% hint style="info" %}
Main article: [UseColors](../../valence-core/hooks/usecolors.md).
{% endhint %}

The `useColors` hook allows easy access to Valence's color palette, and exposes two functions that can be utilized in your code:

1. `getSwatch()` - Retrieves a swatch of a color from the palette, based on the color scheme the user has elected to use.
2. `getHex()` - Retrieves a hex code for a color at the given key. This function will return a complete hex code (including opacity) for a given color.

{% hint style="warning" %}
**Changed in 4.0.0**

`getBgHex()`, `getFgHex()` and `getBorderHex()` were removed. They resolved a `FillVariant` into a concrete color, which is now the job of [materials](../materials/README.md). If you are writing your own material, call `getHex()` directly.
{% endhint %}

Every function accepts a `key` parameter, which is the `key` value of a Valence `Color`. `key` will also accept the following:

* `"primary"`, in which case the current primary color will be used.
* Any six-digit hex code, in which case a default Swatch will be created that can have its opacity modified.
* Any [web-safe color key](https://www.w3schools.com/tags/ref\_colornames.asp), which (if not found on the Valence palette), will just return exactly as it is. This should be used as an absolute last resort, because these values cannot have their opacity modified.
