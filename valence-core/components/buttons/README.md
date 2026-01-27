# 🔘 Buttons

Buttons are interactive elements that allow users to trigger actions. Valence provides a variety of button components to suit different use cases.

## Available buttons

- **[Button with Icon](button-with-icon.md)** - A button that displays both an icon and text
- **[Text Button](text-button.md)** - A simple button that displays text
- **[Icon Button](icon-button.md)** - A button that displays only an icon
- **[Grid Button](grid-button.md)** - A larger button designed for grid layouts
- **[Multi-part Button](multi-part-button.md)** - A button with a dropdown for secondary actions
- **[Unstyled Button](un-styled-button.md)** - A button with no default styling
- **[Primitive Button](primitive-button.md)** - The foundational button component (for advanced use)

## Shared features

All buttons share common props inherited from [`GenericButtonProps`](../../generics/generic-button-props.md), including:

- **`variant`** - The visual style (`subtle`, `light`, `filled`, `outlined`, or `paper`)
- **`size`** - The size class (`xs`, `sm`, `md`, `lg`, or `xl`)
- **`radius`** - The border radius size
- **`disabled`** - Whether the button is disabled
- **`loading`** - Whether the button is in a loading state
- **`float`** - Allows the button to float like a FAB (Floating Action Button)
