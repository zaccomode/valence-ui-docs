---
description: 'Last updated: 2.0.0 (18/01/2024)'
---

# Pill selector

## Usage

```tsx
import { PillSelector } from "@valence-ui/core";

function MyComponent() { 
    const [value, setValue] = React.useState(["hello", "world"]);

    return ( 
        <PillSelector 
            value={value}
            setValue={setValue}
            pills={["hello", "there", "world"]}
        />
    )
}
```

### Add new pills

To allow users to add new pills to this input, the `allowEditing` prop must be used. Additionally, the `pills` and `setPills` props must be tied to a React state, allowing them to be updated.

Allowing editing will create a new [Text input](text-input.md) above the Pill selector. Using this text editor, the user may type out a new pill and use the `Enter` key or the accompanying add button to create and select that pill. If the user then de-selects a pill they have created, it will be deleted from the list of pills as well.

The `placeholder`, `inputProps`, `addButtonProps` and `addButtonIcon` props can be used to modify the appearance and behavior of the inputs created when adding new pills.

```tsx
import { PillSelector } from "@valence-ui/core";

function MyComponent() { 
    const [selected, setSelected] = React.useState(["hello", "world"]);
    const [pills, setPills] = React.useState(["hello", "there", "world"]);

    return ( 
        <PillSelector 
            value={selected}
            setValue={setSelected}
            
            pills={pills}
            setPills={setPills}
            allowEditing
        />
    )
}
```

### Change wrap style

By default, the Pill selector will be formatted as a horizontally-scrolling series of pills, but the `wrap` prop exists to allow different wrapping of the input.

Setting `wrap="wrap"` allows the input to display every pill at once as a block:

```tsx
import { PillSelector } from "@valence-ui/core";

function MyComponent() { 
    const [value, setValue] = React.useState(["hello", "world"]);

    return ( 
        <PillSelector 
            value={value}
            setValue={setValue}
            pills={["hello", "there", "world"]}
            
            wrap="wrap"
        />
    )
}
```

***

## Props

_Extends_ [_`GenericInputProps<string[]>`_](../../generics/generic-input-props.md) _and `PillSelectorEventProps`._

<table data-full-width="true"><thead><tr><th width="186">Property</th><th width="362">Type</th><th>Description</th></tr></thead><tbody><tr><td>pills (required)</td><td><code>string[]</code></td><td>A list of pills to display.</td></tr><tr><td>setPills</td><td><code>(pills: string[]) => void</code></td><td>Optional callback to complete the state.</td></tr><tr><td>allowClear</td><td><code>boolean</code></td><td>Whether to allow pills to be cleared. <code>true</code> by default.</td></tr><tr><td>grow</td><td><code>boolean</code></td><td>Shorthand for <code>flex-grow = 1</code></td></tr><tr><td>gap</td><td><code>number</code></td><td>Sets the gaps between everything. <code>5</code> by default.</td></tr><tr><td>wrap</td><td><code>CSSProperties["flexWrap"]</code></td><td>How the pills should wrap within their container. Defaults to <code>"nowrap"</code>.</td></tr><tr><td>maxSelectable</td><td><code>number</code></td><td>The maximum number of pills that can be selected. <code>Infinity</code> by default.</td></tr><tr><td>clearButtonIcon</td><td><code>ReactNode</code></td><td>An icon to use for the clear button. Defaults to <code>IconX</code></td></tr><tr><td>clearButtonProps</td><td><code>Omit&#x3C;IconButtonProps, "children"></code></td><td>Optional props to pass to the clear button.</td></tr><tr><td>pillProps</td><td><code>Omit&#x3C;TextButtonProps, "children"></code></td><td>Optional props to pass to all pills.</td></tr><tr><td>selectedPillProps</td><td><code>Omit&#x3C;TextButtonProps, "children"></code></td><td>Optional props to pass to selected pills. Will override attributes from <code>pillProps</code>.</td></tr><tr><td>pillContainerProps</td><td><code>Omit&#x3C;FlexProps, "children"></code></td><td>Optional props to pass to the pill container.</td></tr><tr><td>allowEditing</td><td><code>boolean</code></td><td>Whether to allow the creation of new pills.</td></tr><tr><td>placeholder</td><td><code>string</code></td><td>Placeholder text to display in the Text input. Will only show if <code>allowEditing = true</code>.</td></tr><tr><td>inputProps</td><td><code>Omit&#x3C;TextInputProps, "value"|"setValue"></code></td><td>Optional styles to pass to the Text input.</td></tr><tr><td>addButtonProps</td><td><code>Omit&#x3C;IconButtonProps, "children"></code></td><td>Optional props to pass to the add button.</td></tr><tr><td>addButtonIcon</td><td><code>ReactNode</code></td><td>Optional icon to use for the add button.</td></tr></tbody></table>

### PillSelectorEventProps

Extends `MouseClickEvents`, `MouseEvents`, `PointerEvents`, `FocusEvents` and `KeyboardEvents`.

<table data-full-width="true"><thead><tr><th width="176">Property</th><th width="263">Type</th><th>Description</th></tr></thead><tbody><tr><td>onPillSelected</td><td><code>(value: string) => void</code></td><td>Callback to be fired when a pill is selected.</td></tr><tr><td>onPillDeselected</td><td><code>(value: string) => void</code></td><td>Callback to be fired when a pill is deselected.</td></tr></tbody></table>
