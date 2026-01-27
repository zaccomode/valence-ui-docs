# 🔼 Overlays

Overlay components appear on top of other content, typically to present focused information or actions. They include modals, tooltips, and sheets.

## Available overlay components

- **[Modal](modal.md)** - A centered dialog box for focused content
- **[Tooltip](tooltip.md)** - Small contextual information popups
- **[Modal Background](modal-background.md)** - The backdrop behind modals and sheets
- **[Sheets](sheets/README.md)** - Slide-in panels from the edges of the screen

## Shared features

Overlay components typically share these behaviors:

- **`disclosure`** - A disclosure hook to control open/closed state
- **`closeOnOverlayClick`** - Close when clicking the background
- **`closeOnEscape`** - Close when pressing the Escape key
- **`lockScroll`** - Prevent background scrolling while open
