# 🤚 Generics

Generics are shared prop interfaces that provide consistent behavior across related components. Understanding these interfaces helps you work more effectively with Valence components.

## Available generics

- **[Generic Button Props](generic-button-props.md)** - Shared props for all button components
- **[Generic Input Props](generic-input-props.md)** - Shared props for all input components
- **[Generic Sheet Props](generic-sheet-props.md)** - Shared props for all sheet components

## How generics work

Each component in Valence extends one or more generic interfaces. For example, all button components extend `GenericButtonProps`, which provides common properties like `variant`, `size`, and `disabled`.

When reading component documentation, you'll often see "Extends `GenericButtonProps`" which means all the props from that generic interface are available on that component.
