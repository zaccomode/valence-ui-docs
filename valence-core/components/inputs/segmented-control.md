---
description: 'Last updated: 3.0.0 (04/07/2024)'
---

# Segmented Control

The Segmented Control is an input component that allows users to select one option from a set of mutually exclusive options. It presents options as a row of buttons within a styled container.

## Usage

```tsx
import { SegmentedControl } from "@valence-ui/core";
import { useState } from "react";

function MyComponent() { 
    const [value, setValue] = useState("option1");

    return ( 
        <SegmentedControl
            value={value}
            setValue={setValue}
            options={["option1", "option2", "option3"]}
        />
    )
}
```

### Custom labels

By default, the option value will be used as the label. To provide custom labels, use the object form:

```tsx
import { SegmentedControl } from "@valence-ui/core";
import { useState } from "react";

function MyComponent() { 
    const [value, setValue] = useState("sm");

    return ( 
        <SegmentedControl
            value={value}
            setValue={setValue}
            options={[
                { value: "sm", label: "Small" },
                { value: "md", label: "Medium" },
                { value: "lg", label: "Large" },
            ]}
        />
    )
}
```

### Custom label components

Labels can also be React nodes, allowing for icons or other custom content:

```tsx
import { SegmentedControl, Icon } from "@valence-ui/core";
import { IconList, IconLayoutGrid } from "@tabler/icons-react";
import { useState } from "react";

function MyComponent() { 
    const [value, setValue] = useState("list");

    return ( 
        <SegmentedControl
            value={value}
            setValue={setValue}
            options={[
                { value: "list", label: <Icon><IconList /></Icon> },
                { value: "grid", label: <Icon><IconLayoutGrid /></Icon> },
            ]}
        />
    )
}
```

### Styling

```tsx
import { SegmentedControl } from "@valence-ui/core";
import { useState } from "react";

function MyComponent() { 
    const [value, setValue] = useState("option1");

    return ( 
        <SegmentedControl
            value={value}
            setValue={setValue}
            options={["option1", "option2", "option3"]}
            
            variant="filled"
            size="md"
            radius="md"
            color="primary"
            equalWidth={true}
        />
    )
}
```

***

## Props

_Extends_ [_`GenericInputProps<string>`_](../../generics/generic-input-props.md) _and_ [_`StyledFlexProps`_](../layout/flex/styled-flex.md)_._

<table data-full-width="true"><thead><tr><th width="180">Property</th><th width="280">Type</th><th>Description</th></tr></thead><tbody><tr><td>options (required)</td><td><code>SegmentedControlOption[]</code></td><td>A list of options to supply for the content of this input.</td></tr><tr><td>onSelect</td><td><code>(value: SegmentedControlOption) => void</code></td><td>Callback to be called when an option is selected.</td></tr><tr><td>equalWidth</td><td><code>boolean</code></td><td>Whether every option should have an equal width. Defaults to <code>true</code>.</td></tr><tr><td>buttonProps</td><td><code>PrimitiveButtonProps</code></td><td>Optional props to pass to the child button components.</td></tr></tbody></table>

### SegmentedControlOption

Can be either a `string` or an object:

```tsx
type SegmentedControlOption = 
    | string
    | {
        /** The value of this option */
        value: string;
        /** The label to display for this option */
        label?: string | ReactNode;
    };
```
