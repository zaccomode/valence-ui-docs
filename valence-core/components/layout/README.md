# 🧩 Layout

Layout components help structure and organize content within your application. They provide consistent spacing, alignment, and responsive behavior.

## Available layout components

### Core containers
- **[App Container](the-appcontainer.md)** - The root application layout container
- **[Page Container](page-container.md)** - Centered, scrollable page content wrapper
- **[Card](card.md)** - Styled content container with padding

### Flexbox
- **[Flex](flex/README.md)** - Flexible box layout container
  - **[Flex Center](flex/flex-center.md)** - Centered flex container

### Grid
- **[Grid](grid.md)** - CSS Grid layout container

### Specialized
- **[Header](header.md)** - Page/section header container
- **[Floating Toolbar](floating-toolbar.md)** - Floating action toolbar
- **[Overflow Container](overflow-container.md)** - Scrollable container
- **[Space](space.md)** - Spacing utility component

## Shared features

Layout components share common props from [`GenericLayoutProps`](../../../valence-utils/generics/layout.md), including:

- **`padding`**, **`margin`** - Spacing properties
- **`width`**, **`height`** - Dimension properties
- **`material`** - The [material](../../../core-concepts/materials/README.md) applied to the container (`Flex`, `Card`, `FloatingToolbar`)
