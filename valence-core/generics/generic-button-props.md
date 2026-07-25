---
description: 'Last updated: 4.0.0'
---

# Generic button props

## Props

_Extends `GenericClickableProps`, `GenericClickableEventProps`, `PolymorphicButtonProps`, `GenericLayoutProps`._

<table data-full-width="true"><thead><tr><th width="149">Property</th><th width="176">Type</th><th>Description</th></tr></thead><tbody><tr><td>material</td><td><a href="../../core-concepts/materials/README.md"><code>Material</code></a></td><td>This button's material. Defaults to <code>theme.materials.button</code>.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>This button's sizing class. Defaults to theme default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>This button's radius size class. Defaults to theme default.</td></tr><tr><td>square</td><td><code>boolean</code></td><td>Whether this button is square.</td></tr><tr><td>grow</td><td><code>boolean</code></td><td>Shorthand for <code>flex-grow = 1</code>.</td></tr><tr><td>disabled</td><td><code>boolean</code></td><td>Whether this button is disabled.</td></tr><tr><td>loading</td><td><code>boolean</code></td><td>Whether this button is loading.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Replaced `variant` with `material`. Removed `shadow` — use a material's `elevation` instead.
