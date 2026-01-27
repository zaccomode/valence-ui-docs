---
description: 'Last updated: 2.0.0 (18/01/2024)'
---

# Text input

## Usage

```tsx
import { TextInput } from "@valence-ui/core";

function MyComponent() { 
    const [value, setValue] = React.useState("");

    return ( 
        <TextInput
            value={value}
            setValue={setValue}
        />
    )
}
```

## Props

_Extends_ [_`GenericTextInputProps`_](../../generics/generic-input-props.md) _and_ [_`GenericTextInputEventProps`_](../../generics/generic-input-props.md)_._

<table data-full-width="true"><thead><tr><th width="164">Property</th><th width="243">Type</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td><a href="text-input.md#textinputtype"><code>TextInputType</code></a></td><td>The type of input to render. Defaults to <code>text</code>.</td></tr><tr><td>autoComplete</td><td><a href="text-input.md#autocompletebehaviour"><code>AutoCompleteBehaviour</code></a></td><td>The autocomplete behavior to use. Defaults to <code>off</code>.</td></tr><tr><td>multiple</td><td><code>boolean</code></td><td>For <code>type=email</code>, this specifies if this input accepts multiple values.</td></tr><tr><td>grow</td><td><code>boolean</code></td><td>Shorthand for <code>flex-grow = 1</code>.</td></tr></tbody></table>

### TextInputType

Defines the type of input that will be rendered.

```json
"text" | "password" | "email" | "number" | "tel" | "url" | "search";
```

### AutoCompleteBehaviour

Defines the type of autocomplete behaviour that will be used.

```json
"off" | "on" | "name" | "honorific-prefix" | "given-name" | "additional-name" | "family-name" | "honorific-suffix" | "nickname" | "email" | "email" | "username" | "new-password" | "current-password" | "one-time-code" | "organization-title" | "organization" | "street-address" | "shipping" | "billing" | "address-line1" | "address-line2" | "address-line3" | "address-level4" | "address-level3" | "address-level2" | "address-level1" | "country" | "country-name" | "postal-code" | "cc-name" | "cc-given-name" | "cc-additional-name" | "cc-family-name" | "cc-number" | "cc-exp" | "cc-exp-month" | "cc-exp-year" | "cc-csc" | "cc-type" | "transaction-currency" | "transaction-amount" | "language" | "bday" | "bday-day" | "bday-month" | "bday-year" | "sex" | "tel" | "tel-country-code" | "tel-national" | "tel-area-code" | "tel-local" | "tel-extension" | "impp" | "url" | "photo" | "webauthn"
```
