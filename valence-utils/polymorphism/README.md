# 🧜♀ Polymorphism

Polymorphic components can render as different HTML elements while maintaining their styling and functionality. This is useful for semantic HTML, accessibility, and integrating with routing libraries.

{% hint style="info" %}
For a conceptual overview of polymorphism, see the [Polymorphism core concept](../../core-concepts/polymorphism.md).
{% endhint %}

## Available polymorphic components

- **[Polymorphic Button](polymorphic-button.md)** - Base polymorphic button (default: `button`)
- **[Polymorphic Layout](polymorphic-layout.md)** - Base polymorphic layout container (default: `div`)
- **[Polymorphic Text](polymorphic-text.md)** - Base polymorphic text element (default: `p`)

## Usage

Use the `component` prop to change the underlying HTML element:

```tsx
import { Button } from "@valence-ui/core";

// Renders as an <a> tag
<Button component="a" href="https://example.com">
    External Link
</Button>

// Renders as a React Router Link
<Button component="link" to="/about">
    Internal Link
</Button>
```
