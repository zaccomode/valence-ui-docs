---
description: 'Last updated: 4.0.0'
---

# Stepper

The Stepper component system is useful for displaying a list or guide that a user can progress through.

## Usage

```tsx
import { Stepper, Text } from "@valence-ui/core";

function MyComponent() { 
    const [currentStep, setCurrentStep] = React.useState(0);

    return ( 
        <>
            <Stepper
                currentStep={currentStep}
            >
                <Stepper.Step>
                    <Text size="xl">
                        Step 1
                    </Text>
                </Stepper.Step>
                
                // Other steps
            </Stepper>
        </>
    )
}
```

The Stepper does not expose any way to internally control the current step, as it is expected this logic should be handled by the Stepper's children.&#x20;

***

## Props

### StepperProps

_Extends_ [_`GenericProps`_](../../../valence-utils/generics/global.md)_._

<table data-full-width="true"><thead><tr><th width="211">Property</th><th width="256">Type</th><th>Description</th></tr></thead><tbody><tr><td>currentStep (required)</td><td><code>number</code></td><td>The current step to display.</td></tr><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material to apply to this stepper.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>The size of this stepper.</td></tr><tr><td>color</td><td><code>CSSProperties["color"]</code></td><td>The color of this stepper.</td></tr></tbody></table>

### StepperIndicatorProps

<table data-full-width="true"><thead><tr><th width="157">Property</th><th width="260">Type</th><th>Description</th></tr></thead><tbody><tr><td>step (required)</td><td><code>number</code></td><td>The step number for this indicator.</td></tr><tr><td>state</td><td><a href="stepper.md#stepperindicatorstate"><code>StepperIndicatorState</code></a></td><td>The current state of this indicator.</td></tr><tr><td>material</td><td><a href="../../../core-concepts/materials/README.md"><code>Material</code></a></td><td>The material to apply to this indicator.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>The size of this indicator.</td></tr></tbody></table>

### StepperIndicatorState

```tsx
type StepperIndicatorState = "default" | "active" | "complete";
```

### StepperStepProps

_Extends_ [_`FlexProps`_](../layout/flex/#props)_._

No unique props.

## Changelog

* **4.0.0:** Replaced `variant` with `material` on both the stepper and its indicators. `StepperIndicator` no longer takes a `color`.
