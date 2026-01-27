# ⌨ Inputs

Input components allow users to enter and modify data. Valence provides a comprehensive set of input components for various data types and use cases.

## Available inputs

### Text inputs
- **[Text Input](text-input.md)** - Single-line text input
- **[Text Area](text-area.md)** - Multi-line text input
- **[Number Input](number-input.md)** - Numeric input with increment/decrement controls

### Selection inputs
- **[Select Input](select-input.md)** - Dropdown selection input
- **[Pill Selector](pill-selector.md)** - Multi-select using pill buttons
- **[Segmented Control](segmented-control.md)** - Single-select between a small set of options

### Range inputs
- **[Slider](slider.md)** - Single value slider
- **[Range Slider](range-slider.md)** - Dual-handle range slider

### Toggle inputs
- **[Switch](switch.md)** - Boolean toggle switch

### Specialized inputs
- **[Color Picker](color-picker.md)** - Color selection input

### Containers
- **[Input Container](input-container.md)** - Wrapper for input styling
- **[Dropdown Container](dropdown-container.md)** - Container for dropdown menus

## Shared features

All inputs share common props inherited from [`GenericInputProps`](../../generics/generic-input-props.md), including:

- **`value`** and **`setValue`** - Controlled input state
- **`size`**, **`radius`**, **`variant`** - Styling options
- **`disabled`**, **`readOnly`**, **`required`** - State modifiers
- **`loading`** - Loading state indicator
