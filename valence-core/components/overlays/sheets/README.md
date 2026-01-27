# 📰 Sheets

Sheets are overlay components that slide in from the edges of the screen. They're useful for displaying secondary content, menus, or forms without navigating away from the current page.

## Available sheets

- **[Bottom Sheet](bottom-sheet.md)** - Slides up from the bottom of the screen
- **[Side Sheet](side-sheet.md)** - Slides in from the side (left or right)
- **[Dynamic Sheet](dynamic-sheet.md)** - Automatically chooses between bottom and side based on screen size

## Shared features

All sheets share common props from [`GenericSheetProps`](../../../generics/generic-sheet-props.md), including:

- **`disclosure`** - A disclosure hook to control the sheet's open/closed state
- **`flexProps`** - Props to pass to the inner flex container

Sheets also support overlay features like:
- **`closeOnOverlayClick`** - Close when clicking the background
- **`closeOnEscape`** - Close when pressing the Escape key
- **`lockScroll`** - Prevent background scrolling while open
